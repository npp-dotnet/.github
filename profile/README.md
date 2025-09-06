<!-- SPDX-FileCopyrightText: Public Domain -->
<!-- SPDX-License-Identifier: CC0-1.0  -->

## Npp... .NET?

Notepad++ is a traditional Win32 app. The one [officially supported plugin template](https://github.com/npp-plugins/plugintemplate#readme) assumes a working knowledge of C++ and the Win32 messaging API.

For now, the only viable option for .NET plugin developers is to target .NET Framework. A compatible runtime is always guaranteed, since the Windows operating system depends on it. Great for end-user experience, less so for developers accustomed to recent C# language features, for whom ".NET" means the [SDK](https://dotnet.microsoft.com) targeting multiple platforms and devices.

The availability of modern .NET frameworks on end-user machines is not the entire problem. Any .NET assembly, regardless of framework, is useless to Notepad++ without modifying the binary to make it "look like" a native executable. Until recently, the only way to hack around this limitation involved running a post-build task provided by Rob Giesecke's unmaintained [MSBuild extension library](https://www.nuget.org/packages/UnmanagedExports). The only [.NET plugin template](https://github.com/molsonkiko/NppCSharpPluginPack) still under active development has upgraded this dependency to a relatively newer one. But the post-processing step remains as critical and error-prone as ever.

This organization is a laboratory for experimental projects looking to bridge the gap between a legacy code base and cutting-edge tooling. The goal is to enable future plugin authors to start new projects as easily as typing `dotnet new ...` into a terminal.

To learn more, read about [how you can contribute](../CONTRIBUTING.md), or browse the [NuGet feed](https://www.nuget.org/profiles/Npp.NET).
