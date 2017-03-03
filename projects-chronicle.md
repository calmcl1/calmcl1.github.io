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

#### With binaries
Linux users can also [download the binaries](https://github.com/calmcl1/chronicle/releases). However, you will need to manually install the pre-requisites:
* RtAudio, (`librtaudio-dev`)
* libsndfile, which is in most package managers. (`libsndfile1-dev`)
* Boost, which is in most package managers (`libboost-all-dev`).
* ncurses, which is available in most package managers (`libncurses5-dev`).

#### Compiling from scratch
Or, you can compile chronicle from scratch.
You'll also need to download the build toolchain: `build-essential` and `pkg-config`
Then, [download the source tarball](https://github.com/calmcl1/chronicle/releases) and run `make linux`.

The built binary will exist in (srcdir)/build/linux.

I'm working on getting `.deb`s built!

## Using Chronicle
To start Chronicle recording hourly to the local directory using the default audio device, just run:

`$ chronicle`

No configuration needed!

However, to configure Chronicle more to your liking, use the following options:
```
chronicle [-h | --help]
chronicle [--licence]
chronicle [-l | --list-devices ]
chronicle [-d | --directory OUTPUT_DIRECTORY] [-f | --filename FORMAT] [-i | --input-device DEVICE_ID] 
          [[-a | --max-age MAX_FILE_AGE] | --no-delete] [-s | --audio-format [WAV | OGG]]

Where:
    -h | --help          Prints this help message.
    --licence            Prints the licence information for this software and libraries that it uses.
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
    --no-delete          If passed, Chronicle will not delete old audio files, so they can be manually managed.
		                     Incompatible with --max-age.
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

## FAQ
**Will Chronicle have a GUI?**
[Probably](//github.com/calmcl1/chronicle/issues/17). However, in order to stop the software growing beyond a reasonable scope, it'll probably be introduced as a separate bit of software that will *talk* to Chronicle. This will allow for quick feature development on both the UI side and core recording side without risking one breaking the other.

**Can Chronicle record web streams?**
[Possibly](//github.com/calmcl1/chronicle/issues/11). Though, for the same reason, it will probably be part of a different executable that Chronicle-the-logger can take advantage of.

**So Chronicle isn't going to be just one bit of software?**
I can see Chronicle becoming a suite -- with a UI module, a web-stream-as-virtual-hardware-interface module amongst others. This separation of responsibility keeps development simple, the risk involved with adding new features low, and the likelihood of breaking Chronicle by changing something simple also low.

**I've got a great idea for Chronicle! Or, Chronicle doesn't work!**
Righto - [Add it to the list](//github.com/calmcl1/chronicle/issues).

**Can I get in touch with the developer?**
Of course! Email me at [mail@callum-mclean.co.uk](mailto:mail@callum-mclean.co.uk).