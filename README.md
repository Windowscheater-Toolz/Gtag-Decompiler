
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
<img width="797" height="475" alt="4873473478437478374834783dhfduyhfduyhfduyfhdf" src="https://github.com/user-attachments/assets/9eeb62c8-08d9-45d2-b7ce-978b25bcc9e6" />
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
