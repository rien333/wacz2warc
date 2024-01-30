# Installation

1. Ensure the prerequiste dependencies are installed: 

* Fedora:

``` shellsession
$ sudo dnf install unzip sed gzip
```

* Arch Linux:

``` shellsession
$ sudo pacman -Sy unzip sed gzip
```

* Debian/Ubuntu:

``` shellsession
$ sudo apt-get install unzip sed gzip
```

2. Download [wacz2warc](placeholder), or clone this repository

3. Make sure `wacz2warc` is executable for all users: 

``` shellsession
$ chmod u+x wacz2warc
```

4. Copy `wacz2warc` somewhere in your `$PATH`. For example: 

``` shellsession
$ sudo mv wacz2warc /usr/bin/
```

# Usage #

`wacz2warc` expects one or more `.wacz` files as input:

``` shellsession
$ ls 
archive1.wacz archive2.wacz archive3.wacz 

# convert a single archive
$ wacz2warc archive1.wacz

# combine and convert all archives in the current directory
$ wacz2warc *.wacz
```

If everything goes well, there should be a new `.warc` file in the directory of the original `.wacz` archive. The filename of this new `.warc` file is identical to the first `.wacz` input file given to `wacz2warc`.

Run `wacz2warc -h` or `wacz2warc --help` for a summary of these instructions.

# Known issues #

* The output will probably contain duplicate pages and files
