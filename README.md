# Ponyshow Web Client

Web client for Ponyshow presentations.  Download the [app](http://www.semanticpress.com/ponyshow) or install the [command line tool](http://github.com/ponyshow/ponyshow).

This client is required for viewing Ponyshow markdown files.

## Hosted CDN

You can access the latest version of the client here: 

- CSS: [http://cdn.jsdelivr.net/ponyshow-web-client/latest/css/main.css](http://cdn.jsdelivr.net/ponyshow-web-client/latest/js/main.js)
- JS: [http://cdn.jsdelivr.net/ponyshow-web-client/latest/js/main.js](http://cdn.jsdelivr.net/ponyshow-web-client/latest/js/main.js)

## To Compile

1. Install dependencies ```npm install```
2. Run ```gulp```

Compiled version is in the ```dist``` folder.

# API

## `shower`

### Properties

- `debugMode`: boolean

### Methods

#### Private Methods

##### `_getSlideTitle(<integer> slideNumber)`

Get slide title by number.
  
##### `showPresenterNotes(<integer> slideNumber)`

Show presenter notes in console.

##### `_turnPreviousSlide()`

Show previous slide. 

Returns false on a first slide, otherwise returns shown slide number.

##### `_turnNextSlide()`

##### `_checkInteractiveElement()`

For touch devices: check if link is clicked.

##### `_getSlideIdByEl()`

Get slide id from HTML element.

##### `_normalizeSlideNumber(<integer> slideNumber)`

Normalize slide number.

##### `_isNumber()`: Check if arg is number.

##### `_applyTransform(<string> transform)`

Set CSS transform with prefixes to body.

##### `_getTransform()`: Get slide scale value.

##### `_getData(<HTMLElement> element, <string> name)`

Get value at named data store for the DOM element.

#### Public Methods

##### `init(<string> slideSelector, <string> progressSelector)`

Shower initialization

- `run()`

Run shower by going to slide and entering slide mode if needed.

##### `go(<integer> slideNumber, <function> callback)`

Go to slide number.

##### `next()`

Show next slide or show next Inner navigation item.

Returns false on a last slide, otherwise returns shower.

##### `prev()`

Show previous slide. Returns false on a first slide, otherwise returns shown slide number.

##### `getSlideNumber(<string> slideId)`

Get slide number by slideId (string).

##### `getSlideHash(<integer> slideNumber)`

Get slide hash.

```javascript

```

##### `clearPresenterNotes()`

Clear presenter notes in console (only for Slide Mode).

##### `updateActiveAndVisitedSlides(<integer> slideNumber)`

Update active and visited slides.

##### `updateProgress(<integer> slideNumber)`

Update progress bar.

##### `isSlideMode()`

Check if it's Slide mode.

##### `isListMode()`

Check if it's List mode.

##### `scrollToSlide(<integer> slideNumber)`

Scroll to slide.

##### `getCurrentSlideNumber()`

Get current slide number. Starts from zero. Warning: when you have slide number 1 in URL this method will return 0. If there is no slide number in url, AND slide does not exist, return -1.

##### `toggleMode(<function> callback)`

Toggle Mode: Slide and List.

##### `enterListMode(<function> callback)`

Switch to list view.

##### `enterSlideMode(<function> callback)`

Switch to slide view.

##### `last(<function> callback)`

Show last slide.

##### `first(<function> callback)`
  
Show first slide.

### Document events

- `click`
- `touchstart`
- `touchmove`
- `keydown`


### Window Events

- `resize`
- `keydown`
- `popstate`
- `DOMContentLoaded`


### Tint Events

Callback events are fired for `document.keydown` events.

- `keydown`
- `exitApp`: cmd+q
- `setWindowState`: fullscreen, maximized
- `newFile`: cmd+n
- `editorPanelButton`: [, ]
- `unknown`


## Contribution and License Agreement

If you contribute code to this project, you are implicitly allowing your code
to be distributed under the Apache 2 license. You are also implicitly verifying that
all code is your original work. `</legalese>`

## Author

TZ Martin <martin@semanticpress.com>

## License

Copyright (c) 2015, Semantic Press (Apache 2 Licensed)

See LICENSE for more info.