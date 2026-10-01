# Unofficial Python Security Updates for Windows

For older Python versions in the *security* maintenance status, https://www.python.org/ officially releases only the source code and no installers. But what if you want an easy way to install these versions on Windows? Here, you can obtain unofficial Windows installers for security updates of Python 3.5 and higher.

### Links to Latest Versions

[3.12.15](https://github.com/adang1345/PythonWindows/releases/tag/v3.12.15) &nbsp;
[3.11.17](https://github.com/adang1345/PythonWindows/releases/tag/v3.11.17) &nbsp;
[3.10.22](https://github.com/adang1345/PythonWindows/releases/tag/v3.10.22) &nbsp;
[3.9.25](https://github.com/adang1345/PythonWindows/releases/tag/v3.9.25) &nbsp;
[3.8.20](https://github.com/adang1345/PythonWindows/releases/tag/v3.8.20) &nbsp;
[3.7.17](https://github.com/adang1345/PythonWindows/releases/tag/v3.7.17) &nbsp;
[3.6.15](https://github.com/adang1345/PythonWindows/releases/tag/v3.6.15) &nbsp;
[3.5.10](https://github.com/adang1345/PythonWindows/releases/tag/v3.5.10)

---

For each Python version, this repository includes the following.

- AMD64 executable installer (e.g. python-3.5.5-amd64-full.exe)
- x86 executable installer (e.g. python-3.5.5-full.exe)
- ARM64 executable installer (e.g. python-3.11.10-arm64-full.exe) (since 3.11)
- AMD64 embeddable zip file (e.g. python-3.5.5-embed-amd64.zip)
- x86 embeddable zip file (e.g. python-3.5.5-embed-win32.zip)
- ARM64 embeddable zip file (e.g. python-3.11.10-embed-arm64.zip) (since 3.11)
- AMD64 NuGet package (e.g. python.3.5.5.nupkg)
- x86 NuGet package (e.g. pythonx86.3.5.5.nupkg)
- ARM64 NuGet package (e.g. pythonarm64.3.11.10.nupkg) (since 3.11)
- Windows help file (e.g. python355.chm) (3.5 to 3.10 only)

These installers were built from the source distributions published at https://www.python.org/downloads/source/, patched to fix some bugs in the build scripts and to include all components to allow for a fully-offline installation. For the more technical among you, see [Notes.md](Notes.md) for further information about how I built the installers and how you may build them yourself.

## NuGet Packages

To install a `.nupkg` package, ensure that you have the [NuGet Command-Line Interface](https://learn.microsoft.com/en-us/nuget/reference/nuget-exe-cli-reference?tabs=windows) installed. Go to the directory containing the `.nupkg` file. Replace `target\installation\directory` in the following commands with the desired location to install the package.

### Command Prompt
For 64-bit Python, run `nuget install python -Source %cd% -OutputDirectory target\installation\directory`

For 32-bit Python, run `nuget install pythonx86 -Source %cd% -OutputDirectory target\installation\directory`

### PowerShell
For 64-bit Python, run `nuget install python -Source $(Get-Location) -OutputDirectory target\installation\directory`

For 32-bit Python, run `nuget install pythonx86 -Source $(Get-Location) -OutputDirectory target\installation\directory`

## History

The project history is recorded at [CHANGELOG.md](CHANGELOG.md).

## License

These files are provided under the MIT License. See [LICENSE.txt](LICENSE.txt).
