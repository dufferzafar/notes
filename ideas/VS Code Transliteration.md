# Transliteration

Gold Standard: https://www.google.co.in/inputtools/try/

Extension: https://github.com/varunkumar/google-input-tools

## Libraries

* Quillpad
    - http://www.quillpad.in/index.html

    - Has open-source server & a client side library
        - Tried running, lots of setup

* Varnam project

    - https://www.varnamproject.com/

    - https://github.com/varnamproject/libvarnam

    - Has an API too: https://www.varnamproject.com/editor

* Polyglot
    - https://github.com/aboSamoor/polyglot

    - Based on the paper:
        + [False-Friend Detection and Entity Matching via Unsupervised Transliteration](https://arxiv.org/abs/1611.06722)

    - @tminima has tried this

* Indic Transliteration
    - https://github.com/sanskrit-coders/indic_transliteration/

    - [Lack of Urdu](https://github.com/sanskrit-coders/indic_transliteration/issues/16)

## Misc. Links

* https://en.wiktionary.org/wiki/Wiktionary:Hindi_transliteration

## Approaches

* Reverse engineer Google Keyboard
    * to see if it does network calls?

* Reverse engineer Google Input Tools' Chrome Extension
    * relatively easy
    * will require internet connectivity

* Use @kwikadi's heuristics based script
    * poor results?
    * ordering?

* Use one of the above libraries for full offline support
    * They're in Python & VS Code would prefer JS?
