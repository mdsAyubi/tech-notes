# Video And Audio

## Audio and video on the web

HTML5 specification has the `<video>` and `<audio>` tags to deal with video and audion on the web.

### The `<video>` element

The `<video>` element allows you to embed a video very easily. For example,

```html
<video src="rabbit320.webm" controls>
  <p>
    Your browser doesn't support HTML5 video. Here is a
    <a href="rabbit320.webm">link to the video</a> instead.
  </p>
</video>
```

- `src` - In the same way as for the `<img>` element, the src (source) attribute contains a path to the video you want to embed. It works in exactly the same way.
- `controls` - Users must be able to control video and audio playback.
- The paragraph inside the `<video>` tags - This is called fallback content — this will be displayed if the browser accessing the page doesn't support the `<video>` element, allowing us to provide a fallback for older browsers.

### Supporting multiple formats

Different browsers support different video (and audio) formats. Formats like MP3, MP4 and WebM are called container formats. They contain different parts that make up the whole song or video — such as an audio track, a video track (in the case of video), and metadata to describe the media being presented.

- A WebM container usually packages Ogg Vorbis audio with VP8/VP9 video. This is supported mainly in Firefox and Chrome.
- An MP4 container often packages AAC or MP3 audio with H.264 video. This is supported mainly in Internet Explorer and Safari.
- The older Ogg container tends to go with Ogg Vorbis audio and Ogg Theora video. This was supported mainly in Firefox and Chrome, but has basically been superceded by the better quality WebM format.

An audio player will tend to play an audio track directly, e.g. an MP3 or Ogg file. These don't need containers.

Example to support multiple formats

```html
<video controls>
  <source src="rabbit320.mp4" type="video/mp4" />
  <source src="rabbit320.webm" type="video/webm" />
  <p>
    Your browser doesn't support HTML5 video. Here is a
    <a href="rabbit320.mp4">link to the video</a> instead.
  </p>
</video>
```

Here we've taken the src attribute out of the actual `<video>` tag, and instead included separate `<source>` elements that point to their own sources. In this case the browser will go through the `<source>` elements and play the first one that it has the codec to support. Including WebM and MP4 sources should be enough to play your video on most platforms and browsers these days.

Each `<source>` element also has a type attribute. This is optional, but it is advised that you include them — they contain the MIME types of the video files, and browsers can read these and immediately skip videos they don't understand.

### Other `<video>` features

Other features in the below code example.

```html
<video
  controls
  width="400"
  height="400"
  autoplay
  loop
  muted
  poster="poster.png"
>
  <source src="rabbit320.mp4" type="video/mp4" />
  <source src="rabbit320.webm" type="video/webm" />
  <p>
    Your browser doesn't support HTML5 video. Here is a
    <a href="rabbit320.mp4">link to the video</a> instead.
  </p>
</video>
```

- width and height - You can control the video size either with these attributes or with CSS. In both cases, videos maintain their native width-height ratio — known as the aspect ratio. If the aspect ratio is not maintained by the sizes you set, the video will grow to fill the space horizontally, and the unfilled space will just be given a solid background color by default.
- autoplay - This attribute makes the audio or video start playing right away while the rest of the page is loading. You are advised not to use auto playing video (or audio) on your sites, because users can find it really annoying.
- loop - This attribute makes the video (or audio) start playing again whenever it finishes. This can also be annoying, so only use if really necessary.
- muted - This attribute causes the media to play with the sound turned off by default.
- poster - This attribute takes as its value the URL of an image, which will be displayed before the video is played. It is intended to be used for a splash or advertising screen.
- preload - This attribute is used in the element for buffering large files. It can take one of 3 values:

  - "none" does not buffer the file
  - "auto" buffers the media file
  - "metadata" buffers only the metadata for the file

### The `<audio>` element

The `<audio>` element works in exactly the same way as the `<video>` element, with a few small differences.

```html
<audio controls>
  <source src="viper.mp3" type="audio/mp3" />
  <source src="viper.ogg" type="audio/ogg" />
  <p>
    Your browser doesn't support HTML5 audio. Here is a
    <a href="viper.mp3">link to the audio</a> instead.
  </p>
</audio>
```

- The `<audio>` element doesn't support the width/height attributes — again, there is no visual component, so there is nothing to assign a width or height to.
- It also doesn't support the poster attribute — again, no visual component.

## Displaying video text tracks

WebVTT is a format for writing text files containing multiple strings of text along with metadata such as what time in the video you want each text string to be displayed, and even limited styling/positioning information. These text strings are called cues, and you can display different types for different purposes,.

- subtitles - Translations of foreign material, for people who don't understand the words spoken in the audio.
- captions - Synchronized transcriptions of dialog or descriptions of significant sounds, to let people who can't hear the audio understand what is going on.
- timed descriptions - Text for conversion into audio, to serve people with visual impairments.

To get this displayed along with the HTML media playback, you need to:

1. Save it as a .vtt file in a sensible place.
1. Link to the .vtt file with the `<track>` element. `<track>` should be placed within `<audio>` or `<video>`, but after all `<source>` elements. Use the kind attribute to specify whether the cues are subtitles, captions, or descriptions. Further, use `srclang` to tell the browser what language you have written the subtitles in. For example,

```html
<video controls>
  <source src="example.mp4" type="video/mp4" />
  <source src="example.webm" type="video/webm" />
  <track kind="subtitles" src="subtitles_en.vtt" srclang="en" />
</video>
```

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/HTML/>

---

Fin
