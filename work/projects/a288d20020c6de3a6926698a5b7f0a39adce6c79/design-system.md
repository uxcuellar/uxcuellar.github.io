---
layout: work
title: Goldstar's Design System
description: A design system that brings consistency and structure across multiple platforms.
tags: design research, visual design.
duration: 3 Months, April 2018.
sponsor: Goldstar Events
img: ds-header.jpg
sitemap: false
---
<script src="/flickity.js"></script>
---

### The story behind this project

In order to bring logic, consistency and structure to our design across multiple platforms, the design team at Goldstar decided to create a Design System. We didn't want to have just a UI kit, but a system that was flexible, scalable and able to enforce better workflows. All the elements in this system needed to have structure and meaning, and they also needed to be easily accessible not only to designers, but to all of our developers. This system was also part of a bigger rebranding effort that the company started months before.

### Steps

1. **Visual audit.**  
The first step was to do a visual audit of the current design, compiling all existing UI elements in order to find duplicities. We reviewed not only Goldstar's main consumer site, but all the different apps, marketing and internal tools.
2. **Creation of visual design language.**  
The visual design language is the core of any design system, and it includes things like colors, typography, spacers, separators and patterns. All these elements were based in Goldstar's new corporate branding.
3. **Creation of component libraries.**  
The design team decided that we would have separate component libraries for each product and we would start by building the one for our B2B marketing platform. This product is smaller than our consumer site and it’s perfect for testing the new libraries architecture, naming conventions, etc. My job was to build this first library and find the best way to put together everything using [Sketch](https://www.sketch.com/) and [Abstract](https://www.abstract.com/).
4. **Documentation of components.**  
We included descriptions and instructions for each component in Sketch (for designer's reference) and in [Storybook](https://storybook.js.org) (a React UI component explorer used by our front-end developers).

<figure>
  <img src="/images/ds-0.jpg" alt="Storybook">
  <br>
  <figcaption>Screenshot of Storybook.</figcaption>
</figure>

### Component architecture

The UI components of our system worked like building blocks; we categorized our components in different levels and each level builds off the one that precedes it. It’s an approach that borrowed heavily from [Atomic Design](http://bradfrost.com/blog/post/atomic-web-design/) principles. All the component library files were structured like this:
- **Primitives:** This included colors, gradients, patterns, and spacers. We thought about including here text styles, but we ended up managing them separately.<br><br>
  <figure>
  <div class="carousel" data-flickity='{ "imagesLoaded": true, "percentPosition": false }'>
    <img src="/images/ds-1.jpg" alt="Primitives: typography">
    <img src="/images/ds-2.jpg" alt="Primitives: primary colors">
    <img src="/images/ds-3.jpg" alt="Primitives: hand drawn patterns">
  </div>
  </figure><br>
- **Level 1 / Foundation:** The foundation level included components that can’t be broken down any further. These are very basic building blocks of our products. As such, they can’t contain nested components and overrides should be minimal. An example of foundational components are logos and avatars.<br><br>
  <figure>
  <div class="carousel" data-flickity='{ "imagesLoaded": true, "percentPosition": false }'>
    <img src="/images/ds-4.jpg" alt="L1: avatars">
    <img src="/images/ds-5.jpg" alt="L1: logos">
    <img src="/images/ds-6.jpg" alt="L1: icons">
  </div>
  </figure><br>
- **Level 2 / Lower-level blocks:** These were typically composed of a combination of primitives and level 1 components. Some UI elements included here are buttons and form elements.<br><br>
  <figure>
  <div class="carousel" data-flickity='{ "imagesLoaded": true, "percentPosition": false }'>
    <img src="/images/ds-7.jpg" alt="L2: alerts">
    <img src="/images/ds-8.jpg" alt="L2: buttons">
    <img src="/images/ds-9.jpg" alt="L2: forms">
    <img src="/images/ds-10.jpg" alt="L2: forms">
    <img src="/images/ds-11.jpg" alt="L2: navigation">
    <img src="/images/ds-12.jpg" alt="L2: navigation">
  </div>
  </figure><br>
- **Level 3 / Mid-level blocks:** Mid-level blocks were typically composed of a combination of primitives, level 1 and level 2 components. Modal windows, tables, and cards are all part of this level.<br><br>
  <figure>
  <div class="carousel" data-flickity='{ "imagesLoaded": true, "percentPosition": false }'>
    <img src="/images/ds-13.jpg" alt="L3: cards">
    <img src="/images/ds-14.jpg" alt="L3: cards">
    <img src="/images/ds-15.jpg" alt="L3: modal windows">
    <img src="/images/ds-16.jpg" alt="L3: tables">
  </div>
  </figure><br>
- **Level 4 / Full composition:** These elements were used mostly for demo purposes. They are full-screen compositions that include all other level components and primitives.

And we also had **separate text and layer styles**. We had text styles available in multiple weights, colors and alignments. The layer styles included predefined colors, gradients, form container states and button states. These all helped create more flexible components in Sketch.

### Naming conventions

It was important to put in place some naming conventions that reflected our component architecture. We ended up using this:

`Level / Type of component / Component name / State or Pieces`

And an example would be:

`L2/nav/breadcrumbs/_pieces/link`

Keeping a consistent naming across components is also important because Sketch uses this names in order to arrange them in menus and in order to display the right component overrides when you use these components. You can use these overrides to customize your components with different nested elements, making them a lot more powerful and flexible.

### Maintenance and updates

So once we had the first of our component libraries ready we had to create a protocol in order to add or modify these components. Keep in mind that modifying these components in the master library will affect any design file using this library. You could easily break things, this is kind of a big deal!

First of all, the designer needs to decide if a new component is necessary. Is this new component going to be reused? If the answer is no, you can detach the original Sketch symbol and call it a day. But if the new variation or pattern is likely to be reused, then it might be time to create a new component.

The new component should follow some rules:
- It needs to follow our naming conventions.
- It should use nested components when it’s possible. The designer should try to organize the layers in a hierarchical way so the overrides panel in Sketch makes sense, make the layer names semantic and remember that color and icon symbols are good helpers.
- It should be responsive so it can be resized without breaking it.

When the new component was ready, it’s time to share it with the team before it’s merged in the component library. We use Abstract for version control of our files and libraries and the workflow here is very similar to git: create a branch, add your new stuff, commit your changes, ask for feedback and if the symbol gets approved then merge your branch.

### Things I Learned

The most exciting part of this project was that we were not just documenting some UI components, we were creating a new workflow for an entire team. There was a lot of trial and error in the process and I found some Sketch bugs (setting resizing constraints in nested symbols is definitely tricky) but this first library was quickly adopted by the entire team and we ended up creating additional libraries for our consumer site, newsletters and wireframes.