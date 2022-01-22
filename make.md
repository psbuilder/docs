---
title: Docs - Make a script
---
One of the most important things about open source software is a build workflow. There's not a lot of PowerShell build tools, even on Microsoft's PowerShell Gallery. This teaches you how
to build a PowerShell script or module.

## Install
Go ahead to https://github.com/psbuilder/psbuilder/releases/latest. Download the `PsBuilder.ps1` asset. Or, just run `git clone https://github.com/psbuilder/psbuilder.git psbuilder`,
but you may get unstable psbuilder.

If you use a GitHub Actions workflow to build your PowerShell script, then use `Invoke-WebRequest https://github.com/psbuilder/psbuilder/releases/download/1.0/PsBuilder.ps1`
with the `pwsh` shell (which is the default for `windows-*` with wildcards).

## Code
You need a `ps1`, `psm1`, or `sps1` file to run the build script.

An example of one would be:
```powershell
echo "Hello world!"
Write-Warning "I AM A WARNING"
Write-Error "I AM AN ERROR"
exit 1
```

## Test
> `pwsh`: TEST THIS. **PLEASE!**

Before you run `PsBuilder.ps1`, you may wish to test your code. You can directly run `Install-Module -Name PSScriptAnalyzer -Force` then `Invoke-ScriptAnalyzer` to lint,
then run your PowerShell script to test. Do not try to press `Ctrl + C` to stop the test.

## Build
After all that, it is time to build! Fire up that `PsBuilder.ps1` and watch your script build.
