### Usage
**NAME**

        imgur - Upload images to imgur.com and print their links.

**SYNOPSIS**

        imgur [-ts0h] -f FILE

**DESCRIPTION**

        Upload images to imgur.com and print their links.

        On first execution, imgur will ask you to provide the following:

        - Access token
        - Refresh token
        - Client id
        - Client secret

        It will then store this info in ~/.imgur_codes with a 077 umask.
        After setup is complete, imgur will automatically use your refresh token to ask imgur.com for a new access token once it expires.

**OPTIONS**

        -f,--file FILE              Select a FILE to upload.
        -0,--null                   Read null terminated file names from stdin.
        -t,--link-type TYPE         Choose what type of link to print after upload.
        -s,--display-size SIZE      Select the display size of the uploaded image.

        -- FILES                    Ignore any options to come.
                                    Everything after this option is considered a file.
        -h,--help                   Show this message and exit successfully.

         Link types:
            * Image    (email & IM)
                The uploaded image as it is hosted in imgur.com, with all the fun stuff around.
                This type of link will ignore any display size ( if provided via -s,--display-size )
            * Direct   (email & IM)
            * Markdown (reddit comments)
            * HTML     (website/blogs)
            * BBCode   (message boards & forums)
            * LBBCode  (Linked BBCode suitable for message boards)

         Display size options:
            * O  (Original)
            * SS (Small square)
            * BS (Big square)
            * ST (Small thumbnail)
            * MT (Medium thumbnail)
            * LT (Large thumbnail)
            * HT (Huge thumbnail)
            
**EXAMPLES**

        Upload foo.png, bar.png, baz.png and print the result links to stdout.
        $ imgur -f foo.png -f bar.png -f baz.png
            or
        $ imgur -- foo.png bar.png baz.png

        Upload all JPEG files in a directory and print the result links to stdout.
        $ find dir/ -type f -name '*.jpg' -print0 | imgur -0

        Upload foo.png and print an HTML type of link to be displayed as a medium thumbnail.
        $ imgur -f foo.png -t HTML -s MT

### Author
Rany Albeg Wein - rany.albeg@gmail.com

### License

Copyright (C) 2016 Rany Albeg Wein - rany.albeg@gmail.com

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
