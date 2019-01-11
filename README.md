**sha1sum**: c50c1026e80366daba7deaa0f1fa5bcafb4ba2a1 

<a href='https://ko-fi.com/E1E0B4X4' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://az743702.vo.msecnd.net/cdn/kofi4.png?v=0' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>


**NAME**

        rugmi - Upload images to imgur.com and print their links.

**SYNOPSIS**

        rugmi [-ts0h] -f FILE

**DESCRIPTION**

        Upload images to imgur.com and print their links.
		
        On first execution, rugmi will ask you to authorize by providing a PIN code.
        If available, xdg-open will be used to open up a browser to log you in imgur.com and get the PIN code.
        Otherwise, you'll be requested to manually copy-paste an authorization link into your browser.

        After providing the PIN code, an access token and refresh token will be requested from imgur.com
        and stored in ~/.rugmi_tokens with a 077 umask.

        *This file should not be edited manually.*

        After setup is complete, rugmi will automatically ask imgur.com for a new access token once expired.

**OPTIONS**

        -f,--file FILE              Select a FILE to upload.
        -0,--null                   Read null terminated file names from stdin.
        -t,--link-type TYPE         Choose what type of link to print after upload.
        -s,--display-size SIZE      Select the display size of the uploaded image.

        -- FILES                    Ignore any options to come.
                                    Everything after this option is considered a file.
        -h,--help                   Show this message and exit successfully.

         Link types:
            * Direct   (email & IM) - Default
            * Image    (email & IM)
                The uploaded image as it is hosted in imgur.com, with all the fun stuff around.
                This type of link will ignore any display size ( if provided via -s,--display-size )
            * Markdown (reddit comments)
            * HTML     (website/blogs)
            * BBCode   (message boards & forums)
            * LBBCode  (Linked BBCode suitable for message boards)

         Display size options:
            * O  (Original) - Default
            * SS (Small square)
            * BS (Big square)
            * ST (Small thumbnail)
            * MT (Medium thumbnail)
            * LT (Large thumbnail)
            * HT (Huge thumbnail)

**EXAMPLES**

        Upload foo.png, bar.png, baz.png and print the result links to stdout.
        $ rugmi -f foo.png -f bar.png -f baz.png
            or
        $ rugmi -- foo.png bar.png baz.png

        Upload all JPEG files in a directory and print the result links to stdout.
        $ find dir/ -type f -name '*.jpg' -print0 | rugmi -0

        Upload foo.png and print an HTML type of link to be displayed as a medium thumbnail.
        rugmi -f foo.png -t HTML -s MT
		

    Written by Rany Albeg Wein - rany.albeg@gmail.com
    21/5/2016
    
    Edit 11/1/2019 - Auto Oauth2 setup.
### Author
    Rany Albeg Wein - rany.albeg@gmail.com

### License

    Copyright (C) 2019 Rany Albeg Wein - rany.albeg@gmail.com
    
    This program is free software; you can redistribute it and/or
    modify it under the terms of the GNU General Public License
    as published by the Free Software Foundation; either version 2
    of the License, or (at your option) any later version.
    
    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.
    
    You should have received a copy of the GNU General Public License
    along with this program; if not, write to the Free Software
    Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301, USA.


