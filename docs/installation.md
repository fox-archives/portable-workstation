# Installation

## Autoconfig

Bootstrap the creation of a portable development environment using a batch or PowerShell script. It does the following

* Downloads & unzips portable-workstation repository
* Downloads & unzips PowerShell Core 6.2 32bit (~52 MB)
* Downloads & unzips Cmder (with Git for Windows) (~108 MB)
* Creates `.bat` file to run `ExecutePortableScripts.ps1` (so you just have to double click it the `.bat` file)

If your current working directory is at `F:\`, executing the Batch or PowerShell script will create files / folders at `F:\_portable-start.bat`, `F:\_portable-applications`, `F:\_portable-binaries`, `F:\_portable-scripts`, etc. for you.

### Autoconfig With Batch Script

```cmd
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://github.com/EanKeen/portable-workstation/blob/master/install/Install.ps1'))"
```

### Autoconfig With PowerShell Script

```ps
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://github.com/EanKeen/portable-workstation/master/install/Install.ps1'))
```

## Manual Setup

If you already have PowerShell Core or Cmder or want to use your own version, you may opt for a manual setup. I would recommend following this manual setup first. Then, if you want to change any folder names or change the config, to do it afterward. *Any relative paths you see from now on are relative to the directory in which you would have used those Autoconfig scripts in*.

### Clone repo

```bash
git clone https://github.com/EanKeen/portable-workstation.git
```
Then, rename `portable-workstation` to `./_portable-scripts`

### Use PowerShell Core
[PowerShell Core](https://github.com/PowerShell/PowerShell) is slightly different than the Windows Powershell variant. Putting it in your thumbdrive means you don't have to rely on the Windows PowerShell version of your host computer. This project is not intinded to work for Windows Powershell (but rather PowerShell core of at least 6.0)

Download PowerShell core and put it in `./portable_binaries/powershell`. Your executable should be located at `./portable_binaries/powershell/pwsh.exe`.

### Use cmder

[Cmder](https://cmder.net) is a console emulator for Windows. This project has not been tested with Cmder Mini, so I'd recommend downloading Cmder with Git for Windows.

Download Cmder and put it in `./_portable-applications/cmder`. Your executable should be located at `./_portable-applications/cmder/Cmder.exe`.

### Running this portable-workstation
To actually run this portable workstation program, I would recommend creating a batch file, so you can just double click in it, without having to go into the terminal.

In `./_portable-start.bat`, add the following

```bat
cd .\_portable-scripts
start ..\_portable-binaries\powershell\pwsh.exe -ExecutionPolicy Bypass -file .\ExecutePortableScripts.ps1
```

## Next steps
Now you can customize your workstation to fit *your* needs!
Then, just setup a configuration schema [here](/schema).