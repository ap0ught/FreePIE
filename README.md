# FreePIE

Programmable Input Emulator for scripting, bridging, and emulating input devices on Windows.

[Download the latest installer](https://andersmalmgren.github.io/FreePIE/)<br>
[Browse the wiki and scripting reference](https://github.com/AndersMalmgren/FreePIE/wiki)

## Overview

FreePIE helps map hardware input to scripts and virtual devices for gaming, VR, remote control, and accessibility scenarios. Scripts use a Python-inspired syntax and can combine multiple devices through the GUI runtime.

The project is designed to be extended through core plugins and separately compiled plugin assemblies.

## Development

### Prerequisites

- Windows with Visual Studio 2019 or later, or equivalent MSBuild tooling
- .NET Framework 4.8 targeting pack
- NuGet CLI for restoring `packages.config` dependencies
- WiX Toolset if you need to build the installer

### Restore packages

```powershell
nuget restore FreePIE.sln
```

### Build the solution

```powershell
msbuild FreePIE.sln /m /p:Configuration=Release /p:Platform="Mixed Platforms"
```

### Run the test suites

```powershell
vstest.console.exe `
  FreePIE.Tests.Core\bin\Release\FreePIE.Tests.Core.dll `
  FreePIE.Tests.Core.Plugins\bin\Release\FreePIE.Tests.Core.Plugins.dll
```

## Security

- Review the repository security policy in [SECURITY.md](SECURITY.md)
- GitHub automation is configured for CodeQL code scanning and Dependabot dependency updates
- Please report vulnerabilities privately instead of opening public issues

## Contributing

Please use the wiki for scripting and plugin reference material, and keep changes targeted so legacy device integrations remain stable.

## License

FreePIE is licensed under GPLv2.
