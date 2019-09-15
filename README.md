Bible-Playlist-Generator
========================

[![forthebadge](https://forthebadge.com/images/badges/made-with-python.svg)](https://forthebadge.com) [![python3](https://img.shields.io/badge/python-3.6%20%7C%203.7-brightgreen.svg)](https://python3statement.org/#sections50-why)

This python script generates an m3u playlist of 10 Bible Chapters (represented by 10 mp3 files) to be listened to on any given day _x_, according to [**Professor Grant Horner's Bible-Reading System**](http://www.thevinefellowship.com/10Lists.pdf). The audio Bible is as downloaded from the [_Faith Comes by Hearing®_ website](http://www.bible.is/audiodownloader).

The script also copies the files on the playlist into a new folder
so that you can carry the folder on your USB or any other device and listen anywhere (car, home theatre, phone, tablet, etc).

### Usage

From the commandline, 

```
python scripture_playlist_gen.py x
```

where *x* is an integer that represents the day on the Bible-Reading System, as in day 1, day 2, ... day 524, etc. For example, if you want the playlist for day *37*;

```
python scripture_playlist_gen.py 37
```

### Prerequisites / Assumptions

* Python must be installed on your computer and [added to the PATH](http://superuser.com/questions/143119/how-to-add-python-to-the-windows-path) (the script has been tested on Windows, Mac OS X and Ubuntu running Python ~2.7~ 3.6 / 3.7. I have since moved to python3. If you are still using python2, you need to [switch to python3](https://docs.python-guide.org/starting/which-python/#recommendations)!).

* Install [eyeD3](http://eyed3.nicfit.net/) &mdash; a Python tool for working with audio files, specifically MP3 files. The script has been tested using version 0.78 upwards. Install eyeD3 as follows:

```
pip install eyeD3
```

* The script requires the following files, which are in the `lists` subdirectory:
  * list1.txt
  * list2.txt
  * list3.txt
  * list4.txt
  * list5.txt
  * list6.txt
  * list7.txt
  * list8.txt
  * list9.txt
  * list10.txt

These text files contain the Bible Chapters in the lists from Professor Grant Horner's Bible-Reading System.

* In addition to the above, it is assumed that the Bible folder is also on the same path as the python script and the above files. If you require a different setup, you can can customize this by editing line 101 in the script. Line 101 is as follows:

```python
BIBLE_DIRECTORY = "ENGESVC2DA/" # Change this to suit your directory. Note the trailing "/"
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
