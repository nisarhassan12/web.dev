---
layout: post
title: Manually check all custom interactive controls are keyboard focusable
description: |
  Learn about custom-controls-labels audit.
web_lighthouse:
  - custom-controls-labels
---

Custom interactive controls should be focusable.
If you use JavaScript to turn a `<div`> into a fancy dropdown,
it won't automatically be inserted into the tab order.
You need to manually check that all custom controls are keyboard focusable.
See also [Keyboard access fundamentals](/keyboard-access).

## How to manually test

To test that the custom control is focusable,
press the `TAB` key to navigate through the site:

<div class="glitch-embed-wrap" style="height: 346px; width: 100%;">
  <iframe
    src="https://glitch.com/embed/#!/embed/tabindex-zero?path=index.html&previewSize=100&attributionHidden=true"
    alt="tabindex-zero on Glitch"
    style="height: 100%; width: 100%; border: 0;">
  </iframe>
</div>

Are you able to reach all of the interactive controls on the page?
If not, you may need to use `tabindex` to improve the focusability of those controls.
See also [Control focus with tabindex](/control-focus-with-tabindex).

## How to fix

To make a custom control focusable,
insert the custom control element into the natural tab order using `tabindex="0"`.
For example:

```html
<div tabindex="0">Focus me with the TAB key</div>
```

## Why this matters

For users who either cannot or choose not to use a mouse,
keyboard navigation is the primary means of reaching everything on a screen.
Good keyboarding experiences depend on a logical tab order and easily discernable focus styles.
If a keyboard user can't see what's focused, they have no way of interacting with the page.

Learn more in [How to do an Accessibility Review](https://developers.google.com/web/fundamentals/accessibility/how-to-review#try_it_with_a_screen_reader).

## More information

- [Check all custom controls are keyboard focusable audit source](https://github.com/GoogleChrome/lighthouse/blob/master/lighthouse-core/audits/accessibility/manual/custom-controls-labels.js)
- [Ensure `tabindex` attribute values are not greater than 0](/tabindex)
