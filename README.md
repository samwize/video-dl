# video-dl

This command line tool is for downloading videos from http://dramacool.to/.

In particular, I was watching [Descendant of the sun](http://dramacool.to/the-descendant-of-the-sun-episode-1.html), the hottest Korean drama right now (as of 2016).

## Installation

[youtube-dl](https://github.com/rg3/youtube-dl) is required, as it is used for downloading the video.

    brew install youtube-dl

Then install `video-dl`:

    gem install video-dl


## Usage

    # Download the highest resolution video in the current directory.
    video-dl http://dramacool.to/the-descendant-of-the-sun-episode-6.html

    # Download all the episodes
    video-dl episodes http://dramacool.to/the-descendant-of-the-sun-episode-1.html
