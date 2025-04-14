## Python 3.5

- Build from a path that doesn't contain spaces. Otherwise you may get an error 9009 when executing `gendef`.
- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install [HTML Help Compiler](http://web.archive.org/web/20160201063255/http://download.microsoft.com/download/0/A/9/0A939EF6-E31C-430F-A3DF-DFAE7960D564/htmlhelp.exe) system-wide, which would register this DLL anyway.
- Install [Windows SDK 10.0.15063.468](https://go.microsoft.com/fwlink/p/?LinkId=845298), which is the latest version that is compatible with Tcl/Tk (https://core.tcl-lang.org/tk/tktview/9e31fd9449). It is OK to have a newer Windows SDK installed as well, in which case Windows SDK 10.0.15063.468 is used to build Tcl/Tk only while the newest installed Windows SDK is used for other components.
- Install Sphinx 1.7.9 for 3.5.5-3.5.7 or Sphinx 1.8.5 for 3.5.8-3.5.10 into a Python 3.6 venv and set `SPHINXBUILD` to the path to `sphinx-build.exe`.
- Apply `support-vs-2022-1.patch` to support building with Visual Studio 2022 using the v143 toolset and to avoid an issue where Tcl/Tk is not compatible with the Windows 11 SDK (derived from https://github.com/python/cpython/commit/0e4ad88ff8956d9289ab0a1314636ac15b374459, https://github.com/python/cpython/commit/eede148296bf3b4578b92ed6a07f2733a0f1c341, https://github.com/python/cpython/commit/c05e491a69df3fe0a8be91eeddd330792ada6755, https://github.com/python/cpython/commit/d9301703fb1086cafbd730c17e3d450a192485d6 and https://github.com/python/cpython/commit/45faf151c693b6f13f78926761caea6df7242024).
- Apply `get-dependencies-from-github.patch` to get external dependencies from GitHub instead of the old SVN repository at https://svn.python.org/projects/python/externals, which no longer exists (derived from https://github.com/python/cpython/commit/04431c926a88be433203f89e3577addd0d41b602). Dependencies are pulled from https://github.com/python/cpython-source-deps and https://github.com/python/cpython-bin-deps. However, some old versions of dependencies predate the migration to GitHub, so they are instead pulled from https://github.com/adang1345/cpython-source-deps and https://github.com/adang1345/cpython-bin-deps.
- Apply `build-full-installer-1.patch` to include debug symbols and debug binaries in the installer.
- Run `buildrelease.bat`.

## Python 3.6

- Build from a path that doesn't contain spaces. Otherwise you may get an error 9009 when executing `gendef`.
- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install [HTML Help Compiler](http://web.archive.org/web/20160201063255/http://download.microsoft.com/download/0/A/9/0A939EF6-E31C-430F-A3DF-DFAE7960D564/htmlhelp.exe) system-wide, which would register this DLL anyway.
- Install [Windows SDK 10.0.15063.468](https://go.microsoft.com/fwlink/p/?LinkId=845298), which is the latest version that is compatible with Tcl/Tk (https://core.tcl-lang.org/tk/tktview/9e31fd9449). It is OK to have a newer Windows SDK installed as well, in which case Windows SDK 10.0.15063.468 is used to build Tcl/Tk only while the newest installed Windows SDK is used for other components.
- Install Sphinx 2.4.5 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `support-vs-2022-2.patch` to support building with Visual Studio 2022 using the v143 toolset and the Windows 11 SDK. Also avoid an issue where Tcl/Tk is not compatible with the Windows 11 SDK. (Derived from https://github.com/python/cpython/commit/30f4fa456ef626ad7a92759f492ec7a268f7af4e, https://github.com/python/cpython/commit/c83ec055a09137e4b24f70e3bb5f887dc0ae6e8e, https://github.com/python/cpython/commit/cba5ddf088683859dd022d04cb3726d56f5f0297, https://github.com/python/cpython/commit/df4852cbe4b757e8b79506d73a09ec8a1b595970, https://github.com/python/cpython/commit/0e4ad88ff8956d9289ab0a1314636ac15b374459, https://github.com/python/cpython/commit/eede148296bf3b4578b92ed6a07f2733a0f1c341, https://github.com/python/cpython/commit/c05e491a69df3fe0a8be91eeddd330792ada6755, https://github.com/python/cpython/commit/d9301703fb1086cafbd730c17e3d450a192485d6, and https://github.com/python/cpython/commit/45faf151c693b6f13f78926761caea6df7242024. Also used the suggestion at https://github.com/python/cpython/issues/84133#issuecomment-1093865746.)
- Apply `fix-hhc.patch` to fix error calling the HTML Help Compiler (https://github.com/python/cpython/issues/79555).
- Apply `fix-htmlhelp.patch` to fix error in documentation build (https://github.com/python/cpython/issues/90621).
- Apply `build-full-installer-2.patch` to include debug symbols and debug binaries in the installer.
- Apply `fix-test_winconsole.patch` to fix a hang during PGO profile generation (https://github.com/python/cpython/issues/85895).
- Run `buildrelease.bat`.

## Python 3.7

- Build from a path that doesn't contain spaces. Otherwise you may get an error 9009 when executing `gendef`.
- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install [HTML Help Compiler](http://web.archive.org/web/20160201063255/http://download.microsoft.com/download/0/A/9/0A939EF6-E31C-430F-A3DF-DFAE7960D564/htmlhelp.exe) system-wide, which would register this DLL anyway.
- Install Sphinx 2.4.5 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `support-vs-2022-3.patch` to support building with Visual Studio 2022 using the v143 toolset and the Windows 11 SDK (derived from https://github.com/python/cpython/commit/d9301703fb1086cafbd730c17e3d450a192485d6 and https://github.com/python/cpython/commit/45faf151c693b6f13f78926761caea6df7242024).
- Apply `build-full-installer-3.patch` to include debug symbols and debug binaries in the installer.
- Apply `fix-htmlhelp.patch` to fix error in documentation build (https://github.com/python/cpython/issues/90621).
- Apply `fix-test_winconsole.patch` to fix a hang during PGO profile generation (https://github.com/python/cpython/issues/85895).
- Apply `fix-ucrt-1.patch` for 3.7.13 or higher to fix error installing Universal C Runtime (https://github.com/python/cpython/issues/138896).
- Run `buildrelease.bat`.

## Python 3.8

- Build from a path that doesn't contain spaces. Otherwise you may get an error 9009 when executing `gendef`.
- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install [HTML Help Compiler](http://web.archive.org/web/20160201063255/http://download.microsoft.com/download/0/A/9/0A939EF6-E31C-430F-A3DF-DFAE7960D564/htmlhelp.exe) system-wide, which would register this DLL anyway.
- Install Sphinx 2.4.5 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `support-vs-2022-4.patch` for 3.8.11-3.8.12 or `support-vs-2022-5.patch` for 3.8.13 or higher to support building with Visual Studio 2022 using the v143 toolset and the Windows 11 SDK (derived from https://github.com/python/cpython/commit/d9301703fb1086cafbd730c17e3d450a192485d6 and https://github.com/python/cpython/commit/45faf151c693b6f13f78926761caea6df7242024).
- Apply `fix-libffi-1.patch` for 3.8.11 or `fix-libffi-2.patch` for 3.8.12 to avoid error where `libffi-7.lib` can't be found (https://github.com/python/cpython/pull/27982).
- Apply `build-full-installer-3.patch` to include debug symbols and debug binaries in the installer.
- Apply `fix-htmlhelp.patch` to fix error in documentation build (https://github.com/python/cpython/issues/90621).
- Apply `fix-chm.patch` to fix formatting errors in the `.chm` help file (https://github.com/python/cpython/issues/91207).
- Apply `fix-vcruntime-threads.patch` to fix https://github.com/python/cpython/issues/115167.
- Apply `fix-ucrt-1.patch` for 3.8.13 or higher to fix error installing Universal C Runtime (https://github.com/python/cpython/issues/138896).
- Run `buildrelease.bat`.

## Python 3.9

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install [HTML Help Compiler](http://web.archive.org/web/20160201063255/http://download.microsoft.com/download/0/A/9/0A939EF6-E31C-430F-A3DF-DFAE7960D564/htmlhelp.exe) system-wide, which would register this DLL anyway.
- Install Sphinx 3.5.4 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `support-vs-2022-6.patch` to support building with Visual Studio 2022 using the v143 toolset and the Windows 11 SDK (derived from https://github.com/python/cpython/commit/d9301703fb1086cafbd730c17e3d450a192485d6 and https://github.com/python/cpython/commit/45faf151c693b6f13f78926761caea6df7242024).
- Apply `build-full-installer-4.patch` to include debug symbols, debug binaries, and the Universal CRT in the installer.
- Apply `fix-guid.patch` to fix https://github.com/python/cpython/issues/96729.
- Apply `fix-chm.patch` to fix formatting errors in the `.chm` help file (https://github.com/python/cpython/issues/91207).
- Apply `fix-vcruntime-threads.patch` to fix https://github.com/python/cpython/issues/115167.
- Apply `fix-ucrt-1.patch` to fix error installing Universal C Runtime (https://github.com/python/cpython/issues/138896).
- Run `buildrelease.bat`.

## Python 3.10

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install [HTML Help Compiler](http://web.archive.org/web/20160201063255/http://download.microsoft.com/download/0/A/9/0A939EF6-E31C-430F-A3DF-DFAE7960D564/htmlhelp.exe) system-wide, which would register this DLL anyway.
- Install Sphinx 3.5.4 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `build-full-installer-5.patch` to include debug symbols, debug binaries, and the Universal CRT in the installer.
- Apply `fix-vcruntime-threads.patch` to fix https://github.com/python/cpython/issues/115167.
- Apply `fix-ucrt-1.patch` to fix error installing Universal C Runtime (https://github.com/python/cpython/issues/138896).
- Run `buildrelease.bat`.

## Python 3.11

- Create a Python 3.10 venv and set `PYTHON` to the location of the Python executable.
- Apply `build-full-installer-6.patch` to include debug symbols, debug binaries, and the Universal CRT in the installer.
- Apply `enable-arm64-zip-nupkg-1.patch` to enable building the ARM64 embeddable ZIP file and the ARM64 NuGet package file. This also fixes https://github.com/python/cpython/issues/123915.
- Apply `fix-ucrt-2.patch` to fix error installing Universal C Runtime (https://github.com/python/cpython/issues/138896).
- Run `buildrelease.bat -x86 -x64 -arm64`.

## Python 3.12

- Create a Python 3.11 venv and set `PYTHON` to the location of the Python executable.
- Apply `build-full-installer-6.patch` to include debug symbols, debug binaries, and the Universal CRT in the installer.
- Apply `enable-arm64-zip-nupkg-2.patch` to enable building the ARM64 embeddable ZIP file and the ARM64 NuGet package file.
- Apply `fix-ucrt-2.patch` to fix error installing Universal C Runtime (https://github.com/python/cpython/issues/138896).
- Run `buildrelease.bat -x86 -x64 -arm64`.
