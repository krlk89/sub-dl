# sub_dl: Subscene subtitle downloader

sub_dl is a script that downloads subtitle files from [Subscene](https://subscene.com).

**LEGAL NOTICE: As written in the [Subscene Terms of Use Agreement](https://subscene.com/site/legal-information) one is only allowed to use scripts like this for personal use!**

[Python 3](https://www.python.org/) is required.

## Dependencies:
* [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/)
* [Requests](http://docs.python-requests.org/en/master/)

Easiest way to install both BeautifulSoup and Requests:

    user@home-pc:~/sub_dl$ pip install -r requirements.txt
    
## How to use:
1. On the first launch your input is needed for generating the configuration file. You can later change these preferences by launching the script as ./sub_dl.py -c.
    ```
    user@home-pc:~/sub_dl$ ./sub_dl.py
    Type your media directory: /home/user/Downloads
    Type your preferred subtitle language (e.g. English): English
    ```

2. Choose movies/tv shows for which you want to download subtitles. You can choose a single release (*e.g.* 1) or a range of releases (*e.g.* 1-2).
    ```
    Checking media directory: /home/user/Downloads
     (1)  Sherlock.The.Abominable.Bride.2016.720p.BluRay.H264.AAC-RARBG
     (2)  sherlock.4x01.repack_720p_hdtv_x264-fov.mkv
    Choose a release: 1

    Searching subtitles for Sherlock.The.Abominable.Bride.2016.720p.BluRay.H264.AAC-RARBG
    ```

3. Choose one from subtitles that are suitable for the selected release. Hearing impaired subtitles are marked with an X.
Downloaded subtitle file will be renamed after the release directory or file.
**Other files on your computer will not be modified in any way (except when a subtitle file with the same name already exists - then it will be overwritten)**!
    ```
    Nr      Rating  Votes	Hearing impaired
    (1)	    9	    16
    (2)	    N/A
    (3)	    10	    16	    X
    Choose a subtitle: 3
    Done.
    user@home-pc:~/sub_dl$
    ```
Note: If there's only one release and/or subtitle available then it will be chosen automatically.

4. For help and available command line arguments:
    ```
    user@home-pc:~/sub_dl$ ./sub_dl.py -h
    usage: sub_dl.py [-h] [-c] [-a] [-w]

    sub-dl: Subscene subtitle downloader.

    optional arguments:
      -h, --help    show this help message and exit
      -c, --config  configure your media directory and subtitle language
      -a, --auto    automatically choose best-rated non hearing-impaired subtitle
      -w, --watch   launch VLC after downloading subtitles
    ```

Enjoy!
