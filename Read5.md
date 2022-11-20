# Images in HTML

In the beginning, the Web was just text, and it was really quite boring. Fortunately, it wasn't too long before the ability to embed images (and other more interesting types of content) inside web pages was added. There are other types of multimedia to consider, but it is logical to start with the humble \<img\> element, used to embed a simple image in a webpage. In this article we'll look at how to use it in depth, including the basics, annotating it with captions using \<figure\>, and detailing how it relates to **CSS** background images.

## How do we put an image on a webpage?

In order to put a simple image on a web page, we use the \<img\> element. This is a void element (meaning, it cannot have any child content and cannot have an end tag) that requires two attributes to be useful: `src` and `alt`. The `src` attribute contains a URL pointing to the image you want to embed in the page. As with the `href` attribute for \<a\> elements, the `src` attribute can be a relative **URL** or an absolute URL. Without a `src` attribute, an `img` element has no image to load.

### Alternative text

The next attribute we'll look at is `alt`. Its value is supposed to be a textual description of the image, for use in situations where the image cannot be seen/displayed or takes a long time to render because of a slow internet connection.

So, why would you ever see or need alt text? It can come in handy for a number of reasons:

- The user is visually impaired, and is using a **screen reader** to read the web out to them. In fact, having alt text available to describe images is useful to most users.
- The spelling of the file or path name might be wrong.
- The browser doesn't support the image type. Some people still use text-only browsers, such as **Lynx**, which displays the alt text of images.
- You may want to provide text for search engines to utilize; for example, search engines can match alt text with search queries.
- Users have turned off images to reduce data transfer volume and distractions. This is especially common on mobile phones, and in countries where bandwidth is limited or expensive.

### Width and height

You can use the width and height attributes to specify the width and height of your image.

This doesn't result in much difference to the display, under normal circumstances. But if the image isn't being displayed, for example, the user has just navigated to the page, and the image hasn't yet loaded, you'll notice the browser is leaving a space for the image to appear in.

### Image titles

As with **links**, you can also add title attributes to images, to provide further supporting information if needed.

However, this is not recommended — title has a number of accessibility problems, mainly based around the fact that screen reader support is very unpredictable and most browsers won't show it unless you are hovering with a mouse (so e.g. no access to keyboard users).

## Annotating images with figures and figure captions

HTML \<figure\> and \<figcaption\> elements. These are created for exactly this purpose: to provide a semantic container for figures, and to clearly link the figure to the caption.

The \<figcaption\> element tells browsers, and assistive technology that the caption describes the other content of the \<figure\> element.

A figure doesn't have to be an image. It is an independent unit of content that:

- Expresses your meaning in a compact, easy-to-grasp way.
- Could go in several places in the page's linear flow.
- Provides essential information supporting the main text.

## CSS background images

You can also use CSS to embed images into webpages.The CSS **background-image** property, and the other `background-*` properties, are used to control background image placement.
The resulting embedded image is arguably easier to position and control than HTML images. So why bother with HTML images? As hinted to above, CSS background images are for decoration only. If you just want to add something pretty to your page to enhance the visuals, this is fine. Though, such images have no semantic meaning at all. They can't have any text equivalents, are invisible to screen readers, and so on. This is where HTML images shine!

## To more information about HTML images, read [Images_in_HTML][1]

***

# Image file type and format guide

## Image file types

1- APNG (Animated Portable Network Graphics)

APNG is a file format first introduced by Mozilla which extends the **PNG** standard to add support for animated images. Conceptually similar to the animated GIF format which has been in use for decades, APNG is more capable in that it supports a variety of **color depths**, whereas animated GIF supports only 8-bit **indexed color**.

APNG is ideal for basic animations that do not need to synchronize to other activities or to a sound track, such as progress indicators, activity **throbbers**, and other animated sequences.

2- AVIF image

AV1 Image File Format (AVIF) is a powerful, open source, royalty-free file format that encodes AV1 bitstreams in the High Efficiency Image File Format (HEIF) container.

AV1 is a coding format that was originally designed for video transmission over the Internet. The format benefits from the significant advances in video encoding in recent years, and may potentially benefit from the associated support for hardware rendering. However it also has disadvantages for some cases, as video and image encoding have some different requirements.

3- BMP (Bitmap file)

The **BMP (Bitmap image)** file type is most prevalent on Windows computers, and is generally used only for special cases in web apps and content.

:warning: **Warning:** You should typically avoid using BMP files for web site content. The most common form of BMP file represents the data as an uncompressed raster image, resulting in large file sizes compared to png or jpg image types. More efficient BMP formats exist but are not widely used, and rarely supported in web browsers.

4- GIF (Graphics Interchange Format)

In 1987, the CompuServe online service provider introduced the **GIF (Graphics Interchange Format)** image file format to provide a compressed graphics format that all members of their service would be able to use. GIF uses the **Lempel-Ziv-Welch (LZW)** algorithm to losslessly compress 8-bit indexed color graphics. GIF was one of the first two graphics formats supported by **HTML**, along with **XBM**.

Each pixel in a GIF is represented by a single 8-bit value serving as an index into a palette of 24-bit colors (8 bits each of red, green, and blue). The length of a color table is always a power of 2 (that is, each palette has 2, 4, 8, 16, 32, 64, or 256 entries). To simulate more than 255 or 256 colors, **dithering** is generally used. It is **technically possible** to tile multiple image blocks, each with its own color palette, to create truecolor images, but in practice this is rarely done.

GIF is a good choice for simple images and animations, although converting full color images to GIF can result in unsatisfactory dithering.

5- ICO (Microsoft Windows icon)

The ICO (Microsoft Windows icon) file format was designed by Microsoft for desktop icons of Windows systems. However, early versions of Internet Explorer introduced the ability for a web site to provide a ICO file named `favicon.ico` in a web site's root directory to specify a **favicon** — an icon to be displayed in the Favorites menu, and other places where an iconic representation of the site would be useful.

:warning: **Warning:** ICO files should not be used in web content. Additionally, their use for favicons has subsided in favor of using a **PNG** file and the \<link\> element.

6- JPEG (Joint Photographic Experts Group image)

The **JPEG** (typically pronounced "**jay-peg**") image format is currently the most widely used lossy compression format for still images. It's particularly useful for photographs; applying lossy compression to content requiring sharpness, like diagrams or charts, can produce unsatisfactory results.

JPEG is actually a data format for compressed photos, rather than a file type. The JFIF (**J**PEG **F**ile **I**nterchange **F**ormat) specification describes the format of the files we think of as "JPEG" images.

7- PNG (Portable Network Graphics)

The **PNG** (pronounced "**ping**") image format uses lossless compression, while supporting higher color depths than **GIF** and being more efficient, as well as featuring full alpha transparency support.

PNG is widely supported, with all major browsers offering full support for its features. Internet Explorer, which introduced PNG support in versions 4–5, did not fully support it until IE 9, and had many infamous bugs for many of the intervening years, including in the once-omnipresent Internet Explorer 6. This slowed PNG adoption, but it is now commonly used, especially when precise reproduction of the source image is needed.

8- SVG (Scalable Vector Graphics)

SVG is an **XML**-based **vector graphics** format that specifies the contents of an image as a set of drawing commands that create shapes, lines, apply colors, filters, and so forth. SVG files are ideal for diagrams, icons, and other images which can be accurately drawn at any size. As such, SVG is popular for user interface elements in modern Web design.

SVG files are text files containing source code that, when interpreted, draws the desired image.

SVG can be used in web content in two ways:

- You can directly write the \<svg\> element within the HTML, containing **SVG elements** to draw the image.

- You can display an SVG image anywhere you can use any of the other image types, including with the \<img\> and \<picture\> elements, the **background-image** CSS property, and so forth.

SVG is an ideal choice for images which can be represented using a series of drawing commands, especially if the size at which the image will be rendered is unknown or may vary, since SVG will smoothly scale to the desired size. It's not generally useful for strictly bitmap or photographic images, although it is possible to include bitmap images within an SVG.

9- TIFF (Tagged Image File Format)

**TIFF** is a raster graphics file format which was created to store scanned photos, although it can be any kind of image. It is a somewhat "heavy" format, in that TIFF files have a tendency to be larger than images in other formats. This is because of the metadata often included, as well as the fact that most TIFF images are either uncompressed or use compression algorithms that still leave fairly large files after compression.

TIFF supports a variety of color spaces, not just RGB. These include CMYK, YCbCr, and others, making TIFF a good choice for storing images intended for print, film, or television media.

Long ago, some browsers supported TIFF images in web content; today, however, you need to use special libraries or browser add-ons to do so. As such, TIFF files are not useful within the context of web content, but it's common to provide downloadable TIFF files when distributing photos and other artwork intended for precision editing or printing.

10- WebP image

WebP supports lossy compression via predictive coding based on the VP8 video codec, and lossless compression that uses substitutions for repeating data. Lossy WebP images average 25–35% smaller than JPEG images of visually similar compression levels. Lossless WebP images are typically 26% smaller than the same images in PNG format.

WebP now has broad support in the latest versions of major web browsers, although it does not have deep historical support. Provide a fallback in either **JPEG** or **PNG** format, such as with **the \<picture\> element**.

11- XBM (X Window System Bitmap file)

XBM (X Bitmap) files were the first to be supported on the Web, but are no longer used and should be avoided, as their format has potential security concerns. Modern browsers have not supported XBM files in many years, but when dealing with older content, you may find some still around.

## Choosing an image format

### Photographs

Photographs typically fare well with lossy compression (depending on the encoder's configuration). This makes **JPEG** and **WebP** good choices for photographs, with JPEG being more compatible but WebP perhaps offering better compression. To maximize quality and minimize download time, consider providing both **using a fallback** with WebP as the first choice and JPEG as the second. Otherwise, JPEG is the safe choice for compatibility.

|  Best choice                       |  Fallback                       |
|------------------------------------|---------------------------------|
| WebP or JPEG                       | JPEG                            |

### Icons

For smaller images such as icons, use a lossless format to avoid loss of detail in a size-constrained image. While lossless WebP is ideal for this purpose, support is not widespread yet, so PNG is a better choice unless you offer a **fallback**. If your image contains fewer than 256 colors, GIF is an option, although PNG often compresses even smaller with its indexed compression option (PNG-8).

If the icon can be represented using vector graphics, consider **SVG**, since it scales across various resolutions and sizes, so it's perfect for responsive design. Although SVG support is good, it may be worth offering a PNG fallback for older browsers.

|  Best choice                       |  Fallback                       |
|------------------------------------|---------------------------------|
| SVG, Lossless WebP, or PNG         | PNG                             |

### Screenshots

Unless you're willing to compromise on quality, you should use a lossless format for screenshots. This is particularly important if there's any text in your screenshot, as text easily becomes fuzzy and unclear under lossy compression.

PNG is probably your best bet, but lossless WebP is arguably going to be better compressed.

|Best choice                       |  Fallback                       |
|------------------------------------|---------------------------------|
| Lossless WebP or PNG;<br> JPEG if compression artifacts aren't a concern| PNG or JPEG;<br> GIF for screenshots with low color counts|

### Diagrams, drawings, and charts

For any image that can be represented using vector graphics, SVG is the best choice. Otherwise, you should use a lossless format like PNG. If you do choose a lossy format, such as JPEG or lossy WebP, carefully weigh the compression level to avoid causing text or other shapes to become fuzzy or unclear.

|  Best choice                       |  Fallback                       |
|------------------------------------|---------------------------------|
| SVG                                | PNG                             |

## Providing image fallbacks

While the standard HTML \<img\> element doesn't support compatibility fallbacks for images, the \<picture\> element does. `<picture>` is used as a wrapper for a number of \<source\> elements, each specifying a version of the image in a different format or under different **media conditions**, as well as an `<img>` element which defines where to display the image and the fallback to the default or "most compatible" version.

You can specify as many \<source\>s as you wish, though typically 2 or 3 is all you need.

## You can read more with more details in this [Image_Types][2]

***

# Applying color to HTML elements using CSS

## Things that can have color

At the element level, everything in HTML can have color applied to it. Instead, let's look at things in terms of the kinds of things that are drawn in the elements, such as text and borders and so forth. For each, we'll see a list of the CSS properties that apply color to them.

At a fundamental level, the **color** property defines the foreground color of an HTML element's content and the background-color property defines the element's **background color**. These can be used on just about any element.

### Text

Whenever an element is rendered, these properties are used to determine the color of the text, its background, and any decorations on the text.

1- **color**

The color to use when drawing the text and any **text decorations** (such as the addition of under- or overlines, strike-through lines, and so forth.

2- **background-color**

The text's background color.

3- **text-shadow**

Configures a shadow effect to apply to text. Among the options for the shadow is the shadow's base color.

4- **text-decoration-color**

By default, text decorations (such as underlines, strikethroughs, etc.) use the `color` property as their colors. However, you can override that behavior and use a different color for them with the `text-decoration-color` property.

5- **caret-color**

The color to use when drawing the **caret** (sometimes referred to as the text input cursor) within the element. This is only useful in elements that are editable, such as \<input\> and \<textarea\> or elements whose HTML **contenteditable** attribute is set.

## How to describe a color

### Keywords

A set of standard color names have been defined, letting you use these keywords instead of numeric representations of colors if you choose to do so and there's a keyword representing the exact color you want to use.

### RGB values

#### Hexadecimal string notation

Hexadecimal string notation represents a color using hexadecimal digits to represent each of the color components (red, green, and blue). It may also include a fourth component: the alpha channel (or opacity). Each color component can be represented as a number between 0 and 255 (0x00 and 0xFF) or, optionally, as a number between 0 and 15 (0x0 and 0xF). All components must be specified using the same number of digits. If you use the single-digit notation, the final color is computed by using each component's digit twice; that is, `"#D"` becomes `"#DD"` when drawing.

A color in hexadecimal string notation always begins with the character `"#"`. After that come the hexadecimal digits of the color code. The string is case-insensitive.

#### RGB functional notation

GB (Red/Green/Blue) functional notation, like hexadecimal string notation, represents colors using their red, green, and blue components (as well as, optionally, an alpha channel component for opacity). However, instead of using a string, the color is defined using the CSS function **rgb()**. This function accepts as its input parameters the values of the red, green, and blue components and an optional fourth parameter, the value for the alpha channel.

### HSL functional notation

Designers and artists often prefer to work using the **HSL** (Hue/Saturation/Luminosity) color method. On the web, HSL colors are represented using HSL functional notation. The `hsl()` CSS function is very similar to the `rgb()` function in usage otherwise.

The value of the hue (H) component of an HSL color is an angle from red around through yellow, green, cyan, blue, and magenta (ending up back at red again at 360°) that identifies what the base color is. The value can be specified in any \<angle\> unit supported by CSS, including degrees (`deg`), radians (`rad`), gradians (`grad`), or turns (`turn`). But this doesn't control how vivid or dull, or how bright or dark the color is.

The saturation (S) component of the color specifies what percentage of the final color is comprised of the specified hue. The rest is defined by the grey level provided by the luminance (L) component.

### HWB functional notation

Much like the HSL functional notation above, the **hwb()** function uses the same hue value. But instead of lightness and saturation you specify whiteness and blackness values in percentages. Values are **not** separated with a comma and an optional alpha value can be included (it must be preceded by a forward slash `/`).

## Using color wisely

Making the right choices when selecting colors when designing a website can be a tricky process, especially if you aren't well-grounded in art, design, or at least basic color theory. The wrong color choice can render your site unattractive, or even worse, leave the content unreadable due to problems with contrast or conflicting colors. Worse still, if using the wrong colors can result in your content being outright unusable by people with certain vision problems, particularly color blindness.

### Finding the right colors

Coming up with just the right colors can be tricky, especially without training in art or design. Fortunately, there are tools available that can help you. While they can't replace having a good designer helping you make these decisions, they can definitely get you started.

#### 1- Base color

#### 2- Fleshing out the palette

#### 3- Color theory resources

#### 4- Color and accessibility

#### 5- Color, backgrounds, contrast, and printing

## And there are way more things you have to read about, so for your start, look at this source that I took my acticle from, see [Applying_color][3]

***

# Fundamental text and font styling

## What is involved in styling text in CSS?

The CSS properties used to style text generally fall into two categories, which we'll look at separately in this article:

- **Font styles**: Properties that affect a text's font, e.g., which font gets applied, its size, and whether it's bold, italic, etc.

- **Text layout styles**: Properties that affect the spacing and other layout features of the text, allowing manipulation of, for example, the space between lines and letters, and how the text is aligned within the content box.

## Fonts

Let's move straight on to look at properties for styling fonts.

### Color

The **color** property sets the color of the foreground content of the selected elements, which is usually the text, but can also include a couple of other things, such as an underline or overline placed on text using the **text-decoration** property.

### Font families

To set a different font for your text, you use the **font-family** property — this allows you to specify a font (or list of fonts) for the browser to apply to the selected elements. The browser will only apply a font if it is available on the machine the website is being accessed on; if not, it will just use a browser **default font**.

### Font size

Font size (set with the font-size property) can take values measured in most of these units (and others, such as percentages); however, the most common units you'll use to size text are:

- `px` (pixels): The number of pixels high you want the text to be. This is an absolute unit — it results in the same final computed value for the font on the page in pretty much any situation.

- `em`s: 1 `em` is equal to the font size set on the parent element of the current element we are styling (more specifically, the width of a capital letter M contained inside the parent element). This can become tricky to work out if you have a lot of nested elements with different font sizes set, but it is doable, as you'll see below. Why bother? It is quite natural once you get used to it, and you can use `em` to size everything, not just text. You can have an entire website sized using `em`, which makes maintenance easy.

- `rem`s: These work just like `em`, except that 1 `rem` is equal to the font size set on the root element of the document (i.e. \<html\>), not the parent element. This makes doing the maths to work out your font sizes much easier, although if you want to support really old browsers, you might struggle — `rem` is not supported in Internet Explorer 8 and below.

### Font style, font weight, text transform, and text decoration

CSS provides four common properties to alter the visual weight/emphasis of text:

- **font-style**
- **font-weight**
- **text-transform**
- **text-decoration**

### Text drop shadows

You can apply drop shadows to your text using the text-shadow property. This takes up to four values, as shown in the example below:

You can apply drop shadows to your text using the text-shadow property. This takes up to four values, as shown in the example below:

    text-shadow: 4px 4px 5px red;

1. The horizontal offset of the shadow from the original text — this can take most available CSS length and size units, but you'll most commonly use `px`; positive values move the shadow right, and negative values left. This value has to be included.

2. he vertical offset of the shadow from the original text. This behaves similarly to the horizontal offset, except that it moves the shadow up/down, not left/right. This value has to be included.

3. The blur radius: a higher value means the shadow is dispersed more widely. If this value is not included, it defaults to 0, which means no blur.

4. The base color of the shadow, which can take any **CSS color unit**. If not included, it defaults to `currentcolor`.

## Text layout

With basic font properties out of the way, let's have a look at properties we can use to affect text layout.

### Text alignment

The text-align property is used to control how text is aligned within its containing content box. The available values are listed below. They work in pretty much the same way as they do in a regular word processor application.

### Line height

The **line-height** property sets the height of each line of text. This property can not only take most **length and size units**, but can also take a unitless value, which acts as a multiplier and is generally considered the best option. With a unitless value, the **font-size** gets multiplied and results in the `line-height`. Body text generally looks nicer and is easier to read when the lines are spaced apart. The recommended line height is around 1.5 – 2 (double spaced).

### Letter and word spacing

The letter-spacing and word-spacing properties allow you to set the spacing between letters and words in your text. You won't use these very often, but might find a use for them to obtain a specific look, or to improve the legibility of a particularly dense font. They can take most **length and size units**.

## These properties and more are explained in [MDN Styling HTML Text Elements][4]

[1]: <https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML>
[2]: <https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types>
[3]: <https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Colors/Applying_color>
[4]: <https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals>
