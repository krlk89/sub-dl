# NOT WORKING ANYMORE, USE THE MASTER BRANCH

# sub_dl: Subscene subtitle downloader

sub_dl is a command-line tool that searches and downloads subtitles from [Subscene](https://subscene.com).

**LEGAL NOTICE: As written in the [Subscene Terms of Use Agreement](https://subscene.com/site/legal-information) one is only allowed to use tools like this (scrapers) for personal, non-commercial use!**

[Python 3](https://www.python.org/) is required.

## Dependencies:
* [fake-useragent](https://pypi.python.org/pypi/fake-useragent)
* [lxml](https://lxml.de/)
* [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/)
* [Requests](http://docs.python-requests.org/en/master/)

Note: You can also substitute the lxml parser with a built-in one (*e.g.* html.parser).

Easiest way to install all the dependencies:

    pip install -r requirements.txt
    
## How to use:
1. On the first launch your input is needed for generating the configuration file. You can later change this preference by launching the script as ./sub_dl.py -c.
    ```
    ./sub_dl.py
    For information about available command line arguments launch the script with -h (--help) argument.
    
    Type your media directory: /home/user/Downloads
    ```

2. Choose movies/tv shows for which you want to download subtitles. You can choose a single release (*e.g.* 1), multiple releases (*e.g.* 1,3) or a range of releases (*e.g.* 1-4).
    ```
    Checking media directory: /home/user/Downloads
     (1)  Sherlock.S04E02.WEBRip.XviD-FUM
     (2)  Sherlock.S04E03.HDTV.x264-FLEET
     (3)  Sherlock.The.Abominable.Bride.2016.720p.BluRay.H264.AAC-RARBG
     (4)  sherlock.4x01.repack_720p_hdtv_x264-fov.mkv
    Choose a release: 3

    Searching English subtitles for Sherlock.The.Abominable.Bride.2016.720p.BluRay.H264.AAC-RARBG
    ```

3. Choose one from subtitles that are suitable for the selected release. Hearing impaired subtitles are marked with an X.
Downloaded subtitle file will be renamed after the release directory or file.
**Other files on your computer will not be modified in any way (except when a subtitle file with the same name already exists - then it will be overwritten)**!
    ```
    Nr      Rating  Votes	H-i
    (1)	9	16
    (2)	N/A
    (3)	10	16	X
    Choose a subtitle: 3
    Done.
    ```
Note: If there's only one release and/or subtitle available then it will be chosen automatically.
If no subtitles are found for the specific release, all available releases will be shown as a fallback.

4. For help and available command line arguments:
    ```
    ./sub_dl.py -h
    usage: sub_dl.py [-h] [-c] [-l LANGUAGE] [-d DIRECTORY [DIRECTORY ...]] [-a]
                     [-w]

    sub_dl: Subscene subtitle downloader.

    optional arguments:
      -h, --help            show this help message and exit
      -c, --config          configure your media directory
      -l LANGUAGE, --language LANGUAGE
                            specify desired subtitles language (overrules default
                            which is English)
      -d DIRECTORY [DIRECTORY ...], --directory DIRECTORY [DIRECTORY ...]
                            specify media directory (overrules default
                            temporarily)
      -a, --auto            automatically choose best-rated non hearing-impaired
                            subtitles
      -w, --watch           launch VLC after downloading subtitles
    ```

Enjoy!
