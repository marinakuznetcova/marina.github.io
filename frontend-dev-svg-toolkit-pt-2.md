[&larr; home](/)

---
title: Frontend dev SVG toolkit. Pt.&nbsp;II
---

I assume you've already got a pretty lightweight SVG with the code which is as clean as possible and pleases the eye. If you haven't&mdash;feel free to read [the previous part of the article](/frontend-dev-svg-toolkit).

So, what do you want to do with these fresh-baked SVG pics? There are few ways you can embed vector images to your web page or app. Not to be confused with the methods of using SVG on the web at once I'd recommend you to ask yourself several questions before getting down to work.

### 1. Is the image interactive?

Interactive SVG is a fairly often use case as it almost always represents an icon or a logo&mdash;that is more than likely clickable. Sure thing, an interactive element of any user interface has to hint somehow about its interactivity. It can either simply change its color on hover or, for example, show-hide its part on click. Using PNG or any other raster format would force you to prepare two or more different images, upload all of them to your hosting and then use one for a default state, another for a hover, one more for a focus and maybe even the forth one for an active state. Sounds horrible, eh?

Meanwhile with SVG you would need the only one file! You're able to manage fill, stroke or visibility of the whole image or its parts. Just you would need to inline the SVG code right into the markup. So, is your image interactive?

*Yes:* inline SVG code into the markup.

*No:* you are free to use a simple img tag or background-image CSS property.

### 2. Is the image a part of content, or a part of design?

Design parts can be used as a background whereas content images should become individual elements in the markup. It's necessary for screen readers and search engines to "understand" all significant details of the content including pictures with filled `alt` attributes.

To tell one point from the other you can read [quite a detailed article here](https://pawelgrzybek.com/image-tag-vs-background-property/). SVG pictures rarely appear to be parts of content&mdash;unlike photos which are sometimes hard to refer to either content or design.

*Content:* insert an image into the markup using img tag or the SVG code itself.

*Design:* you can use background-image property.

### 3. Are there many pictures you're going to insert into the HTML as code?

If there would be much SVG code in the HTML, the markup can easily become tangled, bulky and difficult to read. So first of all, if you are going to use, say, 5 or more pictures inside your markup, you should make a sprite. It's more handy and safe to do that automatically: [here is a Gulp tool](https://github.com/marinakuznetcova/sprite) to help you out.

*Yes (5 or more):* you'd better gather a sprite.

*No (4 or less):* you can just insert the code where you need it.

### 4. Do you need to support old browsers (i.e. IE)?

Internet Explorer does not know what SVG is and seems to simply ignore it. Anyway it doesn't display anything unless you help it a little bit. There is a polyfill called [picturefill](http://scottjehl.github.io/picturefill/). It's a .js file which takes only 23KB, but it does a huge work: makes IE display SVG properly.

One more thing concerning Internet Explorer: if you're going to use a sprite in a separate file, don't. You'll have to insert the whole code of the sprite into the markup. Otherwise you won't be able to manage SVG properties such as fill in some old browsers. Not to make your HTML file look awkward at the development stage, use automation (such as Gulp [posthtml-include](https://www.npmjs.com/package/posthtml-include) plugin) in your project to paste the sprite code after you're done with your markup.

*Yes:* add and link the picturefill.js file and insert the whole sprite code right into the markup.

*No:* enjoy your life.

### 5. Should your code be as independent as possible?

If you don't want to use or don't have a hosting to store an image, you can inline the SVG code into background-image CSS property. `data:image` syntax would help: recall base64 format. This way to use vector graphics lets a developer not to think about URLs and to reduce the number of HTTP requests. But! There is a negative side: a property like that is pretty "expensive" for a browser and would take much time to be processed. So be careful with this syntax and use it when only you really-really need it.

*Yes:* you could inline SVG code into background-image CSS property, but be careful.

*No:* use a method you like or need according to previous points.

### 6. Don't forget the accessibility!

I know, I know, it's not a question. But it's not something you should ask yourself or someone else about or doubt whether you need it or not. It's what every developer has to do, no matter if there is such a request or not.

All you need to make SVG accessible is to add to its opening tag an ARIA attribute and put a title right after it. Then just link them with the same unique ID to get something like this:

```html
<svg aria-labelledby=“unique-id”>
  <title id=“unique-id”>
    Some text describing the image
  </title>
  <!-- inner SVG code -->
</svg>
```

As simple as that!


*28 May 2018*

[&larr; home](/)
