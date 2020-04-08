# 1.3.1 - CSS Page Layout

---

## CSS Pixels

- Your monitor is divided into pixels (screen pixels).
- When you write CSS, you specify the height, width and position in `px` units.

This `px` unit is **not** a screen pixel, but a CSS pixel.

---

- Small laptop resolution: 1366 x 768
- "1080p" resolution: 1920 x 1080
- iPhone X screen resolution: 2436 x 1125

---

### Example of a Desktop site

<img src="./assets/nresp_desktop.png" />

---

The same site on a mobile device

<img src="./assets/nresp_mobile.png" />

---

## "Retina displays"

Apple's fancy branding term

Every "normal" pixel is made up of 4 pixels.

---

## A Quick Fix?

Add the following to your HTML page(s)

`<meta name="viewport" content="width=device-width, initial-scale=1.0" />`

This will make the CSS pixels scale on mobile devices.

---

The same site _fixed_

<img src="./assets/nresp_mobile_fix.png" />

---

## Responsive Web Design

---

Websites shift content around depending on the screen size.

[Montreal Gazette](https://montrealgazette.com/)

---

## Mobile-first

In design, it is recommended to _start with the mobile size_.

It's easier to add stuff for larger screens than to take away stuff on smaller screens.

---

## So how do we implement these things?

---

## [Media queries](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp) 🥳

Media queries can be used to check many things, such as:

- width and height of the viewport
- width and height of the device
- orientation (landscape or portrait)
- resolution

---

### A basic media query

- min-width first is for mobile -> tablet -> desktop
- max-width first is for desktop -> tablet -> mobile

[Try it](https://www.w3schools.com/css/tryit.asp?filename=trycss_mediaqueries_ex1)

---

# Exercises

---

# Exercise 1

Change the font size based on the window size

https://codepen.io/joshwcomeau/pen/QWbeygM?editors=1100

Solutions:

```css
@media (min-width: 600px) {
  h1 {
    font-size:22px;
  }
}

@media (min-width: 1000px) {
  h1 {
    font-size:32px;
  }
}
```
---

# Exercise 2

Change the flex direction based on the orientation

https://codepen.io/joshwcomeau/pen/wvaVMpJ?editors=1100

Solution:

```css
@media (orientation: landscape) {
  .wrapper {
    justify-content: center;
    flex-direction: row;
  }
  section {
    flex: 1;
  }
}
```

---

# Exercise 3

Use a media query to stack the two columns

https://codepen.io/joshwcomeau/pen/GRJVpYb?editors=1100

Solution:

```css
@media (max-width: 600px) { 
  .wrapper {
    flex-direction: column;
  }
}
```

---

# Fonts on the Web

There are only about a dozen fonts that come included with all operating systems.

They aren't pretty.

---

Use link tags in your header to reference font familys which you can activate
later.

[Google Fonts](https://fonts.google.com/)

---

# Advanced topics

---

## CSS Pseudo selectors

### [Pseudo classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#Index_of_standard_pseudo-classes)

Allows for styling based on user interaction

- `:hover`
- `:focus`
- `:checked`
- `:first-child`

[Try it](https://www.w3schools.com/css/tryit.asp?filename=trycss_link) | [Try it](https://www.w3schools.com/css/tryit.asp?filename=trycss_first-child2)

- `:before` and `contents:""` allows you to add text to every tag selected, instead of having to add the content yourself
- pseudo selectors can be nested like `a:hover:before {}`


---

### CSS Viewport units

There are many units in CSS.

Here are two handy ones:

- `vh` - percentage of the Viewport Height
- `vw` - percentage of the Viewport Width

https://codepen.io/joshwcomeau/pen/gOpVMRE

---

## [CSS Transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)

- Translate
- Rotate
- Scale

[Try it](https://www.w3schools.com/cssref/tryit.asp?filename=trycss3_transform) | [Trnasform Generator](https://html-css-js.com/css/generator/transform/)

 
 ### Some examples

- `transform: width 0.5s;` increases width with a transformation
- `transform: scale(x);` scales up the text by x amount, same with `scaleX()` or `scaleY()`
- `transform: rotate(45deg);` rotates

Use `transition: transform 0.5s;` to slow down the animation a little bit to make it smoother.

This code, will add a small red square before text, and when a user hover overs the P tag element on the webpage, the red square will rotate.

```css
p:hover:before {
    transform: rotate(45deg);
    transition: 250ms;
}

p:before {
    content: '';
    display: block;
    width: 10px;
    height: 10px;
    background: red;
    transition: transform 2750ms;
}
```

- The empty `content: ""` is required for the page to load the red square.
- The additional `transition: transform 2750ms` returns the square back to its original state, in a smoother animation when not hovered on.
- You can also add another `transform: rotate(-360deg);` in the `p:before{}` so that the default state will have the red square rotate back instead of going back to `deg(0);`

### Example: Smooth Accordion

In a mobile experience, when you have a p tag that is collaspable (contains text), on a deskptop experience, you want this transition to be smooth. But for mobile users, this should not be the case. The accordion as its called will be set to have a 0ms transition as follows:

```css

@media (max-width:2380px) {
  *, *:before, *:after {
    transition-duration: 0ms
    !important;
  }
}

```
---

## CSS Animation

Two ways to do this.

- Transition
- Keyframe animations 

### Keyframe Animations

A red box will slowly fade in whenever the page is loaded.

```css
@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 100;
  }
}

.box {
  height: 30px;
  width: 30px;
  background: red;
  animation-name: fadeIn;
  /* if you want to have a delay, add anoter time attribute like 5000ms to the animation line */

  animation-duration: 3500ms; /* how long the animation lasts */
  animation-delay: 1000ms:
  animation-fill-mode: both; 
  /* backwards: reverts back to default styling before animation */
  /* forwards: keeps styling as defined by the animation */
  /* both: loops it   */



}
```