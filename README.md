# C# Decompiler

This Decompiler is a small Windows tool for pulling readable source from managed assemblies. No solution to set up, no plugin maze — open the exe, queue your DLLs, hit Export, and you get a folder of `.cs` files (plus a zip) laid out by namespace.

Built on [ICSharpCode.Decompiler](https://github.com/icsharpcode/ILSpy). Ships as a single self-contained executable.

[![Release](https://img.shields.io/github/v/release/Windowscheater-Toolz/Gtag-Decompiler?style=flat-square)](https://github.com/Windowscheater-Toolz/Gtag-Decompiler/releases)
[![License: MIT](https://img.shields.io/github/license/Windowscheater-Toolz/Gtag-Decompiler?style=flat-square)](LICENSE)
[![Issues](https://img.shields.io/github/issues/Windowscheater-Toolz/Gtag-Decompiler?style=flat-square)](https://github.com/Windowscheater-Toolz/Gtag-Decompiler/issues)

---

## What it does

Most decompilers are fine if you want to poke at one type in a tree view. This one is aimed at the boring workflow: you have a pile of game or mod DLLs and you just want the source on disk, organized, without clicking through every namespace.

For each assembly it:

1. Reads the PE file and checks that it is actually .NET (native DLLs are skipped with a clear message).
2. Runs a quick protection/obfuscation check — heavily locked builds are rejected before wasting time on a bad export.
3. Decompiles the whole thing into an SDK-style C# project with nested namespace folders.
4. Packages the result into a `.zip` sitting next to the extracted folder.

You can queue multiple DLLs and export them in one go. The decompiler runs a few at a time in parallel so a batch of small assemblies does not crawl.

---

## Quick start

**GUI**

1. Download `GTagDecompiler.exe` from [Releases](https://github.com/Windowscheater-Toolz/Gtag-Decompiler/releases).
2. Run it. Drag DLLs onto the window, or use **File → Open assemblies**.
3. Pick an output folder (defaults to the install directory).
4. Press **Export** or `F5`.

**CLI**

Pass `--cli` (or `-c`) to skip the window and work from a terminal:

```powershell
GTagDecompiler.exe --cli MyMod.dll Another.dll -o C:\exports
```

With no paths on the command line, it drops into an interactive prompt — paste paths, empty line to run.

```powershell
GTagDecompiler.exe --cli -o C:\exports
```

`--help` / `-h` prints the full flag list.

---

## Output layout

Given `SomeAssembly.dll`, you get:

```
output/
├── SomeAssembly/          # full decompiled project
│   ├── SomeAssembly.csproj
│   ├── SomeAssembly.decompiled.cs   (if generated)
│   └── Namespace/
│       └── Folder/
│           └── Type.cs
└── SomeAssembly.zip       # same tree, zipped
```

Namespaces map to folders (`UseNestedDirectoriesForNamespaces` is on). The `.csproj` is SDK-style so you can open the folder in Visual Studio or Rider if you want to browse with IntelliSense.

---

## Features

| | |
|---|---|
| **Batch export** | Queue many DLLs, export in one run |
| **Drag and drop** | Drop files straight onto the main window |
| **Parallel jobs** | Multiple assemblies decompile at once (capped so the machine stays responsive) |
| **Zip per assembly** | Folder + zip for each successful export |
| **Protection check** | Skips or warns on obfuscated / locked builds instead of dumping garbage |
| **Dark UI** | WinForms, built for long sessions — console-style log, progress bar, cancel with `Esc` |
| **CLI mode** | Same engine, no GUI — useful for scripts and quick one-offs |
| **Standalone exe** | .NET runtime bundled; no separate install step on the target PC |

Keyboard shortcuts in the GUI: `Ctrl+O` open, `F5` export, `Esc` stop a running batch.

---

## What it won't do

Being straight about limits saves everyone time:

- **Native DLLs** — if it is not a .NET assembly, there is no C# to recover. You get told immediately.
- **Heavy obfuscation / commercial protectors** — the tool checks metadata and output quality and bails when the result would be useless. Paid or locked game builds often fall here.
- **Perfect source** — decompiled code is reconstructed IL. Names, control flow, and comments from the original project are gone. Treat output as reference material, not a drop-in replacement.
- **Missing dependencies** — if a DLL expects siblings beside it, keep them together or resolution can fail.

Partial exports sometimes come through with a warning that the source may still be messy. That is intentional — better a heads-up than silent junk.

---

## Requirements

- **Windows 10 or 11** (x64)
- Nothing else for the published build — runtime is included

---

## Building from source

You need the [.NET 10 SDK](https://dotnet.microsoft.com/download) on Windows.

```powershell
git clone https://github.com/Windowscheater-Toolz/Gtag-Decompiler.git
cd Gtag-Decompiler
dotnet build -c Release
```

Publish a release-style single file:

```powershell
dotnet publish -c Release
```

Or use the repo script — builds and publishes into `dist/`:

```powershell
.\build\pack.ps1
```

Output: `dist\GTagDecompiler.exe`

---

## Project layout

```
├── AppHost.csproj       # WinForms host, publish settings
├── src/
│   ├── k0/              # entry point, CLI
│   ├── k1/              # main window, rendering
│   ├── k2/              # splash / loading
│   ├── k3/              # theme, UI helpers
│   ├── k4/              # settings, localization
│   └── k5/              # decompiler pipeline, assembly reader
├── build/pack.ps1       # one-shot publish script
└── res/                 # icon, assets
```

Decompilation logic lives in `src/k5/Pipeline.cs` (`Decompiler` class). UI is standard WinForms — no WPF, no Electron.

---

## Contributing

Bug reports, PRs, and "this DLL should work but doesn't" issues are welcome. If something fails, include the DLL name (or a redacted sample), what you expected, and the message from the console log — that helps a lot.

---

## License

[MIT](LICENSE)
