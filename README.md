# video-dl

This command line tool is for downloading videos from http://dramacool.to/.

In particular, I was watching [Descendant of the sun](http://dramacool.to/the-descendant-of-the-sun-episode-1.html), the hottest Korean drama right now (as of 2016).

## Installation

[youtube-dl](https://github.com/rg3/youtube-dl) is required, as it is used for downloading the video.

    brew install youtube-dl

Then install `video-dl`:

    gem install video-dl


## Usage

    video-dl http://dramacool.to/the-descendant-of-the-sun-episode-6.html

The command will simply download in the current directory.
