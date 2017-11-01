# Testing inotify with .NET Core and LCOW

## How to test

```
C:\code\watch-dotnet-test> docker run -ti -v ${PWD}:/app --workdir /app microsoft/dotnet bash

root@b8bb809a19e3:/app# dotnet restore
  Restore completed in 408.87 ms for /app/foo.csproj.
  Restoring packages for /app/foo.csproj...
  Restore completed in 1.02 sec for /app/foo.csproj.
  Restoring packages for /app/foo.csproj...
  Restore completed in 7.95 ms for /app/foo.csproj.

root@b8bb809a19e3:/app# dotnet watch run
watch : Started

<MAKE FILE CHANGE ON HOST AND SAVE>

/usr/share/dotnet/sdk/2.0.2/Microsoft.Common.CurrentVersion.targets(4052,5): error MSB3021: Unable to copy file "obj/Debug/netcoreapp2.0/foo.dll" to "bin/Debug/netcoreapp2.0/foo.dll". Access to the path is denied. [/app/foo.csproj]

The build failed. Please fix the build errors and run again.
watch : Exited with error code 1
watch : Waiting for a file to change before restarting dotnet...
```