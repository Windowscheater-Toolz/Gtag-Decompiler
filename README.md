# Gtag Decompiler

![Stars](https://img.shields.io/github/stars/Windowscheater-Toolz/Gtag-Decompiler?style=for-the-badge)
![Forks](https://img.shields.io/github/forks/Windowscheater-Toolz/Gtag-Decompiler?style=for-the-badge)
![Issues](https://img.shields.io/github/issues/Windowscheater-Toolz/Gtag-Decompiler?style=for-the-badge)
![License](https://img.shields.io/github/license/Windowscheater-Toolz/Gtag-Decompiler?style=for-the-badge)

Lightweight .NET decompiler built for quickly browsing and exporting source code from managed assemblies.

## Features

* Open .NET DLL files
* Browse namespaces, classes, and methods
* Export decompiled C# source
* Automatic namespace folder sorting
* Fast loading and exporting
* Standalone executable
* Clean dark UI

## Usage

1. Open a DLL
2. Wait for the assembly to load
3. Browse the contents
4. Export the generated source

Exported files are automatically organized by namespace.

## Screenshot

![Decompiler Preview](https://github.com/user-attachments/assets/3955a74e-4aaa-4032-a536-a8b0960a8f3a)

## Installation

Download the latest release from the Releases page.

### Supported Platforms

* Windows 10
* Windows 11

## Building

```bash
git clone https://github.com/Windowscheater-Toolz/Gtag-Decompiler.git
cd Gtag-Decompiler
dotnet build -c Release
```

Publish:

```bash
dotnet publish -c Release
```

## Contributing

Pull requests, bug reports, and suggestions are welcome.

## License

MIT License
