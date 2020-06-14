---
layout: post
title:      "How are are these connected? Javascript and Rails Project"
date:       2020-06-14 12:41:53 -0400
permalink:  how_are_are_these_connected_javascript_and_rails_project
---

My Make Inspiration App was inspired by John Oliver's [Definitely Real Quotes](http://www.definitelyrealquotes.com/). In his segment from a few year's back John discussed politicians using fake quotes (either intentionally or not, it doesn't matter) to support their (usually completely infuriating) beliefs. I thought it would be fun to use a madlibs-like premise to create funny, inspirational quotes that can be shared like the real thing! Ridiculous nature photo backgrounds and all!

<iframe width="560" height="315" src="https://www.youtube.com/embed/2ViZipJUcD0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The most challenging part of this Javascript and Rails project was connecting the two parts - a Javascript based frontend and Rails API backend. My project connects a Rails API, which holds a random collection of quote Templates, to my Javascript frontend, which takes in three words to be entered mad-libs style into the Template. This new Quote is then posted back to the database. Lots of back and forth there! 

The magic begins with a FETCH request: 

```
function fetchRandomTemplate() {
  fetch(templatesURL)
  .then(resp => resp.json())
  .then(templates => {
      randomTemplateId = templates[Math.floor(Math.random() * templates.length)]
      let randomTemplateContent = randomTemplateId.content
      let templateImage = randomTemplateId.image_url
  })
	
   //renders template
}
```
This requests selects a random Template object, which consists of content and an image, to be manipulated in our front end. The template is then associated to the final Quote. (A Template ```has_many``` Quotes, because Templates can be reused multiple times.)

Then, I used Javascript to receive input values from my HTML form. 

```
function createFormHandler(e) {
  e.preventDefault()
  const nounInput = document.querySelector('#input-noun').value
  const verbInput = document.querySelector('#input-verb').value
  const adjectiveInput = document.querySelector('#input-adjective').value

  quoteID = quoteID
  updateQuote(quoteID, nounInput, verbInput, adjectiveInput) 
}
```

This info is used to ```updateQuote( )``` and posted back to the database using a PATCH request. 

```
function postQuote(newQuote, quoteID) {

  let newContent = newQuote
  fetch(`${quotesURL}/${quoteID}`, {
    method: "PATCH",
    headers: {
      'Content-Type': 'application/json',
      'Accept': 'application/json',
    },
    body: JSON.stringify({
      template: newContent
    })
  })
    .then(response => response.json())
    .then(updatedQuote => {
      // renders new quote
    })
}
```

If this app is deployed in the future, I'd love to add additional functionality like: 
<ul>
<li>A users model with authorization to sign in and save all your quotes to one place.</li>
<li>The ability to post the finished quote to social media.</li>
<li>A watermark of some sort on the photo so people know where it came from and it's not real.</li>
<li>More quote templates!</li>
</ul>


