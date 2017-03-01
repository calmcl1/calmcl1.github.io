# Hi there!

I'm Cal McLean - not a developer but I tend to write software and little utilities in my spare time.
These tend to exist simply to make my life easier, but like they say -- sharing is caring ;)

I work in the vision mixer for TV as my day job, and maintain the technical infrastructure behind [Halton Community Radio](//hcr923fm.com) (a community station in the north-west of the UK, where I grew up) in my spare time in the UK. I keep in touch with, and occasionally write some bits and pieces for my old friends from my time as a theatre technician!

## Projects
Most of my available projects pertain to the radio or broadcasting industry, mostly because that's where I work. I believe in [eating my own dog food](https://en.wikipedia.org/wiki/Eating_your_own_dog_food), so many of these projects are in use in a production environment somewhere.

## [Chronicle](//github.com/calmcl1/chronicle)
**Chronicle is an audio logger intended for radio ROT logging.**

### Background
By UK law, radio stations are required to keep a [record of their transmissions for **42 days**](http://www.legislation.gov.uk/ukpga/1996/55/section/117), in case any of their programming is investigated by OFCOM (the UK broadcasting regulator) due to a complaint or suspected licence breach.

When Halton Community Radio was refurbished in 2016, I oversaw the rebuilding of their IT and networking infrastructure. Part of this included their Record of Transmission logger. When the time came to replace the aging unit, we were faced with a choice: buy a new computer and software, or buy an integrated unit. Neither of these options seemed to offer particularly good value-for-money, so naturally, I ended up writing a basic but functional logger in my spare time!

Chronicle is in use now at HCR and is available for anyone else who may find it useful.

### Get Chronicle
The latest version (v0.1.2bX) is stable enough for production use (and is currently running in a production environment,) but the odd niggle here and there means I'm still calling it *beta* for now.

#### Windows Users
Download binaries for [x32 and x64](https://github.com/calmcl1/chronicle/releases). Nice and easy!

#### Linux Users
As yet, there are no binaries available (though that will change soon - and with `.deb`s too!)
For now, [download the source tarball](https://github.com/calmcl1/chronicle/releases) and run `make linux`.
Prerequisites:
* [RtAudio](https://www.music.mcgill.ca/~gary/rtaudio/)
* Boost libraries
* ncurses
* libsndfile