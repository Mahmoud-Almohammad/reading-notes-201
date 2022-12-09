# Video and audio content

### The \<video\> element

The \<video\> element allows you to embed a video very easily. A really simple example looks like this:

    <video src="rabbit320.webm" controls>
      <p>
        Your browser doesn't support HTML video. Here is a
        <a href="rabbit320.webm">link to the video</a> instead.
      </p>
    </video>

The features of note are:

**`src`**

In the same way as for the \<img\> element, the `src` (source) attribute contains a path to the video you want to embed. It works in exactly the same way.

**`controls`**

Users must be able to control video and audio playback (it's especially critical for people who have **epilepsy**.) You must either use the controls attribute to include the browser's own control interface, or build your interface using the appropriate **JavaScript API**. At a minimum, the interface must include a way to start and stop the media, and to adjust the volume.

The paragraph inside the \<video\> tags

This is called **fallback content** — this will be displayed if the browser accessing the page doesn't support the \<video\> element, allowing us to provide a fallback for older browsers. This can be anything you like; in this case, we've provided a direct link to the video file, so the user can at least access it some way regardless of what browser they are using.

## Using multiple source formats to improve compatibility

There's a problem with the above example. It is possible that the video might not play for you, because different browsers support different video (and audio) formats. Fortunately, there are things you can do to help prevent this from being an issue.

### Contents of a media file

First, let's go through the terminology quickly. Formats like MP3, MP4 and WebM are called **container formats**. They define a structure in which the audio and/or video tracks that make up the media are stored, along with metadata describing the media, what codecs are used to encode its channels, and so forth.

A WebM file containing a movie which has a main video track and one alternate angle track, plus audio for both English and Spanish, in addition to audio for an English commentary track can be conceptualized as shown in the diagram below. Also included are text tracks containing closed captions for the feature film, Spanish subtitles for the film, and English captions for the commentary.

The audio and video tracks within the container hold data in the appropriate format for the codec used to encode that media. Different formats are used for audio tracks versus video tracks. Each audio track is encoded using an **audio codec**, while video tracks are encoded using (as you probably have guessed) a **video codec**. As we talked about before, different browsers support different video and audio formats, and different container formats (like MP3, MP4, and WebM, which in turn can contain different types of video and audio).

One additional thing to keep in mind: mobile browsers may support additional formats not supported by their desktop equivalents, just like they may not support all the same formats the desktop version does. On top of that, both desktop and mobile browsers may be designed to offload handling of media playback (either for all media or only for specific types it can't handle internally). This means media support is partly dependent on what software the user has installed.

    <video controls>
    <source src="rabbit320.mp4" type="video/mp4" />
    <source src="rabbit320.webm" type="video/webm" />
    <p>
        Your browser doesn't support this video. Here is a
        <a href="rabbit320.mp4">link to the video</a> instead.
    </p>
    </video>

Here we've taken the `src` attribute out of the actual \<video\> tag, and instead included separate \<source\> elements that point to their own sources. In this case the browser will go through the \<source\> elements and play the first one that it has the codec to support. Including WebM and MP4 sources should be enough to play your video on most platforms and browsers these days.

Each `<source>` element also has a **type** attribute. This is optional, but it is advised that you include it. The `type` attribute contains the **MIME type** of the file specified by the `<source>`, and browsers can use the type to immediately skip videos they don't understand. If `type` isn't included, browsers will load and try to play each file until they find one that works, which obviously takes time and is an unnecessary use of resources.

### Other \<video\> features

you can find the other feature for \<vedio\> element [in this article][1]

### The \<audio\> element

The \<audio\> element works just like the \<video\> element, with a few small differences as outlined below. A typical example might look like so:

    <audio controls>
    <source src="viper.mp3" type="audio/mp3" />
    <source src="viper.ogg" type="audio/ogg" />
    <p>
        Your browser doesn't support this audio file. Here is a
        <a href="viper.mp3">link to the audio</a> instead.
    </p>
    </audio>

This takes up less space than a video player, as there is no visual component — you just need to display controls to play the audio. Other differences from HTML video are as follows:

- The \<audio\> element doesn't support the `width`/`height` attributes — again, there is no visual component, so there is nothing to assign a width or height to.
- It also doesn't support the `poster` attribute — again, no visual component.

## Displaying video text tracks

Now we'll discuss a slightly more advanced concept that is really useful to know about. Many people can't or don't want to hear the audio/video content they find on the Web, at least at certain times. For example:

- Many people have auditory impairments (such as being hard of hearing or deaf) so can't hear the audio clearly if at all.

- Others may not be able to hear the audio because they are in noisy environments (like a crowded bar when a sports game is being shown).

- Similarly, in environments where having the audio playing would be a distraction or disruption (such as in a library or when a partner is trying to sleep), having captions can be very useful.

- People who don't speak the language of the video might want a text transcript or even translation to help them understand the media content.

Wouldn't it be nice to be able to provide these people with a transcript of the words being spoken in the audio/video? Well, thanks to HTML video, you can. To do so we use the **WebVTT** file format and the \<track\> element.

To get this displayed along with the HTML media playback, you need to:

1. Save it as a `.vtt` file in a sensible place.
2. Link to the `.vtt` file with the \<track\> element. `<track>` should be placed within `<audio>` or `<video>`, but after all `<source>` elements. Use the 
**kind** attribute to specify whether the cues are `subtitles`, `captions`, or `descriptions`. Further, use **srclang** to tell the browser what language you have written the subtitles in. Finally, add **label** to help readers identify the language they are searching for.

Here's an example:

    <video controls>
    <source src="example.mp4" type="video/mp4" />
    <source src="example.webm" type="video/webm" />
    <track kind="subtitles" src="subtitles_es.vtt" srclang="es" label="Spanish" />
    </video>

This will result in a video that has subtitles displayed, kind of like this:

![result](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content/video-player-with-captions.png)

## For more details about \<video\> and \<audio\> elements, read [this article][2]

***

# A Complete Guide to CSS Grid

## Properties for the Parent (Grid Container)

1. display

Defines the element as a grid container and establishes a new grid formatting context for its contents.

Values:

- **grid** – generates a block-level grid
- **inline-grid** – generates an inline-level grid
 
    .container {
    display: grid | inline-grid;
    }

2. grid-template-columns / grid-template-rows

Defines the columns and rows of the grid with a space-separated list of values. The values represent the track size, and the space between them represents the grid line.

3. grid-template-areas

Defines a grid template by referencing the names of the grid areas which are specified with the `grid-area` property. Repeating the name of a grid area causes the content to span those cells. A period signifies an empty cell. The syntax itself provides a visualization of the structure of the grid.

Values:

- \<grid-area-name\> – the name of a grid area specified with `grid-area`
- **.** – a period signifies an empty grid cell
- **none** – no grid areas are defined

4. column-gap /
row-gap /
grid-column-gap /
grid-row-gap

Specifies the size of the grid lines. You can think of it like setting the width of the gutters between the columns/rows.

Values:

- \<line-size\> – a length value

Example:

    .container {
    grid-template-columns: 100px 50px 100px;
    grid-template-rows: 80px auto 80px; 
    column-gap: 10px;
    row-gap: 15px;
    }

![example](https://css-tricks.com/wp-content/uploads/2018/11/dddgrid-gap.svg)

5. justify-items

Aligns grid items along the inline (row) axis (as opposed to `align-items` which aligns along the block (column) axis). This value applies to all grid items inside the container.

Values:

- **start** – aligns items to be flush with the start edge of their cell

- **end** – aligns items to be flush with the end edge of their cell

- **center** – aligns items in the center of their cell

- **stretch** – fills the whole width of the cell (this is the default)

6. align-items

Aligns grid items along the block (column) axis (as opposed to `justify-items` which aligns along the inline (row) axis). This value applies to all grid items inside the container.

Values:

The same as justify-items but there is another value which is:

- **baseline** – align items **along text baseline**. There are modifiers to baseline — first baseline and last baseline which will use the baseline from the first or last line in the case of multi-line text.

## Properties for the Children (Grid Items)

1. grid-column-start /
grid-column-end /
grid-row-start /
grid-row-end

Determines a grid item’s location within the grid by referring to specific grid lines. grid-column-start/grid-row-start is the line where the item begins, and grid-column-end/grid-row-end is the line where the item ends.

Values:

- **\<line\>** – can be a number to refer to a numbered grid line, or a name to refer to a named grid line

- **span \<number\>** – the item will span across the provided number of grid tracks

- **span \<name\>** – the item will span across until it hits the next line with the provided name

- **auto** – indicates auto-placement, an automatic span, or a default span of one

2. grid-column /
grid-row

Shorthand for `grid-column-start` + `grid-column-end`, and `grid-row-start` + `grid-row-end`, respectively.

3. grid-area

Gives an item a name so that it can be referenced by a template created with the **grid-template-areas** property. Alternatively, this property can be used as an even shorter shorthand for `grid-row-start` + `grid-column-start` + `grid-row-end` + `grid-column-end`.

Values:

- **\<name\>** – a name of your choosing
- **\<row-start\>** / **\<column-start\>** / **\<row-end\>** / **\<column-end\>** – can be numbers or named lines

4. justify-self

Aligns a grid item inside a cell along the inline (row) axis (as opposed to `align-self` which aligns along the block (column) axis). This value applies to a grid item inside a single cell.

5. align-self

Aligns a grid item inside a cell along the block (column) axis (as opposed to `justify-self` which aligns along the inline (row) axis). This value applies to the content inside a single grid item.

Values for both:

- **start** – aligns the grid item to be flush with the start edge of the cell

- **end** – aligns the grid item to be flush with the end edge of the cell

- **center** – aligns the grid item in the center of the cell

- **stretch** – fills the whole width of the cell (this is the default)

## And there is even more! for full article about **grid** here is the [link][3]

***

# Responsive images

## Why responsive images?

Let's examine a typical scenario. A typical website may contain a header image and some content images below the header. The header image will likely span the whole of the width of the header, and the content image will fit somewhere inside the content column. Here's a simple example:

![example](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images/picture-element-wide.png)

However, issues arise when you start to view the site on a narrow screen device. The header below looks OK, but it's starting to take up a lot of the screen height for a mobile device. And at this size, it is difficult to see faces of the two people within the first content image.

![example](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images/non-responsive-narrow.png)

An improvement would be to display a cropped version of the image which displays the important details of the image when the site is viewed on a narrow screen. A second cropped image could be displayed for a medium-width screen device, like a tablet. The general problem whereby you want to serve different cropped images in that way, for various layouts, is commonly known as the **art direction problem**.

In addition, there is no need to embed such large images on the page if it is being viewed on a mobile screen. And conversely, a small **raster image** starts to look grainy when displayed larger than its original size (a raster image is a set number of pixels wide and a set number of pixels tall. This is called the **resolution switching problem**.

Conversely, it is unnecessary to display a large image on a screen significantly smaller than the size it was meant for. Doing so can waste bandwidth; in particular, mobile users don't want to waste bandwidth by downloading a large image intended for desktop users, when a small image would do for their device. Ideally, multiple resolutions would be made available to the user's web browser. The browser could then determine the optimal resolution to load based on the screen size of the user's device.

To make things more complicated, some devices have high resolution screens that need larger images than you might expect to display nicely. This is essentially the same problem, but in a slightly different context.

You might think that vector images would solve these problems, and they do to a certain degree — they are small in file size and scale well, and you should use them wherever possible. However, they aren't suitable for all image types. Vector images are great for simple graphics, patterns, interface elements, etc., but it starts to get very complex to create a vector-based image with the kind of detail that you'd find in say, a photo. Raster image formats such as JPEGs are more suited to the kind of images we see in the above example.

This kind of problem didn't exist when the web first existed, in the early to mid 90s — back then the only devices in existence to browse the Web were desktops and laptops, so browser engineers and spec writers didn't even think to implement solutions. Responsive image technologies were implemented recently to solve the problems indicated above by letting you offer the browser several image files, either all showing the same thing but containing different numbers of pixels (resolution switching), or different images suitable for different space allocations (art direction).

## How do you create responsive images?

### Resolution switching: Different sizes

So, what is the problem that we want to solve with resolution switching? We want to display identical image content, just larger or smaller depending on the device — this is the situation we have with the second content image in our example. The standard \<img\> element traditionally only lets you point the browser to a single source file:

    <img src="elva-fairy-800w.jpg" alt="Elva dressed as a fairy" />

We can however use two attributes — srcset and sizes — to provide several additional source images along with hints to help the browser pick the right one.

    <img
    srcset="elva-fairy-480w.jpg 480w, elva-fairy-800w.jpg 800w"
    sizes="(max-width: 600px) 480px,
            800px"
    src="elva-fairy-800w.jpg"
    alt="Elva dressed as a fairy" />

**srcset** defines the set of images we will allow the browser to choose between, and what size each image is. Each set of image information is separated from the previous one by a comma. For each one, we write:

1. An **image filename** (elva-fairy-480w.jpg)
2. A space
3. The image's **intrinsic width in pixels** (`480w`) — note that this uses the w unit, not px as you might expect. An image's **intrinsic size** is its real size, which can be found by inspecting the image file on your computer.

**`sizes`** defines a set of media conditions (e.g. screen widths) and indicates what image size would be best to choose, when certain media conditions are true — these are the hints we talked about earlier. In this case, before each comma we write:

1. A **media condition** (`(max-width:600px)`) — a media condition describes a possible state that the screen can be in. In this case, we are saying "when the viewport width is 600 pixels or less".
2. A space
3. The **width of the slot** the image will fill when the media condition is true (`480px`)

### Art direction

To recap, the **art direction problem** involves wanting to change the image displayed to suit different image display sizes. For example, a web page includes a large landscape shot with a person in the middle when viewed on a desktop browser. When viewed on a mobile browser, that same image is shrunk down, making the person in the image very small and hard to see. It would probably be better to show a smaller, portrait image on mobile, which zooms in on the person. The \<picture\> element allows us to implement just this kind of solution.

Like \<video\> and \<audio\>, the `<picture>` element is a wrapper containing several \<source\> elements that provide different sources for the browser to choose from, followed by the all-important \<img\> element.

    <picture>
    <source media="(max-width: 799px)" srcset="elva-480w-close-portrait.jpg" />
    <source media="(min-width: 800px)" srcset="elva-800w.jpg" />
    <img src="elva-800w.jpg" alt="Chris standing up holding his daughter Elva" />
    </picture>

- The `<source>` elements include a `media` attribute that contains a media condition — as with the first `srcset` example, these conditions are tests that decide which image is shown — the first one that returns true will be displayed. In this case, if the viewport width is 799px wide or less, the first `<source>` element's image will be displayed. If the viewport width is 800px or more, it'll be the second one.

- The `srcset` attributes contain the path to the image to display. Just as we saw with `<img>` above, `<source>` can take a `srcset` attribute with multiple images referenced, as well as a `sizes` attribute. So, you could offer multiple images via a `<picture>` element, but then also offer multiple resolutions of each one. Realistically, you probably won't want to do this kind of thing very often.

- In all cases, you must provide an `<img>` element, with `src` and `alt`, right before `</picture>`, otherwise no images will appear. This provides a default case that will apply when none of the media conditions return true (you could actually remove the second `<source>` element in this example), and a fallback for browsers that don't support the `<picture>` element.

## For full source, read [Responsive images][4]

[1]: <https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content#other_video_features>
[2]: <https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content>
[3]: <https://css-tricks.com/snippets/css/complete-guide-grid/>
[4]: <https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images>
