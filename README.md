# GenericHostedServiceAsAService

Nuget package to be used to allow dotnet core console application to run as Windows service.
Including small example of a generic host based .NET core app which can be run as a Windows Service.

## Building and creating nuget package
1. Set package version (requires [GitVersion](https://chocolatey.org/packages/GitVersion.Portable/4.0.0) and [Setversion](https://www.nuget.org/packages/dotnet-setversion/) to be installed):
   
   ```PS> setversion $(gitversion /showvariable semver)```
2. Create nuget package: 

    ```dotnet pack -c Release```

## Building and creating a service demo

### Build and publish demo project

`dotnet publish --configuration Release`

### Define the service from demo

`sc create MyFileService binPath= "E:\Projects\IHostedServiceAsAService\IHostedServiceAsAService\bin\Release\netcoreapp2.1\win7-x64\publish\IHostedServiceAsAService.exe"`

### Start the service

`sc start MyService`

For further details see blog post [Running a .NET Core Generic Host App as a Windows Service](https://www.stevejgordon.co.uk/running-net-core-generic-host-applications-as-a-windows-service)
