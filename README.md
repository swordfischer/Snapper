Snapper
=======

Snapper is a screenshotting/screencasting tool, which simplifies the process of copying and linking to your files (if you have place to scp/rsync them, and serve them)  


Dependencies
------------

* bash
* imagemagick
* xclip
* rsync/scp

Usage
-----

    Usage: snapper [-c <video|screenshot>] [-h host] [-d destination] [-a <screen|window|active|select>] [-l URL] [-?]

      -c    defines whether to screencast or screenshot
            video       (ffmpeg screencast)
            screenshot  (xwd/import screenshot)

      -h    defines host
            either localhost or remote host.            
            
      -d    defines destination         
            default is ${HOME}
            
      -a    defines area:           
            screen     (entire screen)
            window     (selected window)
            active     (active window) ! NOT FOR VIDEO
            select     (selection) ! NOT FOR VIDEO

      -l    defines the URL
            default is ss_${DATE}.png

      -?    display this help and exit

    Examples:
      snapper
            Checks for .snapperrc, and screenshots folder, otherwise creates it
            and gives defaults values, and snap, a screenshot
            
      snapper -h localhost -a screen
            Takes a screenshot of the entire screen
            and saves to home dir.
            
      snapper -h host.tld -a window -l https://host.tld
            Takes a screenshot of a selected window
            and copy the url (https://host.tld/${FILE})
            to the clipboard.

License
-------
Snapper is licensed under the [MIT License](http://en.wikipedia.org/wiki/MIT_License)  
The full license text is available in [LICENSE.md](https://github.com/swordfischer/snapper/blob/master/LICENSE.md)
