---
permalink: /projects/chronicle
title: Chronicle - a logger for radio
---
# Chronicle
**Chronicle is an audio logger intended for radio ROT logging.**

Find Chronicle [on GitHub](//github.com/calmcl1/projects/chronicle)!

## About Chronicle
Chronicle is a simple, command-line audio logger, designed to record on-the-hour, every hour. This makes it suitable for basic Record of Transmission logging for most radio stations.

## The Story
By UK law, radio stations are required to keep a [record of their transmissions for **42 days**](http://www.legislation.gov.uk/ukpga/1996/55/section/117), in case any of their programming is investigated by OFCOM (the UK broadcasting regulator) due to a complaint or suspected licence breach.

When Halton Community Radio was refurbished in 2016, I oversaw the rebuilding of their IT and networking infrastructure. Part of this included their Record of Transmission logger. When the time came to replace the aging unit, we were faced with a choice: buy a new computer and software, or buy an integrated unit. Neither of these options seemed to offer particularly good value-for-money, so naturally, I ended up writing a basic but functional logger in my spare time!

Chronicle is in use now at HCR and is available for anyone else who may find it useful.

## Get Chronicle
The latest version (v0.1.2bX) is stable enough for production use (and is currently running in a production environment,) but the odd niggle here and there means I'm still calling it *beta* for now.

>If you find Chronicle to be useful, maybe buy me a coffee? I'm on [Flattr](https://flattr.com/submit/auto?fid=kzr39z&url=http%3A%2F%2Fgithub.com%2Fcalmcl1%2Fchronicle) and [PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=FXDR44PHGFEDN)!

### Windows Users
Download binaries for [x32 and x64](https://github.com/calmcl1/chronicle/releases). Nice and easy!

### Linux Users
As yet, there are no binaries available (though that will change soon - and with `.deb`s too!)
For now, [download the source tarball](https://github.com/calmcl1/chronicle/releases) and run `make linux`.
Prerequisites:
* [RtAudio](https://www.music.mcgill.ca/~gary/rtaudio/)
* Boost libraries
* ncurses
* libsndfile

## Using Chronicle
To start Chronicle recording hourly to the local directory using the default audio device, just run:

`$ chronicle`

No configuration needed!

However, to configure Chronicle more to your liking, use the following options:
```
chronicle [-h | --help]
chronicle [-l | --list-devices ]
chronicle [-d | --directory OUTPUT_DIRECTORY] [-f | --filename FORMAT] [-i | --input-device DEVICE_ID] 
          [-a | --max-age MAX_FILE_AGE] [-s | --audio-format [WAV | OGG]]

Where:
    -h | --help          Prints this help message.
    -l | --list-devices  Lists the available input devices with their IDs.
    -d | --directory     Sets the directory to save the logged audio to. A trailing slash is not required, but may
                             be added. On Windows, if using a trailing slash, use a trailing double-slash.
                             Defaults to current directory.
    -f | --format        strftime-compatible format to use when naming the audio files.
                             Defaults to %F %H%M%S .
    -i | --input-device  The ID number of the input device to record from. A list of input devices and their ID
                             numbers can be obtained with `chronicle -l`.
                             If unspecified, the system default audio recording device will be used.
    -a | --max-age       Sets the maximum age (in seconds) before audio files will be automatically deleted.
                             Defaults to 3600000 (1000 hours, in accordance with OFCOM rules).
    -s | --audio-format Sets the audio format to use for the recorded audio files.
                             Acceptable parameters are:
                                 OGG | Ogg Vorbis (.ogg)
                                 WAV | 16-bit PCM WAV (.wav)
                             Defaults to WAV.
```

Read the [README](//github.com/calmcl1/chronicle#chronicle) for more info.

## Making Chronicle Better
Does Chronicle not work the way you expected, or do you have an idea to make Chronicle even more useful?

Head over to the [GitHub Issues](//github.com/calmcl1/chronicle/issues) page and log a new request! Or, those who fancy diving straight in can clone the repo and submit a pull request.