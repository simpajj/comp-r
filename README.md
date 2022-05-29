# ComPär

Compare two videos running simultaneously in the same window, with a realtime slider to adjust the width of the compared videos. This little tool is useful for comparing the quality of different video coding formats/codecs. 

![preview](ss.png)

## Setup 

1. Point to the video/image sources in index.html
2. Open index.html in your browser

> ⚠️ On Mac, MacOS High Sierra + Safari is required for web playback. 
> Note that as of 2017-08-18 h265 playback in Safari requires the HEVC coding to be of type `hvc1` and not `hev1` (check with `ffmpeg -i 'video.mp4'`).
> To encode from `hev1` to `hvc1`: 

```
mp4box -raw 1 h265_hev.mp4
mp4box -add h265_hev_track1.hvc h265_hvc.mp4
```

## Keyboard shortcuts

| Action                    | Key          
| -------------             |:-------------
| Pause/Play video          | Space
| Show/hide video overlay   | i
| Jump to next frame *      | Right arrow 
| Jump to prev frame *      | Left arrow

> ⚠️ The frame jump functionality is based on a frame rate constant set in index.js, which might have to be changed for the functionality to work as expected.

## Known issues
* The two videos might fall out of sync during playback 

> Nothing is done to resync the videos during playback. Syncing is currently done when pausing, but may still take some time. Maybe needless to say, jumping to the next or previous frames also triggers syncing of the videos (and also pauses the videos).

* No progress bar or seek functionality

* Clip video on hover does not work with HLS-playlist

> Workaround is to click and drag to clip instead of only hovering.
