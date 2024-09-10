## All Versions

- Build from a path that doesn't contain spaces. Otherwise you may get an error 9009 when executing `gendef`.

## Python 3.5

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Windows 8.1 SDK and Visual Studio 2015 build tools.
- Install SVN with command line tools from https://tortoisesvn.net/downloads.html.
- Build of installer works with Sphinx 1.7.9 for Python 3.5.5 to 3.5.7 and Sphinx 1.8.5 for Python 3.5.8 to 3.5.10. Install Sphinx into a Python 3.6 venv and set `SPHINXBUILD` to the path to `sphinx-build.exe`.
- Apply `build-full-installer-1.patch` to include debug symbols and debug binaries in the installer.
- Run `buildrelease.bat -x86 -x64`.

## Python 3.6

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Sphinx 1.8.5 to a Python 3.6 venv and set `SPHINXBUILD` to the path to `sphinx-build.exe`.
- Due to a bug in build scripts (https://github.com/python/cpython/issues/79555), set `HTMLHELP` to the path to `hhc.exe` in `externals\windows-installer\htmlhelp`.
- Install Windows SDK 10.0.10586.212.
- Apply `build-full-installer-1.patch` to include debug symbols and debug binaries in the installer.
- Apply `fix-test_winconsole.patch` to fix a hang during PGO profile generation (https://github.com/python/cpython/issues/85895).
- Run `buildrelease.bat -x86 -x64`.

## Python 3.7

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Sphinx 2.4.5 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `build-full-installer-2.patch` to include debug symbols and debug binaries in the installer.
- Apply `fix-htmlhelp.patch` to fix error in documentation build (https://github.com/python/cpython/issues/90621).
- Apply `fix-test_winconsole.patch` to fix a hang during PGO profile generation (https://github.com/python/cpython/issues/85895).
- Run `buildrelease.bat -x86 -x64`.

## Python 3.8

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Sphinx 2.4.5 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `fix-libffi-1.patch` for 3.8.11 or `fix-libffi-2.patch` for 3.8.12 to avoid error where `libffi-7.lib` can't be found (https://github.com/python/cpython/pull/27982).
- Apply `build-full-installer-2.patch` to include debug symbols and debug binaries in the installer.
- Apply `fix-htmlhelp.patch` to fix error in documentation build (https://github.com/python/cpython/issues/90621).
- Apply `fix-chm.patch` to fix formatting errors in the `.chm` help file (https://github.com/python/cpython/issues/91207).
- Run `buildrelease.bat -x86 -x64`.

## Python 3.9

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Sphinx 3.5.4 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `build-full-installer-3.patch` to include debug symbols, debug binaries, and the Universal CRT in the installer.
- Apply `fix-guid.patch` to work around https://github.com/python/cpython/issues/96729.
- Apply `fix-chm.patch` to fix formatting errors in the `.chm` help file (https://github.com/python/cpython/issues/91207).
- Run `buildrelease.bat -x86 -x64`.

## Python 3.10

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Sphinx 3.5.4 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `build-full-installer-4.patch` to include debug symbols, debug binaries, and the Universal CRT in the installer.
- Apply `fix-vcruntime-threads.patch` to fix https://github.com/python/cpython/issues/115167.
- Run `buildrelease.bat -x86 -x64`.

## Python 3.11

- Create a Python 3.10 venv and set `PYTHON` to the location of the Python executable.
- Apply `build-full-installer-5.patch` to include debug symbols, debug binaries, and the Universal CRT in the installer.
- Apply `enable-arm64-zip-nupkg.patch` to enable building the ARM64 embeddable ZIP file and the ARM64 NuGet package file. This also fixes https://github.com/python/cpython/issues/123915.
- Run `buildrelease.bat -x86 -x64 -arm64`.
