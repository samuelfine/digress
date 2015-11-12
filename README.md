# Digress
Digress is a simple, lightweight library for creating dynamic, toggleable footnotes or helpful hints. Unlike other libraries, Digress is dependency free. Seriously. Doesn't even need jQuery.
## Installation
1. Download digress.js and digress.css, and include them in your project.
```HTML
<link rel="stylesheet" href="digress.css">
<script src="digress.js"></script>
```
(You'll need to upgrade the `href` and `src` depending on the files' locations in your directory structure, of course.)
## Usage
Digress requires three parts to function properly:

#### 1. Notes
These are HTML elements that will be shown/hidden, containing the content you want to display to the user. To function as a Digress note, an element needs to have the ```digress-note``` class, and a unique ID.
```HTML
<div class="digress-note" id="footnote-1">
  I was very surprised to learn this.
</div>
```
#### 2. Triggers
These are HTML elements that will toggle a given note. To function as a Digress trigger, an element needs to have the ```digress-trigger``` class, and a ```data-digress-trigger``` attribute that correlates to a Digress note's ID.
```HTML
<div class="digress-trigger" data-digress-trigger="footnote-1"></div>
```
#### 3. Javascript
Call the ```digress()``` function at the bottom of your page, after your HTML triggers and notes.
```Javascript
digress({
  // Options (optional). Example:
  // position: 'right'
});
```
For greater reliability, call the function after the document has loaded. ```document.addEventListener('DOMContentLoaded', fn, false);``` for example, or ```$( document ).ready()``` if you're using jQuery.
## Options

Option | Description | Default | Values
------------- | ------------- | ------------- | -------------
```position```  | (String) The position that a note will display, relative to its trigger. Additional positioning details can be applied via CSS. (See below.) | ```top``` | ```top, left, bottom, right```

## Styling / Positioning
Triggers can be styled via their ```.digress-trigger``` class, and notes can by styled via their ```.digress-note``` class. Active triggers—that is, triggers whose note is visible—are given an ```.active``` class for additional styling.

Some basic default styling is included in ```digress.css```, and the file is commented in regards to which CSS rules are required for Digress to function properly, and which can be modified or overridden as desired.