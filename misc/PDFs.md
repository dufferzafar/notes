# PDFs

An assortment of PDF related tools & libraries.

Some written by me, some used by me and some just on my might-need-later list.

## Getting data into a PDF

* [`imagemagick`](https://imagemagick.org/index.php)
    * Images (jpg,png) to PDF
    * `convert` Commands get very complicated very quickly

    * Look at [`imagetragick`](https://imagetragick.com/) for why it shouldn't _directly_ be used in a "production environment"
        * https://www.imageflow.io/
        * https://superuser.com/questions/333116
        * https://imagemagick.org/script/security-policy.php

* [`pandoc`](https://github.com/jgm/pandoc/)
    * Documents (markdown, docx) to PDF
    * written in Haskell, by an academician - that's all you need to know

* [ScanTailor Advanced](https://github.com/4lex4/scantailor-advanced/)
    * CamScanner for Desktop (linux, win, mac)
    * Written in Python
    * Myriad of different algorithms for image processing

* [Handwritten notes to PDFs](https://github.com/mzucker/noteshrink)

* [Creating a PDFs using Python](https://www.reportlab.com/opensource/)
    * selected to power the print/export feature for Wikipedia

### Stuff written by me

* [Convert _anything_ to a _beautiful_ PDF](https://github.com/dufferzafar/topdf)
    * Source code architecture copied from `youtube-dl`
    * The readme includes lots of references to PDF engines etc.

* [Convert source code to PDF](https://github.com/dufferzafar/src2tex)
    * Battle tested on Bitcoin / CPython codebases

* [HackerRank topic wise PDFs](https://github.com/dufferzafar/HackerRank.pdf)

* [Geeks for Geeks topic wise PDFs](https://github.com/dufferzafar/geeksforgeeks.pdf/)
    * DMCA'd by Geeks for Geeks

* [Zerodha.pdf](https://github.com/dufferzafar/zerodha.pdf)
    * Not public yet

    * [Zerodha Varsity](https://zerodha.com/varsity/) modules that are not available as PDF on their site
    * [z-connect articles](https://zerodha.com/z-connect/) assembled into a PDF

## Getting data out of a PDF

* `pdftotext`
    * Part of the [Poppler Library](https://poppler.freedesktop.org/)
    * Poppler has bindings in all major languages

* Extracting tabular data

    * [Camelot](https://camelot-py.readthedocs.io/en/master/)
        * Python library, very straightforward!
        * Web frontend: https://github.com/camelot-dev/excalibur

        * [Comparison with other libraries](https://github.com/camelot-dev/camelot/wiki/Comparison-with-other-PDF-Table-Extraction-libraries-and-tools) 

    * [Tabula](https://tabula.technology/)
        * Uses [tabula-java](https://github.com/tabulapdf/tabula-java) under the hood
        * Python binding: https://github.com/chezou/tabula-py/

* Optical Character Recognition

    * [OCRmyPDF](https://github.com/jbarlow83/OCRmyPDF)
        * Adds an OCR text layer to scanned PDFs
        * Uses [Tesseract](https://github.com/tesseract-ocr/tesseract) which is as good as it gets

    * [pdftabextract](https://github.com/WZBSocialScienceCenter/pdftabextract)
        * Extracting tables from OCR'ed PDFs

    * [open-paperless](https://github.com/zhoubear/open-paperless)
        * Scan, index, and archive all of your paper documents

        * [papermerge](https://github.com/ciur/papermerge)
        * [openpaper](https://openpaper.work/en/)

    * [doc2text](https://github.com/jlsutherland/doc2text)
        * Detect text blocks and OCR poorly scanned PDFs
        * Does some image processing on the input image as well - like ScanTailor

* Stuff written by me
    * [Export PDF annotations to markdown](https://github.com/dufferzafar/pdf-ano)

## Editing a PDF inplace

* [sejda online suite](https://www.sejda.com/pdf-editor)
    * "basic" text editing
    * not a lot of freedom with text movement

* [Master PDF Editor 5](https://code-industry.net/masterpdfeditor/)
    * Native application for Linux as well
    * Trial version adds a watermark

* [Foxit Phantom](https://www.foxitsoftware.com/pdf-editor/)
    * Cracked version easily availble for Windows
    * Can run on Linux with [Wine](https://www.winehq.org/)

## todo / research

* what does a PDF actually "look" like?
    * creating/editing a simple PDF file in a text editor
    * HTML like tags?

* add references to history
    * how pdf became "the" document format?
    * adobe's pov
