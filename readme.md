# Roslyn API reference documentation

This repository contains the files necessary to publish the roslyn API docs on [Microsoft Learn](https://learn.microsoft.com/dotnet/api/?view=roslyn-dotnet-4.7.0). That includes OPS build configuration and the XML output from the `///` comments on files in the [roslyn](https://github.com/dotnet/roslyn) and [roslyn-sdk](https://github.com/dotnet/roslyn-sdk) repositories. The source of truth for roslyn API documentation is the `///` comments in those repositories. If you find issues with the API documentation, you should report them in those repositories. Issues are disabled in this repo for that reason.

If you wish to make updates by submitting a pull request, it should be done in those repositories. The only updates here should be to the configuration metadata. Other PRs will be closed, and you'll be redirected to the correct source repository.

This project has adopted the code of conduct defined by the Contributor Covenant to clarify expected behavior in our community. For more information, see the [.NET Foundation Code of Conduct](https://dotnetfoundation.org/code-of-conduct).

The remainder of this file has notes which NuGet packages make up the .NET Compiler SDK metapackage.

## NuGet Packages that comprise the Roslyn APIs

The package that you need to install to use Roslyn is **Microsoft.CodeAnalysis**.  This is a meta-package, so there are no DLLs or XML files delivered with it.

The documentation says that this package contains:

- ***Microsoft.CodeAnalysis.CSharp.Workspaces*** (C# Compiler and services)
- ***Microsoft.CodeAnalysis.VisualBasic.Workspaces*** (VB Compiler and Services)
- ***Microsoft.CodeAnalysis.Compilers*** (both compilers)
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
