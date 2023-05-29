# Frontend Mentor - Results summary component solution

This is a solution to the [Results summary component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/results-summary-component-CE_K6s0maV). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page

### Screenshot

![desktop site preview](./assets/images/site-preview-desktop.png)
![mobile site preview](./assets/images/site-preview-mobile.png)

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow

### What I learned

CSS does not support transitions for linear gradient. To get around this, I used a pseudo element (::before) beneath my button element, with an opacity of 0 which contained the gradient I wanted to transition to. Then I added a transition to the opacity from 0 to 1 at hover and focus states.

```html
<button id="summary__continue">Continue</button>
```

```css
#summary__continue {
  background: var(--text__accent);
  transition: background 1s;
  z-index: 100;
  position: relative;
}
```

```css
#summary__continue::before {
  content: '';
  display: block;
  width: 100%;
  height: 100%;
  border-radius: 50px;
  position: absolute;
  top: 0;
  left: 0;
  opacity: 0;
  background: linear-gradient(
      var(--bg__light),
      var(--bg__dark)
  );
  z-index: -100;
  transition: opacity 0.4s;
}
```

```css
#summary__continue:hover::before,
#summary__continue:focus::before {
    opacity: 1;
}
```

### Useful resources

- [Animating CSS Gradients, using only CSS](https://medium.com/@dave_lunny/animating-css-gradients-using-only-css-d2fd7671e759) - This helped me understand how to implement a transition with linear gradients.

## Author

- Frontend Mentor - [@ragonscreen](https://www.frontendmentor.io/profile/ragonscreen)

## Acknowledgments

- I would once again, like to thank [Kevin Powell](https://www.youtube.com/@KevinPowell) for introducing me to Frontend Mentor and his other awesome CSS guides.
