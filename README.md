# Emacs binaries for Android (ARM)

These binaries are based on Michał Zieliński's patches and build scripts available at https://github.com/zielmicha/emacs

I've patched the scripts to build Emacs as a PIE executable so that it will run under Android L (Lollipop).  Otherwise, there are no changes from Michał's work.  

## Installation

For installation instructions, see my blog post http://quoderat.megginson.com/2014/02/17/how-to-install-a-usable-emacs-in-android-feb-2014/

## License

Binaries are distributed under the same GPL license as Gnu Emacs (see LICENSE.txt). Michał's modified source code is available at https://github.com/zielmicha/emacs

## Known issues

* Tested only under Android L (Lollipop)
* Works in most terminals, but crashes JuiceSSH (reason unknown)
* Dates on ``*.elc`` files are earlier than dates on ``*.el`` files after running Michał's build scripts; you should probably fix that with something like
```
find /sdcard/emacs/lisp -name '*.elc' -print0 | xargs -0 touch
```
* You may need to copy additional terminal definitions into terminfo (e.g. "linux")
* Starts with the message "WARNING: linker: /data/local/bin/emacs.bin has text relocations. This is wasting memory and prevents security hardening. Please fix." -- this seems to be a common problem in Android L, and I have not yet found the right combination of GCC flags to fix it.


_David Megginson, Ottawa, Canada, 2015-05-26_
