# video-dl

This command line tool is for downloading videos from http://dramacool.to/.

In particular, I was watching [Descendant of the sun](http://dramacool.to/the-descendant-of-the-sun-episode-1.html), the hottest Korean drama right now (as of 2016).

## Installation

[youtube-dl](https://github.com/rg3/youtube-dl) is required, as it is used for downloading the video.

    brew install youtube-dl

Then install `video-dl`:

    gem install video-dl


## Usage

_IMPORTANT_: Because dramacool added [CloudFlare DDoS protection](http://superuser.com/questions/888507/problems-with-wget-to-a-cloudflare-hosted-site-503-service-unavailable/888523) in July 2016, it is now impossible to use this script as it is. There will be a 503 Service Unavailable error. To solve, you have to edit the script. Change the cookies and useragent to yours (instructions within the script).

    # Download the highest resolution video in the current directory.
    video-dl http://dramacool.to/the-descendant-of-the-sun-episode-6.html

    # Download all the episodes
    video-dl episodes http://dramacool.to/the-descendant-of-the-sun-episode-1.html
