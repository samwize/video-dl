# video-dl

This command line tool is for downloading videos from http://dramacool.to/.

In particular, I was watching [Descendant of the sun](http://dramacool.to/the-descendant-of-the-sun-episode-1.html), the hottest Korean drama right now (as of 2016).

## Installation

[youtube-dl](https://github.com/rg3/youtube-dl) is required, as it is used for downloading the video.

    brew install youtube-dl

Then install `video-dl`:

    gem install video-dl

If cloned this project, then:

    gem build video-dl.gemspec
    gem install video-dl-1.x.x.gem

## Usage

_IMPORTANT_: Because dramacool added [CloudFlare DDoS protection](http://superuser.com/questions/888507/problems-with-wget-to-a-cloudflare-hosted-site-503-service-unavailable/888523), there will be a 503 Service Unavailable error prior to v1.1.0.

To solve, you have to provide some information manually in current version.

1. Open http://dramacool.to/ in Safari
2. Go to Developer > Open Web Inspector
3. In Console, enter `navigator.userAgent` and copy this value
4. In Storage, look for the cookie for dramacool.io and copy the value for `cf_clearance` and `__cfduid`

In you bash, you need to set the 3 values you copied to your environment variables, like this:

    export VD_USERAGENT="Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/603.3.8 (KHTML, like Gecko) Version/10.1.2 Safari/603.3.8"
    export CFDUID=d306446c6518e36a1b96dae1fcf7f74681503574569
    export CFCLEARANCE=d05eaa36a565f18d305eb78d4ea28a85c1af24fd-1503574573-604800

Note: `CFCLEARANCE` will expired in 90 minutes, so if you need to use beyond that, you need to update this value.

    # Download the highest resolution video in the current directory.
    video-dl http://dramacool.to/the-descendant-of-the-sun-episode-6.html

    # Download all the episodes
    video-dl episodes http://dramacool.to/the-descendant-of-the-sun-episode-1.html

## For Game of Thrones

[VideoPad](http://videopad.me/series/2-game-of-thrones/seasons/2/episodes/6) has streams via WeShare.

They are also protected by CloudFlare so you will have to provide some environment variables similarly (read above).

    # Download season 2 episode 6
    video-dl videopadweshare http://videopad.me/series/2-game-of-thrones/seasons/2/episodes/6
