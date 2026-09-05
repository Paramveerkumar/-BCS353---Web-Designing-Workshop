# 🎵🎬 HTML Multimedia

## 📌 Introduction

**Multimedia** refers to different types of media that we can **see or hear** on a web page.

Examples of multimedia include:

* 🖼️ Images
* 🎵 Music
* 🔊 Audio and sound
* 🎬 Videos
* 🎥 Movies
* 🎞️ Animations

Modern websites often use multimedia to make web pages more interactive and attractive.

---

# 1️⃣ What is Multimedia?

The word **Multimedia** means using more than one type of media to present information.

For example, a website may contain:

```text
Text
  +
Images
  +
Audio
  +
Video
  +
Animation
```

All these together can be called **multimedia content**.

### 🌐 Real-Life Examples

Multimedia is commonly used on:

* YouTube → Videos
* Spotify → Music and audio
* Instagram → Images and videos
* Online learning websites → Video lectures
* News websites → Images, videos, and audio
* Gaming websites → Animation, sound, and video

---

# 2️⃣ Multimedia on Web Pages

A web page can contain different types of multimedia.

```text
                 WEB PAGE
                     │
        ┌────────────┼────────────┐
        │            │            │
      Images        Audio        Video
        │            │            │
      🖼️            🔊           🎬
```

HTML provides special elements to add multimedia to a webpage.

The most important multimedia elements are:

```html
<audio>
<video>
```

We will study these elements in detail in the next sections.

---

# 3️⃣ Multimedia Files and File Extensions

Multimedia elements are usually stored in **media files**.

The file type can often be identified by its **file extension**.

### Examples

| File Extension | Common Media Type |
| -------------- | ----------------- |
| `.mp3`         | Audio             |
| `.wav`         | Audio             |
| `.ogg`         | Audio/Video       |
| `.mp4`         | Video             |
| `.webm`        | Video             |
| `.avi`         | Video             |

### Example

```text
song.mp3
```

The `.mp3` extension indicates an audio file.

```text
movie.mp4
```

The `.mp4` extension usually indicates a video file.

---

# 4️⃣ Common Video Formats

There are many video formats available.

However, modern HTML browsers mainly support formats such as:

* MP4
* WebM
* Ogg

## Common Video Formats Table

| Format    | File Extension  | Description                     | HTML Support                       |
| --------- | --------------- | ------------------------------- | ---------------------------------- |
| MPEG      | `.mpg`, `.mpeg` | Older popular video format      | Limited/Not recommended            |
| AVI       | `.avi`          | Audio Video Interleave format   | Limited browser support            |
| WMV       | `.wmv`          | Windows Media Video             | Limited browser support            |
| QuickTime | `.mov`          | Apple video format              | Limited browser support            |
| Flash     | `.swf`, `.flv`  | Older web multimedia technology | ❌ Not supported in modern browsers |
| Ogg       | `.ogg`          | Open multimedia format          | Supported by some browsers         |
| WebM      | `.webm`         | Web-focused video format        | Supported by modern browsers       |
| MP4       | `.mp4`          | Most commonly used video format | ✅ Widely supported                 |

---

# ⭐ Recommended Video Formats

For modern web development, the most commonly used formats are:

```text
🥇 MP4
🥈 WebM
```

### Best Practice

For maximum compatibility, developers often provide multiple video formats.

```html
<video controls>

    <source src="movie.mp4" type="video/mp4">

    <source src="movie.webm" type="video/webm">

    Your browser does not support the video tag.

</video>
```

The browser will try to play a supported format.

---

# 5️⃣ Common Audio Formats

Audio files are used to store:

* 🎵 Music
* 🔊 Sound effects
* 🎙️ Voice recordings
* 🎧 Podcasts

Some common audio formats are:

* MP3
* WAV
* OGG
* AAC

---

## Common Audio Formats Table

| Format    | File Extension  | Description                                                    |
| --------- | --------------- | -------------------------------------------------------------- |
| MIDI      | `.mid`, `.midi` | Contains musical instructions/notes rather than recorded sound |
| RealAudio | `.rm`, `.ram`   | Older streaming audio format                                   |
| WMA       | `.wma`          | Windows Media Audio                                            |
| AAC       | `.aac`          | Advanced Audio Coding                                          |
| WAV       | `.wav`          | High-quality audio format                                      |
| Ogg       | `.ogg`          | Open multimedia format                                         |
| MP3       | `.mp3`          | Popular compressed music format                                |
| MP4       | `.mp4`          | Container format that can also contain audio                   |

---

# ⭐ Recommended Audio Formats

The most commonly used audio formats for websites are:

```text
🥇 MP3
🥈 WAV
🥉 OGG
```

### Why is MP3 Popular?

MP3 is popular because it provides:

* ✅ Good audio quality
* ✅ Smaller file size
* ✅ Wide browser and device support

---

# 6️⃣ Video vs Audio Formats

| Feature          | Video     | Audio     |
| ---------------- | --------- | --------- |
| Contains visuals | ✅ Yes     | ❌ No      |
| Contains sound   | Often     | ✅ Yes     |
| Example          | `.mp4`    | `.mp3`    |
| HTML Element     | `<video>` | `<audio>` |

---

# 7️⃣ The HTML `<video>` Element

The `<video>` element is used to display a video on a webpage.

### Basic Syntax

```html
<video controls>

    <source src="movie.mp4" type="video/mp4">

</video>
```

The `controls` attribute displays video controls such as:

* ▶️ Play
* ⏸️ Pause
* 🔊 Volume
* ⛶ Full screen

---

## Complete Video Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Video Example</title>
</head>

<body>

    <h1>My Video</h1>

    <video width="500" controls>

        <source src="movie.mp4" type="video/mp4">

        Your browser does not support the video element.

    </video>

</body>

</html>
```

---

# 8️⃣ The HTML `<audio>` Element

The `<audio>` element is used to play audio files on a webpage.

### Basic Syntax

```html
<audio controls>

    <source src="song.mp3" type="audio/mpeg">

</audio>
```

The `controls` attribute displays audio controls such as:

* ▶️ Play
* ⏸️ Pause
* 🔊 Volume

---

## Complete Audio Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Audio Example</title>
</head>

<body>

    <h1>My Audio</h1>

    <audio controls>

        <source src="song.mp3" type="audio/mpeg">

        Your browser does not support the audio element.

    </audio>

</body>

</html>
```

---

# 9️⃣ Important `<video>` Attributes

The `<video>` element supports several useful attributes.

| Attribute  | Purpose                                                             |
| ---------- | ------------------------------------------------------------------- |
| `controls` | Displays play, pause, volume controls                               |
| `autoplay` | Starts the video automatically (browser policies may restrict this) |
| `muted`    | Mutes the video                                                     |
| `loop`     | Repeats the video                                                   |
| `width`    | Sets the width of the video                                         |
| `height`   | Sets the height of the video                                        |

### Example

```html
<video width="500"
       controls
       muted
       loop>

    <source src="movie.mp4" type="video/mp4">

</video>
```

---

# 🔟 Important `<audio>` Attributes

The `<audio>` element also supports useful attributes.

| Attribute  | Purpose                                                 |
| ---------- | ------------------------------------------------------- |
| `controls` | Displays audio controls                                 |
| `autoplay` | Starts audio automatically (may be blocked by browsers) |
| `muted`    | Mutes the audio                                         |
| `loop`     | Repeats the audio                                       |

### Example

```html
<audio controls loop>

    <source src="song.mp3" type="audio/mpeg">

</audio>
```

---

# 🧠 Easy Way to Remember

```text
VIDEO → You can SEE + HEAR 🎬🔊

AUDIO → You can only HEAR 🔊🎵
```

### HTML Elements

```text
Video → <video>

Audio → <audio>
```

---

# 🔄 Supporting Multiple Formats

Different browsers may support different media formats.

Therefore, we can provide multiple source files.

## Video Example

```html
<video controls>

    <source src="movie.mp4" type="video/mp4">

    <source src="movie.webm" type="video/webm">

    Your browser does not support the video.

</video>
```

The browser checks the available formats and uses one that it supports.

---

## Audio Example

```html
<audio controls>

    <source src="song.mp3" type="audio/mpeg">

    <source src="song.ogg" type="audio/ogg">

    Your browser does not support the audio.

</audio>
```

---

# 🎯 Complete Multimedia Webpage Example

```html
<!DOCTYPE html>
<html>

<head>

    <title>HTML Multimedia</title>

</head>

<body>

    <h1>Welcome to Multimedia Page</h1>

    <hr>

    <h2>Video Example</h2>

    <video width="500" controls>

        <source src="movie.mp4" type="video/mp4">

        <source src="movie.webm" type="video/webm">

        Your browser does not support the video element.

    </video>

    <hr>

    <h2>Audio Example</h2>

    <audio controls>

        <source src="song.mp3" type="audio/mpeg">

        <source src="song.ogg" type="audio/ogg">

        Your browser does not support the audio element.

    </audio>

</body>

</html>
```

---

# 🧠 Multimedia Concept Map

```text
                    MULTIMEDIA
                        │
        ┌───────────────┼───────────────┐
        │               │               │
      IMAGE            AUDIO           VIDEO
       🖼️               🔊              🎬
                        │               │
                     <audio>         <video>
                        │               │
                    MP3/WAV          MP4/WebM
```

---

# 🎯 Chapter Summary

* Multimedia includes sound, music, videos, movies, images, and animations.
* Multimedia files are stored in media files.
* File extensions help identify media formats.
* Common video formats include MP4, WebM, and Ogg.
* MP4 is widely used for videos on the web.
* Common audio formats include MP3, WAV, and OGG.
* MP3 is widely used for compressed music.
* The `<video>` element is used to add videos to a webpage.
* The `<audio>` element is used to add audio to a webpage.
* The `<source>` element specifies media files.
* The `controls` attribute displays media controls.
* Multiple `<source>` elements can improve browser compatibility.

---

# ❓ Practice Questions

### Question 1

What is multimedia?

### Question 2

Name four examples of multimedia.

### Question 3

Which HTML element is used to add a video?

### Question 4

Which HTML element is used to add audio?

### Question 5

What is the purpose of the `controls` attribute?

### Question 6

Name two commonly used video formats.

### Question 7

Name two commonly used audio formats.

### Question 8

What is the purpose of the `<source>` element?

### Question 9

What is the difference between audio and video?

---

# 💻 Practice Task

Create a webpage called **My Multimedia Page** containing:

### 🎬 Video Section

* Add a heading.
* Add one video using the `<video>` element.
* Add `controls`.
* Set the width of the video.

### 🎵 Audio Section

* Add a heading.
* Add one audio file using the `<audio>` element.
* Add `controls`.

### 🎯 Goal

Practice using:

```html
<video>

<audio>

<source>
```

and understand how multimedia files are added to HTML webpages.

