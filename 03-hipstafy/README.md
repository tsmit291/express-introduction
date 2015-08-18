## Set Up

```
npm install
nodemon bin/www or DEBUG=exporting-modules:* npm start
```

## Instructions

Use `body-parser`, `module.exports` and `require` to accomplish the following:

1. Build a form that uses `textarea` and allows users to submit random sentences.
![](wireframes/hipstafy.png)
1. Using `POST` and `body-parser` in your route, capture the user input.
1. In `public/javascripts/hipstafy.js` write a function that returns a 'hipstafied' response using the user input.

For every word input by the user, the function should:
 - return a random hipster snippet from `models/hipstafy.js`
 - split up the user input and mix each word in between a hipster snippet.

EXAMPLE:

If the user input was "Hey what's up??", your app would return this:

```
Hey Portland Pug
what's mustache Intelligentsia
up?? Thundercats mullet
```
NOTE: The user input was 3 words, so the function returned 3 hipster snippets mixed in with the 3 words the user input.

```
module.exports = [
  "Brooklyn fap",
  "Portland pug",
  "90s sustainable quinoa ",
  "Artisan Thundercats drinking Pabst",
  "chia readymade",
  "flexitarian",
  "lo-fi fashion",
  "mustache Intelligentsia",
  "Aesthetic keytar",
  "hella beard boy",
  "Beards",
  "mixologist",
  "craftsmania",
  "like a broke ass mothafucka",
  "keytar beard",
  "Thundercats mullet",
  "dayglo milk fat",
  "zebras zebras lions and bears"
];
```

```
extends layout

block content
  h1.title= title
  h3.subtitle #{subtitle}
  div.container
      div.form
        label(id="sentence") Write a sentence or two, and we'll hipstafy it for you!
      div.form
        textarea(id="sentence", rows="4", cols="70", type="text", name="sentence")
      div.form
        input(type="submit" value="hipstafy!")
```

#### DON'T FORGET

Use `module.exports` and `require` to access the function in your routes (to pass user input to your function and get the results) and also to use the hipster snippets found in `models/hipstafy.js` in your function.
