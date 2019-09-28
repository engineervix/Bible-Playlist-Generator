Bible-Playlist-Generator
========================

[![forthebadge](https://forthebadge.com/images/badges/made-with-python.svg)](https://forthebadge.com)

[![python3](https://img.shields.io/badge/python-3.6%20%7C%203.7-brightgreen.svg)](https://python3statement.org/#sections50-why) [![CircleCI](https://circleci.com/gh/engineervix/Bible-Playlist-Generator/tree/master.svg?style=svg)](https://circleci.com/gh/engineervix/Bible-Playlist-Generator/tree/master)

This python script generates an m3u playlist of 10 Bible Chapters (represented by 10 mp3 files) to be listened to on any given day _x_, according to [**Professor Grant Horner's Bible-Reading System**](http://www.thevinefellowship.com/10Lists.pdf). The audio Bible is as downloaded from the [_Faith Comes by Hearing®_ website](http://www.bible.is/audiodownloader).

The script also copies the files on the playlist into a new folder
so that you can carry the folder on your USB or any other device and listen anywhere (car, home theatre, phone, tablet, etc).

### Usage

From the command prompt,

```
python bible_playlist_generator.py -d x
```

where *x* is an integer that represents the day on the Bible-Reading System, as in day 1, day 2, ... day 524, etc. For example, if you want the playlist for day *37*;

```
python bible_playlist_generator.py -d 37
```

### Help

```
python bible_playlist_generator.py --help
```

### Prerequisites / Assumptions

* Python must be installed on your computer and [added to the PATH](http://superuser.com/questions/143119/how-to-add-python-to-the-windows-path) (the script has been tested on GNU/Linux<sup>[1](#footnote1)</sup> running Python ~2.7~ 3.6 / 3.7. I have since moved to python3. If you are still using python2, you need to [switch to python3](https://docs.python-guide.org/starting/which-python/#recommendations)!).

* Install the dependencies:

```
pip install -r requirements.txt
```

* The script requires the following files, which are in the `data` subdirectory:
  * list_01.txt
  * list_02.txt
  * list_03.txt
  * list_04.txt
  * list_05.txt
  * list_06.txt
  * list_07.txt
  * list_08.txt
  * list_09.txt
  * list_10.txt

These text files contain the Bible Chapters in the lists from Professor Grant Horner's Bible-Reading System.

* In addition to the above, it is assumed that:

  1. the Bible folder is also on the same path as the python script and the above files.
  2. the Bible folder is named `ENGESVC2DA` by default. If your Bible folder is named differently, pass the folder name as an argument to the script:

  ```bash
  python bible_playlist_generator.py -d 37 -f "Name_of_folder"
  ```

### Important Notes

* This script will only be useful to you if you use Professor Grant Horner's Bible-Reading System as the basis for your Bible Reading Plan.
* The Audio Bible version used is the 2001 ESV dramatized Bible (complete), as freely downloaded from http://www.bible.is/audiodownloader. (The size is over 2Gb)

## Extras

### `make_one_week_playlist.sh`

There's a bash script `make_one_week_playlist.sh` which allows you to create playlists for a week or whatever period you so wish. I created it because I wanted to make my playlists in advance and copy the files to my other devices and external media only once. Also, I only get to run one command and I have as many playlists as I want!

All you need to do is specify the start day as an argument to the script, as shown below:

```bash
$ ./make_one_week_playlist.sh 200
```

If you want playlists for a period longer than seven days, edit the script and modify the `$END` variable accordingly.

## Tests

Simply run `pytest` in the root directory of this repository. If you want to check the coverage and get more details of the tests, you could run

```bash
pytest -vv --cov=. --cov-report term-missing
```

----

**Footnotes**

<a name="#footnote1">**1**</a>: I am yet to test it on a Windows Shell as well as on a Mac. Previous versions of the script ran well on Windows and Mac OS X. However, since the major re-write of the script in September 2019, I haven't tested it on other platforms other than Ubuntu where I primarily develop from.
