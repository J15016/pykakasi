========
Pykakasi
========


Overview
========

.. image:: https://readthedocs.org/projects/pykakasi/badge/?version=latest
   :target: https://pykakasi.readthedocs.io/en/latest/?badge=latest
   :alt: Documentation Status

.. image:: https://travis-ci.org/miurahr/pykakasi.svg?branch=master
   :target: https://travis-ci.org/miurahr/pykakasi
   :alt: Travis-CI

.. image:: https://badge.fury.io/py/pykakasi.png
   :target: http://badge.fury.io/py/Pykakasi
   :alt: PyPI version

.. image:: https://coveralls.io/repos/miurahr/pykakasi/badge.svg?branch=master
   :target: https://coveralls.io/r/miurahr/pykakasi?branch=master
   :alt: Coverage status

.. image:: https://ci.appveyor.com/api/projects/status/mhej9bbe5jomvaj4/branch/master?svg=true
   :target: https://ci.appveyor.com/project/miurahr/pykakasi/branch/master
   :alt: Build status

pykakasi is re-implementation of kakasi library (original is written in C) in Python.

pykakasi at glance
==================

Install::

    pip install pykakasi

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

Documentation
=============

Manual is placed on `readthedocs`_.

.. _`readthedocs`: https://pykakasi.readthedocs.io/en/latest/contents.html


Copyright and License
=====================

Copyright 2010-2019 Hiroshi Miura <miurahr@linux.com>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

