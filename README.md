[![Release](https://img.shields.io/github/v/release/Windowcheater-Tools/CDecompiler)](https://github.com/Windowcheater-Tools/CDecompiler/releases)

[![Downloads](https://img.shields.io/github/downloads/Windowcheater-Tools/CDecompiler/total)](https://github.com/Windowcheater-Tools/CDecompiler/releases)

[![Stars](https://img.shields.io/github/stars/Windowcheater-Tools/CDecompiler)](https://github.com/Windowcheater-Tools/CDecompiler/stargazers)

[![Issues](https://img.shields.io/github/issues/Windowcheater-Tools/CDecompiler)](https://github.com/Windowcheater-Tools/CDecompiler/issues)

[![License](https://img.shields.io/github/license/Windowcheater-Tools/CDecompiler)](https://github.com/Windowcheater-Tools/CDecompiler/blob/main/LICENSE)
# Gtag Decompiler

A simple and fast .NET decompiler built for quickly viewing and exporting source code from assemblies.

## Features

- Open DLL Files
- Browse namespaces, classes, and methods
- Export decompiled source code
- Automatic folder organization
- Fast loading and exporting
- Standalone executable
- Dark, clean interface

## How It Works

 Decompiler loads a .NET assembly, reads its metadata, and reconstructs readable C# code.

1. Open a DLL
2. Let the assembly load
3. Browse the contents
4. Export the generated source

The exported files are automatically sorted into folders based on their namespaces.

## Installation

Download the latest release from the Releases page.

The standalone version does not require a separate .NET installation.

Supported platforms:

- Windows 10
- Windows 11

## Screenshots

Add screenshots here.

```md
![Main Window](images/main.png)
```

## Building

Clone the repository:

```bash
git clone https://github.com/USERNAME/VDecompiler.git
```

Build using:

```bash
dotnet build -c Release
```

Publish:

```bash
dotnet publish -c Release
```

## Why I Made This

Most decompilers either felt bloated or had interfaces that were difficult to navigate. Decompiler was made to provide a cleaner experience while keeping everything fast and straightforward.

## Contributing

Pull requests are welcome.

If you find a bug or have a suggestion, open an issue.

## License

MIT License
