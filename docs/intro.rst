Introduction
============

This is the documentation for Pykakasi library and utility.
pykakasi is a library and utility implemented `KAKASI`_ functionality in Python.
KAKASI was originaly built to convert Japanese text to roman form.

pykakasi is a free software, and available on `GitHub`_ project.


How To Use pykakasi
===================

How to Install::

    pip install pykakasi

Building library, setup script build dictionary db file and generate pickled db files.
Without dictionary files, a library fails to run.

Dependencies::

    six and semidbm

Sample source code::

    from pykakasi import kakasi,wakati

    text = u"かな漢字交じり文"
    kakasi = kakasi()
    kakasi.setMode("H","a") # Hiragana to ascii, default: no conversion
    kakasi.setMode("K","a") # Katakana to ascii, default: no conversion
    kakasi.setMode("J","a") # Japanese to ascii, default: no conversion
    kakasi.setMode("r","Hepburn") # default: use Hepburn Roman table
    kakasi.setMode("s", True) # add space, default: no separator
    kakasi.setMode("C", True) # capitalize, default: no capitalize
    conv = kakasi.getConverter()
    result = conv.do(text)
    print(result)

    wakati = wakati()
    conv = wakati.getConverter()
    result = conv.do(text)
    print(result)

You can use output `Mode` values from "H", "K", "a" which is each means
"Hiragana", "Katakana" and "Alphabet".
For input, you can use "J" that means "Japanese" that is
mixture of Kanji, Katakana and Hiragana.
Also there is values of "H", "K" that means "Hiragana", and "Katakana".
You can use  "Hepburn" , "Kunrei" or "Passport" as mode "r", Roman table switch.
Also "s" used for separator switch, "C" for capitalize switch.
"S" for separator storing option.

`wakati` is an implementation of kakasi's wakati gaki option.


Supported python versions
=========================

Pykakasi supports python 2.7, python 3.5, 3.6 and PyPy.

It may work with python 2.6, 3.3, 3.4 and pypy3 but these are not tested now.

Options
=======

These switch alphabets are derived from original Kakasi.
Now it support following options:

+--------+---------------------+------------+---------------------------------------+
| Option | Description         | Values     | Note                                  |
+========+=====================+============+=======================================+
| K      | Katakana convertion | a,H,None   | roman, Hiragana or noconversion       |
+--------+---------------------+------------+---------------------------------------+
| H      | Hiragana convertion | a,K,None   | roman, Katakana or noconversion       |
+--------+---------------------+------------+---------------------------------------+
| J      | Kanji conversion    | a,H,K,None | roman or Hiragana, Katakana or noconv |
+--------+---------------------+------------+---------------------------------------+
| a      | Roman conversion    | E,None     | JIS ROMAN or noconversion             |
+--------+---------------------+------------+---------------------------------------+
| E      | JIS ROMAN conversion| a,None     | ascii roman or noconversion           |
+--------+---------------------+------------+---------------------------------------+

Each character means character sets as follows::

    Character Sets
       a: ascii  j: jisroman  g: graphic  k: kana
       (j,k     defined in jisx0201)
       E: kigou  K: katakana  H: hiragana J: kanji
       (E,K,H,J defined in jisx0208)


About KAKASI
============

`KAKASI`_ is the language processing filter to convert Kanji characters to Hiragana, Katakana or Romaji [#1]_ and
may be helpful to read Japanese documents.

The name "KAKASI" is the abbreviation of "kanji kana simple inverter" and the inverse of SKK "simple kana kanji converter"
which is developed by Masahiko Sato at Tohoku University. The most entries of the kakasi dictionary is derived form the
SKK dictionaries. If you have some interests in the naming of "KAKASI", please consult to Japanese-English dictionary. :-)

`KAKASI`_ is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License
as published by the Free Software Foundation; either version 2, or (at your option) any later version.

`KAKASI`_ is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY;
without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License
for more details.


.. _GitHub: https://github.com/miurahr/pykakasi
.. _`KAKASI`: http://kakasi.namazu.org/


.. rubric:: Footnotes

.. [#1] "Romaji" is alphabetical description of Japanese pronunciation.
