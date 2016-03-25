# video-dl

This command line tool is for downloading videos from http://dramacool.to/.

In particular, I was watch [Descendant of the sun](http://dramacool.to/the-descendant-of-the-sun-episode-1.html), the hottest Korean drama right now (as of 2016).

## Installation

[youtube-dl](https://github.com/rg3/youtube-dl) is required, as it is used for the downloading:

    brew install youtube-dl

Then install this

    git clone <this-url>
    gem build video-dl.gemspec
    gem install video-dl-1.0.0.gem


## Usage

    video-dl http://dramacool.to/the-descendant-of-the-sun-episode-6.html

The command will simply download in the current directory.
