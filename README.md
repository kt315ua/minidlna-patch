# minidlna-patch

Patch: `03_improve_audio_video_titles.diff`

Description: Add disk/track or seasons/episodes into the titles for Audios and Videos.
 
    Adds disk/tracks or seasons/episodes information into the titles 
    for Audios and Videos if option 'enable_serial_episodes_in_titles' 
    is enabled (by default) for comfort serials watching. Previously 
    serial episode was displayed on DLNA clients as 'High way to hell',
    so, now it's displayed as season + episode nubers + title,
    example: 'S01E02 - High way to hell'.

## Instructions to build
- Debian 11:
    - install build deps:
      ``` bash
      apt install build-essential
      apt install debhelper-compat libavcodec-dev libavformat-dev libexif-dev libjpeg62-turbo-dev libid3tag0-dev libvorbis-dev libsqlite3-dev libflac-dev quilt
      ```
    - copy `patch`  to `minidlna-dmo-1.3.0/debian/patches` and update `series` for correct patch name
    - update `minidlna-dmo-1.3.0/debian/changelog` fos usefull description and up version prefix `1.3.0-dmo[prefix+1]`
    - build apt package:
      ``` bash
      cd minidlna-dmo-1.3.0 && dpkg-buildpackage --build=binary,source -kyourmail@mailbox.com -uc -us -tc
      ```
    - install apt pkg
      ```bash
      dpkg -i minidlna_1.3.0-dmo[prefix+1]_amd64.deb
      ```
    - enjoy :)
