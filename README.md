# wacz2warc

[wacz2warc](https://github.com/rien333/wacz2warc) is a simple shell script to convert and combine one or more [`.wacz`](https://specs.webrecorder.net/wacz/1.1.1/) files into a single `.warc` file.

# Installation

1. Ensure that `sed`, `unzip`, and `gzip` are installed: 

 
* <details>
  <summary>Fedora</summary>
  
  ```shell
  sudo dnf install unzip sed gzip
  ```
</details>

* <details>
  <summary>Arch Linux</summary>
  
  ``` shell
  sudo pacman -Sy unzip sed gzip
  ```
</details>

* <details>
  <summary>Debian/Ubuntu</summary>
  
  ```shell
  sudo apt-get install unzip sed gzip
  ```
</details>

2. Clone this repository (or simply download [wacz2warc](wacz2warc)), and make it your working directory: 

```shell
git clone https://github.com/rien333/wacz2warc.git && cd wacz2warc
```
3. Copy or [symlink](https://en.wikipedia.org/wiki/Symbolic_link#POSIX_and_Unix-like_operating_systems) `wacz2warc` to a location in your `$PATH`, so that you can call it from anywhere. For example: 

```shell
sudo cp wacz2warc /usr/bin/
```

# Usage

`wacz2warc` expects one or more `.wacz` files as input. Thus, say you directory looks like this:

``` shellsession
$ ls 
archive1.wacz archive2.wacz archive3.wacz 
```

In that case, run this to convert `archive1` to a `.warc` file:

``` shell
wacz2warc archive1.wacz
```

Or this to combine and convert  all `.wacz` in the current directory into a single `.warc`:

``` shell
wacz2warc *.wacz
```

The latter command is especially helpful if you encounter a webpage archive that has been split acrross multiple `.warcz` files. 

If everything goes well, there should be a new `.warc` file in the directory of the original `.wacz` file(s). The filename of this new `.warc` will match the first `.wacz`  file provided to `wacz2warc`.

Run `wacz2warc -h` or `wacz2warc --help` for a summary of these instructions.

# Known issues

* The output file will probably contain duplicate pages and files
