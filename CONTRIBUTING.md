<!-- SPDX-FileCopyrightText: Public Domain -->
<!-- SPDX-License-Identifier: CC0-1.0 -->

Thanks for your interest in contributing!

This document explains the areas of project development where help is most needed.

Feel free to [start a discussion](https://github.com/orgs/npp-dotnet/discussions/new) if you're interested in something not listed below.


### 🔄 CI/CD

Plugins using the `Npp.DotNet.Plugin` package have access to hundreds of methods that directly interact with Notepad++ and the [Scintilla](https://www.scintilla.org/ScintillaDoc.html) editing component.

At the moment, the API surface receives only minimal testing. A stable version of the package depends largely on improving test coverage.

#### 🔬 Unit testing

.NET Framework versions of the template were not fully compatible with 64-bit applications and suffered from memory safety issues.
The modern .NET version fixes many of these problems, but some old bugs (as well as new ones) probably remain.

If you would like to fix a memory safety bug affecting 64-bit Notepad++ (ARM or x64), use the current [unit tests] as a guide to validating your changes.

> [!Note]
> 32-bit x86 is a [supported] native target in .NET 9 and later. However, cross-compiling for a legacy architecture is not a goal of this project.

#### ♾️ Integration testing, or "[E2E](https://www.softwaretestingmaterial.com/end-to-end-testing)"

There are many, *many* untested Scintilla[^1] and Notepad++[^2] gateway methods in the template library.
A real-world plugin project using *every method* at least once is needed to make sure the API is fully functional.

#### ☔ Code coverage

Each line of code executed during a test run should be tracked in order to measure the progress of our testing efforts.
If you know a good coverage tool for C#, please open a pull request to have it integrated with the [build workflow].


### 🛠️ Tooling

Microsoft releases a new major version of the .NET SDK every year. They also publish preview versions of the forthcoming release at regular intervals.
Building the template library with a preview SDK can help identify potential improvements or breakages ahead of time.


### 📝 Documentation

If you encountered problems installing, building, or using the template, consider writing a tutorial for the [documentation website], explaining the issue and (if applicable) how you worked around it.
Write your docs in Markdown and add them to the [table of contents] by updating the [documentation workflow]. Learn about [DocFX] if you're not familiar with it.

Found an open source project using the template? Suggest adding it to the [README].


### 🪪 Project management

If you'd like to help maintain a repository in the Npp.NET GitHub organization, ask to become [a member](https://github.com/orgs/npp-dotnet/people).


[^1]: https://npp-dotnet.github.io/Npp.DotNet.Plugin/api/Npp.DotNet.Plugin.ScintillaGateway.html
[^2]: https://npp-dotnet.github.io/Npp.DotNet.Plugin/api/Npp.DotNet.Plugin.NotepadPPGateway.html


[DocFX]: https://dotnet.github.io/docfx/reference/docfx-cli-reference/overview.html
[README]: https://github.com/npp-dotnet/Npp.DotNet.Plugin/tree/main/lib#projects-using-nppdotnetplugin
[build workflow]: https://github.com/npp-dotnet/Npp.DotNet.Plugin/tree/main/.github/workflows
[documentation workflow]: https://github.com/npp-dotnet/Npp.DotNet.Plugin/tree/main/docfx
[documentation website]: https://npp-dotnet.github.io/Npp.DotNet.Plugin
[table of contents]: https://dotnet.github.io/docfx/docs/table-of-contents.html
[unit tests]: https://github.com/npp-dotnet/Npp.DotNet.Plugin/tree/main/test#readme
[supported]: https://learn.microsoft.com/dotnet/core/deploying/native-aot/?tabs=windows%2Cnet9plus#platformarchitecture-restrictions
