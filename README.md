### Usage
`imgur file1 file2 ... fileN`

On first execution, `imgur` will ask you to provde the following:

- Access token
- Refresh token
- Client id
- Client secret

It will then store this info in `~/.imgur_codes` with a **077** `umask`. After setup is complete, `imgur` will automatically use your refresh token to ask [imgur.com](http://imgur.com/) for a new access token once it expires.

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

