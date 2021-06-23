# Default global usings

1. Edit SDK with changes in https://github.com/dotnet/sdk/pull/18459
2. Pack Library: `dotnet pack .\Library\Library.csproj`
2. Restore App: `dotnet restore -s Library\bin\Debug .\App\App.csproj`
3. Run App: `dotnet run -p .\App\App.csproj`

## What the sample does

1. We add a curated list of global using for apps that use the "Microsoft.NET.Sdk.Web" SDK
   1. This is only enabled for apps targeting `net6.0`
   2. `LangVersion` must be set to preview for now to support global using syntax
   3. Can opt out with `<EnableGlobalUsingFiles>false</EnableGlobalUsingFiles>`
2. Global usings from PackageReference
   1. Library packages can append to the item group `DefaultGlobalUsingFiles` to include a set of default global usings for types in the library.