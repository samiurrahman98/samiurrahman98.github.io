---
layout: post
title: "Audio Player"
description: "An overview and video demonstration of an embedded audio player system."
thumb_image: "documentation/sample-image.jpg"
tags: [school, development]
---

{% highlight html %}
<div class="background">
  <h2> Damn Samuel, back at it again with the HTML </h2>
  <p>
    My name's not Samuel, I just needed a name to use that 
    has two syllables and rhymes with Daniel. If you don't 
    understand the reference, you should probably watch the 
    video embed below this HTML body.
  </p>
</div>
{% endhighlight %}

### <strong>Damn Daniel Reference for the Meme-Deprived</strong>

<div class="embed-responsive embed-responsive-16by9">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/PnI-byHtMN0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>

Long time no see! I've been busy with school lately, but that's nothing new. This project specifically is one of many that has kept me busy over the past few weeks, but one that I certainly enjoyed working on.

For this project, we were asked to design a digital audio player (software implementation only - in C) using the university-provided LogicalStep FPGA Board for our ECE 224 (Embedded Microprocessor Systems) course. The idea was to develop a device that can play stereo wav files off a MicroSD card and send the output to a standard headphone jack. Aside from the basic functionality, it required that we develop a user interface that displays the file name on an LCD and incorporate push buttons to start/stop the song, as well as search through tracks.

### <strong>Specifications</strong>
* The audio player must support .wav format audio files (stereo audio with 16-bit audio samples).
* The audio must be read from a MicroSD card.
* The audio output uses a standard headphone jack.
* The hardware must include an LCD that indicates the track number (as enumerated on the SD card) and the track title (filename) on the first line of the LCD. THe second line of the LCD must show the Player functiosn for STOPPED, PAUSED, PLAYBACK-NORMAL SPD, PLAYBACK - HALF SPD, PLAYBACK - DBL SPD, PLAYBACK - MONO LEFT_Audio.
* The player must only display track titles (the filename) that are actual wav files indicated by the .wav extension.
* The audio played must be free of distortion for all speeds.

<strong>User Interface/Push-Button Functionality:</strong>

{% include image.html path="audio-player-ui.png" path-detail="audio-player-ui.png" alt="UI/Push-Button Functionality Specifications" %}

When the WavePlayer is initialized it displays the <strong>first</strong> track title on the LCD and is then in the <strong>stopped</strong> mode. Pressing the <u>Play/Pause</u> button plays the currently selected track, as currently displayed on the LCD and then <u>must automatically stop</u>. Pressing the Play/Pause button while a track is playing pauses the track. When paused, the WavePlayer must remain on the current track at its current position and the audio must be silent. Pressing the Play/Pause button again will allow the WavePlayer to continue the playback from its current track position and then continue to the end of the track. At this point, the WavePlayer must <strong>stop</strong> and then set the current track position back to the <u>beginning of the current track</u>.

The <u>Stop</u> button stops a currently playing track and resets the track position to the beginning of the track. If a track is paused, the Stop button resets the track position to the beginning of the track.

The <u>Previous</u> button searches backwards through the tracks on the SD card (one track each time the button is pressed), and displays the current track name on the LCD if the button is pressed. Searching farther backward past the first track in the list should cause the last track to be displayed. If the button is pressed while a track is <u>not</u> playing (stopped or paused) then the player just moves to the start of the previous track and <strong>stops</strong>. If the button is pressed <u>while a track is playing</u> then the playing continues but it begins at the start of the previous track.

The <u>Next</u> button searches forwards through the tracks on the SD card (one track each time the button is pressed), and displays the newly searched track name on the LCD. Searching farther forward past the last track should cause the first track to be displayed. If the button is pressed while a track is <u>not</u> playing (stopped or paused) then the player just moves to the start of the next track and stops. If the button is pressed <u>while a track is playing</u> then the playing continues but it begins at the start of the next track.

### Demonstration

<div class="embed-responsive embed-responsive-16by9">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/Ss-cPUwrizw" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>

And there you have it! Special thanks to my partner Marcus for keeping his composure during all the late-nights spent on debugging the software for the device.

That's all from me today folks. Stay tuned for new content, thanks for reading!