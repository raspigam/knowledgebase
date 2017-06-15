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
...
$ make install
...
```
