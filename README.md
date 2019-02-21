remove-pdf-watermark
====================

Short script for removing watermarks from PDF files. Requires [pdftk](http://www.pdflabs.com/tools/pdftk-the-pdf-toolkit/). Users of MacOS El Capitan (10.11) and above should download [pdftk server version 2.02](https://www.pdflabs.com/tools/pdftk-the-pdf-toolkit/pdftk_server-2.02-mac_osx-10.11-setup.pkg).

Tested only lightly. Works by using pdftk to uncompress the PDF, scans through the file for the supplied watermark text 
and removes the closest containing object, then recompresses with pdftk. Sometimes a watermark might not be represented as
contiguous text in the PDF file. That would cause this to fail. Search for the watermark text is not careful to only match
visible text. If the watermark happens to be some control word in PDF, then random objects will be deleted.

Not tested on Windows at all. Requires Python 3.

Not in anyway guaranteed to produce a valid PDF.
