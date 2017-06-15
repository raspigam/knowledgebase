# Compiling the Elm compiler

Elm is a programming language that compiles Elm code into very robust Javascript.
Its compiler is created in Haskell, another language for Functional Programming.
The Functional Programming approach greatly reduces (run time) errors, because it involves a strictness enabling the compiler to catch a lot of mistakes up-front.
Also, it can reduce mental overhead. The latter is true in particular for Elm, because amongst the Functional Programming languages, Elm is probably simplest while still very powerful.

## Installing Haskell

Following the instructions at https://medium.com/@zw3rk/a-haskell-cross-compiler-for-raspberry-pi-ddd9d41ced94 as compiling from source with Stack broke at installing Cabal, possibly due to memory issues.

```
$ stack -v install cabal-install
...
2017-06-15 10:21:28.808670: [debug] Exception ignored when attempting to load /home/pi/.stack/precompiled/arm-linux/ghc-7.10.3/1.22.5.0/mtl-2.2.1/ZVTYqqJ8A0VdVHgKToukNwAIYBaW7unCvafaM-R4J5c=: /home/pi/.stack/precompiled/arm-linux/ghc-7.10.3/1.22.5.0/mtl-2.2.1/ZVTYqqJ8A0VdVHgKToukNwAIYBaW7unCvafaM-R4J5c=: openBinaryFile: does not exist (No such file or directory)
...
```
After a whole load of ignores the process just stops, not consuming any resources, just hangs. Ctrl-c gives `PrProgress: 4/11user interrupt`.

Get the latest GHC at http://downloads.haskell.org/~ghc/latest (which linked in my case to ghc version 8.0.1).
I got this one: http://downloads.haskell.org/~ghc/latest/ghc-8.0.1-armv7-deb8-linux.tar.xz
Maybe important to mention as this is a non-https link, you should verify [sha checksums](verify-sha-sum.md) and [signatures](verify-sig.md).
I could not find out so far how to get to these downloads from the main https://www.haskell.org site - I got the link from helpful people on the #elm-dev Slack channel.

[Unpack](unpack-compressed-files.md) the downloaded files and [navigate to the directory](navigate-directories.md) where it got extracted to: You can [read](read-text-files.md) the file `INSTALL` for instructions.

```
$ ./configure
checking for path to top of build tree...
...
checking for ranlib... ranlib
configure: creating ./config.status
config.status: creating settings
config.status: creating mk/config.mk
config.status: creating mk/install.mk
****************************************************
Configuration done, ready to 'make install'
(see README and INSTALL files for more info.)
****************************************************
```

Note that the INSTALL readme mentions the availability of a `make show-install-setup` which seems not true, I should ask the Haskell packagers. Performing `make install` requires [sudo rights](run-with-sudo.md).

```
$ sudo make install
make --no-print-directory -f ghc.mk install BINDIST=YES NO_INCLUDE_DEPS=YES
/usr/bin/install -c -m 755 -d "/usr/local/bin"
"rm" -f                                 "/usr/local/bin/ghci-8.0.1"  
create () { touch "$1" && chmod 755 "$1" ; } && create                                   "/usr/local/bin/ghci-8.0.1"
...
Registering ghc-8.0.1...
for f in '/usr/local/lib/ghc-8.0.1/package.conf.d'/*; do create () { touch "$1" && chmod 644 "$1" ; } && create "$f"; done
/usr/bin/install -c -m 755 -d "/usr/local/bin"
for i in utils/hp2ps/dist/build/tmp/hp2ps; do \
	/usr/bin/install -c -m 755  $i "/usr/local/bin" ;  \
done
/usr/bin/install -c -m 755 -d "/usr/local/lib/ghc-8.0.1/bin"
for i in inplace/lib/bin/ghc-split; do \
	/usr/bin/install -c -m 755  $i "/usr/local/lib/ghc-8.0.1/bin"; \
done
/usr/bin/install -c -m 755 -d "/usr/local/share/doc/ghc-8.0.1"
/usr/bin/install -c -m 755 -d "/usr/local/share/doc/ghc-8.0.1/html"
/usr/bin/install -c -m 644  docs/index.html "/usr/local/share/doc/ghc-8.0.1/html"
/usr/bin/install -c -m 755 -d "/usr/local/share/doc/ghc-8.0.1/html/libraries"
for i in libraries/dist-haddock/*; do \
	/usr/bin/install -c -m 644  $i "/usr/local/share/doc/ghc-8.0.1/html/libraries/"; \
done
/usr/bin/install -c -m 644  libraries/prologue.txt "/usr/local/share/doc/ghc-8.0.1/html/libraries/"
/usr/bin/install -c -m 755  libraries/gen_contents_index "/usr/local/share/doc/ghc-8.0.1/html/libraries/"
for i in utils/haddock/doc/haddock docs/users_guide/build-html/users_guide; do \
	cp -Rp $i "/usr/local/share/doc/ghc-8.0.1/html"; \
done
```
