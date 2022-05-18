# alut-glitch
Reproduces an error found when building a haskell program using Sound.ALUT.
You can reproduce the problem by issues the following commands on a Windows 10 system.

```
git clone https://github.com/markcornwell/alut-glitch
cd alut-glitch
stack exec -- pacman -S mingw-w64-x86_64-openal
stack exec -- pacman -S mingw-w64-x86_64-freealut
stack build
stack run
```
The error looks like this:
```
C:\Users\Mark\alut-glitch>stack build
OpenAL     > configure
OpenAL     > Configuring OpenAL-1.7.0.5...
OpenAL     > Cabal-simple_Z6RU0evB_3.2.1.0_ghc-8.10.7.exe: Missing dependency on a foreign
OpenAL     > library:
OpenAL     > * Missing (or bad) C library: OpenAL32
OpenAL     > This problem can usually be solved by installing the system package that
OpenAL     > provides this library (you may need the "-dev" version). If the library is
OpenAL     > already installed but in a non-standard location then you can use the flags
OpenAL     > --extra-include-dirs= and --extra-lib-dirs= to specify where it is.If the
OpenAL     > library file does exist, it may contain errors that are caught by the C
OpenAL     > compiler at the preprocessing stage. In this case you can re-run configure
OpenAL     > with the verbosity flag -v3 to see the error messages.
OpenAL     >
Progress 0/3: OpenAL

--  While building package OpenAL-1.7.0.5 (scroll up to its section to see the error) using:
      C:\sr\setup-exe-cache\x86_64-windows\Cabal-simple_Z6RU0evB_3.2.1.0_ghc-8.10.7.exe --builddir=.stack-work\dist\274b403a configure --with-ghc=C:\Users\Mark\AppData\Local\Programs\stack\x86_64-windows\ghc-8.10.7\bin\ghc-8.10.7.exe --with-ghc-pkg=C:\Users\Mark\AppData\Local\Programs\stack\x86_64-windows\ghc-8.10.7\bin\ghc-pkg.exe --user --package-db=clear --package-db=global --package-db=C:\sr\snapshots\87ecdd59\pkgdb --libdir=C:\sr\snapshots\87ecdd59\lib --bindir=C:\sr\snapshots\87ecdd59\bin --datadir=C:\sr\snapshots\87ecdd59\share --libexecdir=C:\sr\snapshots\87ecdd59\libexec --sysconfdir=C:\sr\snapshots\87ecdd59\etc --docdir=C:\sr\snapshots\87ecdd59\doc\OpenAL-1.7.0.5 --htmldir=C:\sr\snapshots\87ecdd59\doc\OpenAL-1.7.0.5 --haddockdir=C:\sr\snapshots\87ecdd59\doc\OpenAL-1.7.0.5 --dependency=ObjectName=ObjectName-1.1.0.2-DuEbzYljkktH7U5m2bwpk2 --dependency=OpenGL=OpenGL-3.0.3.0-HWRKYgbN7MeKxBFtoCd3zw --dependency=StateVar=StateVar-1.2.2-E5VfLD39xuSBKKtL6sMcfd --dependency=base=base-4.14.3.0 --dependency=transformers=transformers-0.5.6.2 -f-buildexamples -fusenativewindowslibraries --extra-include-dirs=C:\Users\Mark\AppData\Local\Programs\stack\x86_64-windows\msys2-20220503\mingw64\include --extra-lib-dirs=C:\Users\Mark\AppData\Local\Programs\stack\x86_64-windows\msys2-20220503\mingw64\lib --extra-lib-dirs=C:\Users\Mark\AppData\Local\Programs\stack\x86_64-windows\msys2-20220503\mingw64\bin --exact-configuration --ghc-option=-fhide-source-paths
    Process exited with code: ExitFailure 1

C:\Users\Mark\alut-glitch>

```
