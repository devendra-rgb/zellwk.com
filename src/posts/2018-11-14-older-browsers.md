---
title: Supporting older browsers with Polyfills
layout: post
slug: older-browsers
newsletter: better-fed
tags:
  - best practice
  - best
description: "You don't have to worry much about supporting older browsers today. They've been decent ever since Internet Explorer 8 died. But the question remains: How should you go about supporting Internet Explorer 9 and other browsers?"
---

You don't have to worry much about supporting older browsers today. They've been decent ever since Internet Explorer 8 died.

But the question remains: How should you go about supporting Internet Explorer 9 and other browsers? In the first place, should you even be thinking about supporting Internet Explorer 9?

We'll look at a few things you'd want to consider.

<!-- more -->

<div class="jsCkClone" data-should-not-clone></div>

## Think features, not browsers

Let's say the world contains only two features and two browsers.

1. Browser A supports feature A but not feature B.
2. Browser B supports feature B but not feature A.

It's possible to detect what browsers support what features and act from there.

```js
if (Browser A) {
  // Code for A
}

if (Browser B) {
  // code for B
}
```

But what if there are more browsers? What if the world contains browsers C, D, and E? It gets hard to support the features you need if you're thinking about browsers.

There's a better way: You can check whether a feature exists. If it exists, use it. If not, provide fallback code.

The following block of code works from browser A to browser Z.

```js
if (feature A) {
  // Code if browser contains feature A
} else {
  // Code if browser doesn't contain feature A
}
```

And now you don't have to worry about browsers.

## Deciding whether to use a feature

Many people decide whether to use a feature depending on the number of browsers that support it. But as I argued above, **browsers don't matter.**

What matters is: Can you code the fallback for the feature easily? **If you can code the fallback easily, go ahead and use the feature.** If you can't code the fallback easily, don't use the feature.

## Deciding what browsers to support

You still need a cutoff. What browsers are you going to support? What browsers are you NOT going to support? If you don't want to support the browser, then it doesn't make sense for you to write fallback code for it.

My best answer is: Watch who is using your site. What browsers do they use? Follow accordingly.

Yes, there may be outliers who try to visit your website on Internet Explorer 6. But do have the time and energy to write extra code for a browser that almost no one uses?

Will your energy be better spent elsewhere?

## The level of support

I'd argue there are four levels of support:

1. Everything must look and work the same in all browsers
2. The site must look the same, but functionality can be different across browsers
3. Functionality must be the same, but looks can be different across browsers
4. Looks and functionality can both differ across browsers

What kind of support are you providing to the older browsers? Why?

## Other articles in this series

1. Part 1: This article
2. Part 2: [Supporting older browsers—Part 2: CSS][1]
3. Part 3: [Supporting older browsers—Part 3: JS][2]
4. Part 4: Why support older browsers? (To be released!)

## Wrapping up

Think about it.

1. Why are you trying to support the old browser you're trying to support?
2. What level of support are you giving?
3. It is worth the resources you've allocated?

In the following two articles, we'll look at supporting CSS and JavaScript features in older browsers. We'll also talk about what level of support you should provide.

[1]: /blog/older-browsers-css
[2]: /blog/older-browsers-js 'Supporting older browsers—Part 3: JS'
