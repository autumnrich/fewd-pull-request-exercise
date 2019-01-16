class: center, middle

## Unit 6
# Responsive Web Design

---

name: rwd-definition
class: center, middle
# What is Responsive Web Design (RWD)?

![Responsive Web Design](../assets/rwd.jpg)

---

name: rwd-ethan-marcotte

# The Father of Responsive Web Design

> The web's moved beyond the desktop, and it's not looking back. The number of devices we're designing for is growing just as quickly as mobile traffic.

<cite>-- Ethan Marcotte</cite>

### - .red-text[2010:] alistapart.com/article/responsive-web-design/
### - .red-text[2011:] Responsive Web Design (first edition)
### - .red-text[2014:] Responsive Web Design (2nd edition)

???
A List Apart: [Responsive Web Design](http://alistapart.com/article/responsive-web-design/) by Ethan Marcotte

A Book Apart: [Responsive Web Design](http://abookapart.com/products/responsive-web-design)

Creative Bloq: [Ethan Marcotte on responsive web design](http://www.creativebloq.com/netmag/ethan-marcotte-responsive-web-design-1126512)

---

name: rwd-timeline
class: left

# RWD Timeline

> I think of responsive design as an alternative to mobile sites.

<cite>-- Ethan Marcotte</cite>

### Desktop & Laptop &rarr; iPhone .red-text[(2007)] &rarr; EM RWD .red-text[(2010)] &rarr;

### EM RWD Book .red-text[(2011 1st ed.)] &rarr; EM RWD Book .red-text[(2014 2nd ed.)]

---

name: rwd-principles
class: center, middle

# 3 Core Components of RWD

### - Fluid grids
### - Flexible images
### - Media queries

---

name: rwd-layouts
class: center, middle

## Fixed Width Layout .red-text[(rigid px)] &rarr; Liquid Layout .red-text[(arbitrary %)] &rarr; Fluid Grid .red-text[(smart % proportions)]

---

name: rwd-fluid-grid
class:

# Fluid Grid

## target / context = result

### 960px / 1920px = 50%

.float-left[<img src="../assets/rwd-fluid-grid.png" alt="Fluid Grid" style="width: 600px;"/>]

### Smart Proportions 🙌

#### .red-text[sidebar:] 300px / 960px = 31.25%
#### .red-text[main content:] 640px / 960px = 66.66667%
#### .red-text[margin:] 20px / 960px = 2.08334%

???
Treehouse: [The 2014 Guide to Responsive Web Design](http://blog.teamtreehouse.com/modern-field-guide-responsive-web-design)

---

name: rwd-flexible-image
class:

# Flexible Images

```css
img {
	max-width: 100%;
	height: auto;
}
```

### - Images should only ever be as large as their physical width in pixels
### - If nested inside a smaller parent container, then the image should shrink
### - Height will be calculated automatically, will maintain original aspect ratio

---

name: rwd-media-query
class:

# Media Queries

```css
@media screen and (max-device-width: 480px) {

  /* If the above condition is met, the styles below will be applied */
	p {
		color: blue;
	}
}
```

### - The above media query checks whether the current horizontal screen size .red-text[(max-device-width)] is equal to or less than 480px.
### - If so, the CSS rules defined within the media query will be applied.

???

* W3C: [Media Queries](http://www.w3.org/TR/CSS21/media.html)
* W3Schools: [Responsive Web Design - Media Queries](https://www.w3schools.com/css/css_rwd_mediaqueries.asp)
* screensiz.es: [screensiz.es](http://screensiz.es)

---

name: rwd-media-query-anatomy
class:

# Anatomy of a Media Query

```css
@media screen and (min-width: 768px) and (orientation: landscape) {

  /* ... styles here ... */

}
```

### - media type (all, screen, print, tv, ...)
### - the query itself wrapped in parentheses
### - name of feature
### - corresponding value

???

* [More Media Query Syntax Details](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp)

---

name: rwd-media-query-features
class: center

## In the W3C specs, every device has a .red-text["display area"] and .red-text["rendering surface."]

## .red-text[display area] = browser viewport = browser window
## .red-text[rendering surface] = entire display = screen

#### `width` = display area width = viewport width
#### `height` = display area height = viewport height
#### `device-width` = rendering surface width = screen width
#### `device-height` = rendering surface height = screen height

---

name: rwd-mobile-viewport
class:

# Mobile Browser Viewport

### Mobile browsers render pages in a virtual "window" (the viewport). This viewport is usually wider than the physical screen (e.g. .red-text[980px] for mobile Safari).

### That way these browsers don't need to squeeze every page layout into a tiny window, which would break many non-mobile-optimized sites. Users can pan and zoom to see different areas of the page.

???

MDN: [Using the viewport meta tag to control layout on mobile browsers](https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag)

---

name: rwd-viewport-meta-tag-history
class:

# Viewport Meta Tag History

### Mobile Safari introduced the "viewport meta tag" to let web developers control the viewport's size and scale. Many other mobile browsers now support this tag, but it's not part of any web standard.

???

Safari Developer Library: [Configuring the Viewport](https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariWebContent/UsingtheViewport/UsingtheViewport.html)

quirksmode.org: [A Tale of Two Viewports](http://www.quirksmode.org/mobile/viewports2.html)

---

name: rwd-viewport-meta-tag
class:

# Viewport Meta Tag

### - a typical mobile-optimized page contains something like:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### - `width` property controls the size of the viewport
### - It can be set to a specific number of pixels (e.g. `width=320`) or to `device-width`, which is the width of the screen in CSS pixels at a scale of 100%
### - `initial-scale` controls the zoom level when the page is first loaded

???

Google Developers: [Configuring the Viewport](https://developers.google.com/speed/docs/insights/ConfigureViewport?hl=en)

---

name: rwd-mobile-first
class:

# Mobile First Development Approach

```css
/* Extra small devices (phones, less than 768px) */
/* No media query since this is the default in Bootstrap */

/* Small devices (tablets, 768px and up) */
@media (min-width: 768px) { /* Styles Here */ }

/* Medium devices (desktops, 992px and up) */
@media (min-width: 992px) { /* Styles Here */ }

/* Large devices (large desktops, 1200px and up) */
@media (min-width: 1200) {/* Styles Here */ }
```

### It can be tricky to cram a multi-column layout into a smaller screen space. Instead, it’s better to design for smaller screens _first_, then work upwards to more complex designs.

???

Luke Wroblewski: [Mobile First](http://www.lukew.com/ff/entry.asp?933)
