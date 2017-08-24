# video-dl

This command line tool is for downloading videos from http://dramacool.to/.

In particular, I was watching [Descendant of the sun](http://dramacool.to/the-descendant-of-the-sun-episode-1.html), the hottest Korean drama right now (as of 2016).

## Installation

[youtube-dl](https://github.com/rg3/youtube-dl) is required, as it is used for downloading the video.

    brew install youtube-dl

Then install `video-dl`:

    gem install video-dl


## Usage

_IMPORTANT_: Because dramacool added [CloudFlare DDoS protection](http://superuser.com/questions/888507/problems-with-wget-to-a-cloudflare-hosted-site-503-service-unavailable/888523), there will be a 503 Service Unavailable error prior to v1.1.0.

To solve, you have to provide some information manually in current version.

1. Open http://dramacool.to/ in Safari
2. Go to Developer > Open Web Inspector
3. In Console, enter `navigator.userAgent` and copy this value
4. In Storage, look for the cookie for dramacool.io and copy the value for `cf_clearance` and `__cfduid`

In you bash, you need to set the 3 values you copied to your environment variables, like this:

    export VD_USERAGENT="Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_6) AppleWebKit/601.7.7 (KHTML, like Gecko) Version/9.1.2 Safari/601.7.7"
    export CFDUID=dc161acc7c803d061e37601f99d3a613f1467552669
    export CFCLEARANCE=24a24f89450cc2fbc4f58c430e0c52551093af9a-1470733072-1800

Note: `CFCLEARANCE` will expired in 90 minutes, so if you need to use beyond that, you need to update this value.

    # Download the highest resolution video in the current directory.
    video-dl http://dramacool.to/the-descendant-of-the-sun-episode-6.html

    # Download all the episodes
    video-dl episodes http://dramacool.to/the-descendant-of-the-sun-episode-1.html
