## 10 October 2025

- Add 3.9.24, 3.10.19, 3.11.14, and 3.12.12.

## 16 September 2025

- Rebuild Python 3.7.13-3.7.17, 3.8.13-3.8.20, and 3.9-3.12 to fix error installing Universal C Runtime (https://github.com/python/cpython/issues/138896).

## 13 September 2025

- Rebuild Python 3.5-3.6 to include the correct version of `vcruntime140.dll` in the NuGet and embeddable packages.

## 7 September 2025

- Remove note that Python 3.5 is no longer possible to build.
- Given that https://svn.python.org/projects/python/externals no longer exists, create https://github.com/adang1345/cpython-source-deps and https://github.com/adang1345/cpython-bin-deps to hold external dependencies that Python 3.5 requires that were never migrated from SVN to GitHub.
- Rebuild Python 3.5 using Visual Studio 2022 and the Windows 11 SDK. Patch the build script to pull some external dependencies from https://github.com/adang1345/cpython-source-deps and https://github.com/adang1345/cpython-bin-deps. Use Windows SDK 10.0.15063.468 to build the Tcl/Tk external dependency.
- Update patch for Python 3.6 to use Windows SDK 10.0.15063.468 when building the Tcl/Tk external dependency instead of downloading a pre-built version. Rebuild Python 3.6.

## 2 September 2025

- Remove `index` lines from patch files. They are unnecessary.

## 29 August 2025

- Rebuild Python 3.6+ using Visual Studio 2022 and the Windows 11 SDK. Update patches to fix any incompatibilities with the newer compiler and SDK.
- Add note that Python 3.5 is no longer possible to build.
- Change the note to build from a path without spaces. This requirement applies to versions under 3.9 only and not all versions.

## Previous

- This project's history was not recorded until 29 August 2025.
