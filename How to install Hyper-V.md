# HOW TO INSTALL HYPER-V

**Step 1**: 
Open **Notepad** => **paste this**:
```bat
pushd "%~dp0"

dir /b %SystemRoot%\servicing\Packages\*Hyper-V*.mum >hyper-v.txt

for /f %%i in ('findstr /i . hyper-v.txt 2^>nul') do dism /online /norestart /add-package:"%SystemRoot%\servicing\Packages\%%i"

del hyper-v.txt

Dism /online /enable-feature /featurename:Microsoft-Hyper-V -All /LimitAccess /ALL

pause
```

**Step 2**: Save as **hyperv.bat** file.

**Step 3**: Open that file as Administrator => Wait => enter Y or Wait the laptop restart.

**Step 4**: Enter code ```DISM /Online /Enable-Feature /All /FeatureName:Microsoft-Hyper-V``` at **Command Prompt** application when the laptop has started.