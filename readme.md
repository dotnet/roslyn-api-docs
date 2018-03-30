# Readme.md

This repository contains the API documentation for the
[.NET Compiler Platform SDK](https://github.com/dotnet/roslyn-sdk). The .NET
Compiler Platform SDK is part of the overall .NET developer documentation.
The .NET content team tracks all work for .NET developer documentation
on the [.NET Docs](https://github.com/dotnet/docs) repository. If you find
any issues, or have suggestions on how to improve the .NET Compiler platform
SDK documentation, create them on the [docs repository](https://github.com/dotnet/docs/issues).
That repository contains the source for conceptual documentation, tutorials and more,
including all the dcoumentation on the .NET Compiler Platform SDK.

This remainder of this file has notes which NuGet packages make up the
.NET Compiler SDK Meta-package.

## NuGet Packages that comprise the Roslyn APIs

The package that you need to install to use Roslyn is
**Microsoft.CodeAnalysis**.  This is a meta-package, so
there are no DLLs or XML files delivered with it.

The documentation says that this package contains:

- ***Microsoft.CodeAnalysis.CSharp.Workspaces*** (C# Compiler and services)
- ***Microsoft.CodeAnalysis.VisualBasic.Workspaces*** (VB Compiler and Services)
- ***Microsoft.CodeAlaysis.Compilers*** (both compilers)
- ***Microsoft.CodeAnalysis.CSharp*** (C# compiler)
- ***Microsoft.CodeAnalysis.VisualBasic*** (VB compiler

The package dependencies contain only the first two on that list.

## Transitive Dependencies

- ***Microsoft.CodeAnalysis.CSharp.Workspaces*** lists the following dependencies:
  - ***Microsoft.CodeAnalysis.CSharp*** lists the following dependency:
    - ***Microsoft.CodeAnalysis.Common*** lists the following dependency:
      - ***Microsoft.CodeAnalysis.Analyzers***: Tools, not SDKs
  - ***Microsoft.CodeAnalysis.Workspaces.Common*** lists the following dependency:
    - ***Microsoft.CodeAnalysis.Common*** lists the following dependency:
      - ***Microsoft.CodeAnalysis.Analyzers***: Tools, not SDKs
- ***Microsoft.CodeAnalysis.VisualBasic.Workspaces*** lists the following dependencies:
  - ***Microsoft.CodeAnalysis.VisualBasic*** lists the following dependency:
    - ***Microsoft.CodeAnalysis.Common*** lists the following dependency:
      - ***Microsoft.CodeAnalysis.Analyzers***: Tools, not SDKs
  - ***Microsoft.CodeAnalysis.Workspaces.Common*** lists the following dependency:
    - ***Microsoft.CodeAnalysis.Common*** lists the following dependency:
      - ***Microsoft.CodeAnalysis.Analyzers***: Tools, not SDKs
- ***Microsoft.CodeAnalysis.Compilers*** lists the following dependencies:
  - ***Microsoft.CodeAnalysis.CSharp*** lists the following dependency:
    - ***Microsoft.CodeAnalysis.Common*** lists the following dependency:
      - ***Microsoft.CodeAnalysis.Analyzers***: Tools, not SDKs
  - ***Microsoft.CodeAnalysis.VisualBasic*** lists the following dependency:
    - ***Microsoft.CodeAnalysis.Common*** lists the following dependency:
      - ***Microsoft.CodeAnalysis.Analyzers***: Tools, not SDKs

## XML File locations

The following packages are metapackages and do not have XML files:

- ***Microsoft.CodeAnalysis***
- ***Microsoft.CodeAnalysis.Compilers***

The following package only contains tools and does not have an APIs:

- ***Microsoft.CodeAnalysis.Analyzers***

The following packages have a single XML file:

- ***Microsoft.CodeAnalysis.Common*** (File is Microsoft.CodeAnalysis.xml)
- ***Microsoft.CodeAnalysis.CSharp***
- ***Microsoft.CodeAnalysis.CSharp.Workspaces***
- ***Microsoft.CodeAnalysis.VisualBasic***
- ***Microsoft.CodeAnalysis.VisualBasic.Workspaces***

One package has multiple XML files, for .NET standard and .NET Framework:

- ***Microsoft.CodeAnalysis.Workspaces.Common***
The `Microsoft.CodeAnalysis.Workspaces.XML` file for .NET Standard and
`Microsoft.CodeAnalysis.Workspaces.Desktop.XML` and `Microsoft.CodeAnalysis.Workspaces.XML` for .NET 4.6

