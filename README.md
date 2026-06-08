# Gtag Decompiler

Lightweight .NET decompiler for quickly viewing, browsing, and exporting source code from managed assemblies.

![Stars](https://img.shields.io/github/stars/Windowcheater-Tools/CDecompiler)
![License](https://img.shields.io/github/license/Windowcheater-Tools/CDecompiler)
![Issues](https://img.shields.io/github/issues/Windowcheater-Tools/CDecompiler)

## Features

* Open and inspect .NET DLLs
* Browse namespaces, classes, methods, and fields
* Export decompiled C# source
* Automatic namespace-based folder structure
* Fast assembly loading
* Standalone executable
* Simple dark-themed interface

## Usage

1. Open a .NET assembly (.dll)
2. Wait for the assembly to load
3. Browse the available types and members
4. Export the generated source code

Exported files are automatically organized by namespace.

## Screenshots

<img width="797" alt="Decompiler Preview" src="https://github.com/user-attachments/assets/3955a74e-4aaa-4032-a536-a8b0960a8f3a" />

## Installation

Download the latest release from the Releases page.

### Supported Operating Systems

* Windows 10
* Windows 11

No additional installation is required for the standalone build.

## Building

Clone the repository:

```bash
git clone https://github.com/USERNAME/GtagDecompiler.git
cd GtagDecompiler
```

Build:

```bash
dotnet build -c Release
```

Publish:

```bash
dotnet publish -c Release
```

## Why?

Most decompilers are packed with features many people never use. Gtag Decompiler focuses on the basics: opening assemblies, viewing code, and exporting source as quickly as possible.

## Contributing

Issues, suggestions, and pull requests are welcome.

## License

Released under the MIT License.
