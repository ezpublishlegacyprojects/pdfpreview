<code>
/*
    PDF preview for eZ publish
    Copyright (C) 2006  xrow GbR, Hannover Germany, http://xrow.de

    This program is free software; you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation; either version 2 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.
*/

### BEGIN INIT INFO
# Provides:          pdfpreview
# Depends:		     imagemagick + ghostscript
# OS:			     Linux, FreeBSD, Windows
# Version:		     > eZ 3.4		
# Developed:	     Björn Dieding  ( bjoern@xrow.de )
# Short-Description: PDF Preview image generator
# Description:       Generates an image from a single PDF page  
# Resources:	     http://pubsvn.ez.no/community/trunk/extension/pdfpreview/
### END INIT INFO
</code>

#### Setup ####

install imagemagick + ghostscript + activate extension

#### Usage ####

pathtofile|pdfpreview( width [, page [, name ] ] ] )

<code>
{if $node.object.data_map.file.content.mime_type|eq('application/pdf')}
<img src={$node.object.data_map.file.content.filepath|pdfpreview( 99, 1, "My PDF.pdf" )|ezroot} alt="Preview">
{/if}
</code>

#### Troubleshooting ####

Look in the debug output