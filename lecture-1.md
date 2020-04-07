# 1.3.1 - CSS Page Layout

---

## [CSS Combinators(]https://developer.mozilla.org/en-US/docs/Web/CSS/Adjacent_sibling_combinator)

Sometimes, we want need to use a more convoluted targeting method. 😜

- Adjacent sibling combinator `div + p`
- General sibling combinator `div ~ p`
- Child combinator `div > p`
- Descendant combinator `div p`

---


## CSS Pixels

- Your monitor is divided into pixels (screen pixels).
- When you write CSS, you specify the height, width and position in `px` units.

This `px` unit is **not** a screen pixel, but a CSS pixel.

It's approx. 1/96 inches, _but it varies from display to display._

---

### Example of a Desktop site

<img src="./assets/nresp_desktop.png" />

---

The same site on a mobile device

<img src='./assets/nresp_mobile.png' />

---

## A Quick Fix?

Add the following to your HTML page(s)

`<meta name="viewport" content="width=device-width, initial-scale=1.0" />`

This will make the CSS pixels scale on mobile devices.

---

The same site _fixed_

<img src='./assets/nresp_mobile_fix.png' />

---

## [Responsive vs. Mobile-first](https://darwindigital.com/mobile-first-versus-responsive-web-design/)

---

<img src='./assets/responsive.png' />

---

<img src='./assets/mobile_first.png' />

---

### Responsive (pros)

- Good for heavily stacked information websites
- Easier for large forms and complex call-to-actions
- Cost-effective development and maintenance
- Great for SEO

---

### Responsive (cons)

- The mobile experience is not 100% optimized

---

### Mobile-First (pros)

- Better user-experience on mobile devices
- Majority of internet browsing in on a smartphone
- Design website to use built-in phone features
- Cheaper than building an iOS, Android or Hybrid App
- Easier to add new stuff once we go to a desktop size screen

---

### Mobile-First (cons)

- The desktop experience is not 100% optimized
- Not suited for content heavy websites

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

[Try it](https://www.w3schools.com/css/tryit.asp?filename=trycss_mediaqueries_ex1)

---

# Advanced topics

---

## CSS Pseudo selectors

### [Pseudo classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#Index_of_standard_pseudo-classes)

- `:hover`
- `:focus`
- `:checked`
- `:first-child`

[Try it](https://www.w3schools.com/css/tryit.asp?filename=trycss_link)  |  [Try it](https://www.w3schools.com/css/tryit.asp?filename=trycss_first-child2)

---

### [Pseudo elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements#Index_of_standard_pseudo-elements)

- `::before`
- `::after`

[Try it](https://www.w3schools.com/css/tryit.asp?filename=trycss_before)

---

## [CSS Transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)

- Translate
- Rotate
- Scale

[Try it](https://www.w3schools.com/cssref/tryit.asp?filename=trycss3_transform) | [Trnasform Generator](https://html-css-js.com/css/generator/transform/)

---

