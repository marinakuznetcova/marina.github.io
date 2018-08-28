---
title: Frontend dev SVG toolkit
---

So, imagine (or recall) you're a web developer. And you've got another PSD that you are to magically turn into a functioning interface. Among other cute stuff you see multiple icons, logos, animations - and you find out that all these nice pics are vector graphics.

*Note: vector graphics is continuously, endlessly, infinitely scalable - that is the main reason why you should do your best to keep this attribute, pass it into the web and so export all vector graphics in vector format, i. e. SVG.*

I am going to create kind of memo and list here a number of universal to-do things you can do with vector graphics in every other project. It needs slightly more time and deeper knowledge than to give up on users and all these modern technologies and just save each icon and logo as good old PNG. But I hope you're a true developer, curious and brave, ready to spend a bit more time and to know something new - at least for the sake of clean and beautiful Internet. But - let's finally cut to the chase!

### Save it carefully

First off, check if you can export a picture as SVG. Be careful and check the code itself by all means. Some editors (or some of their versions) simply sew up a typical raster image into the SVG tags in, say, base64 format. It does not become scalable and lightweight just because of the ".svg" extension. Speaking about Adobe Photoshop, if you can't export an image as SVG, you can try to "Export contents..." and save it as an AI file. And then you'll be likely to need some converter. I prefer trusted online services, so I'm going to hint you there is one like that: Online <a href="https://image.online-convert.com/convert-to-svg" target="_blank">SVG image converter</a>.

You can use Adobe Illustrator for this goal as well - if you have one installed on your machine.

### Crop the blank space

SVG pics often have some empty space around the image. I always just crop it to easily manage the picture's size. So you'll be able to get the image parameters directly from the PSD (or whatever format of a project you have) which shows you native size of the drawing itself and apply them to width and height in your markup and CSS. To crop SVG you can use any vector graphics editor, I use the free application called <a href="https://inkscape.org/en/" target="_blank">Inkscape</a>.

### Throw away the extra

Always look into the code of an image you get: it's likely to contain something to throw away (especially after graphics editors). This can be meta information no-one really needs on the web, lots of empty tags, unnecessary attributes influencing nothing... So you should always compress the SVG. There're many ways to do that including deleting all this stuff with your own hands, but I prefer a quicker and cleaner solution which is accessible online called <a href="https://jakearchibald.github.io/svgomg/" target="_blank">SVGOMG</a>.

Yep, usually it's a matter a few kilobytes, but in terms of SVG it can appear to be a half or 70% or even, in a bad case, 95% you save.

### What's next?

Now you have a nice lightweight vector image you can use on the web freely! But there're still some things to consider before pushing your SVG into an `img` tag. This is what I'm going to discuss with you in the [pt. II](/frontend-dev-svg-toolkit-pt-2).

*21 May 2018*

[home](/index)
