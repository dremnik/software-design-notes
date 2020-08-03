# Portability

Language
--------

**Program in the mainstream**
* Stick to the features of a language that are well-defined and unambiguous. This is the *mainstream* of a language.

**Beware of language trouble spots**
* Write code that avoids relying too much on the order of evaluation. This includes the side effects
  of certain expressions.
* Never assume that the elements of a structure occupy contiguous memory. Memory alignment restrictions
  introduce "holes" in the structures, which means that the data isn't necessarily contiguous.

**Try several compilers**
* Different compilers sometimes see your program differently, so use their help. Turn on all warnings.
* Using multiple compilers on multiple operating systems will reveal portability issues that would otherwise
  go unnoticed.

Libraries
---------

**Use standard libraries**
* Your best bet to relying on the consistent behavior of a program is to use the standard libraries
  of the language.

Program Organization
--------------------

**Use only features available everywhere**
* A good approach is to use only those features that exist in all target systems.
* Prefer to assume that standard environments will features present in standard libraries,
  rather than provide band-aid fixes for environments in which certain files are not defined.

