@echo off
title Runtime Broker Disabler, made by Ventetos

echo.	Questo e  il  programma  per la game mod  assicurati di attivarlo quando sei in  game e  toglierlo quando fai azioni quotidiane
echo.   se hai bisgono   di assistenza  scrvimi su ig  Vente.tweak
echo.
echo.	Press [D] to Active Game Mode
echo.	Press [E] to Disable Game Mode


set /p c="What is your choice? "
if /i %c% equ D goto :Active Game Mode
if /i %c% equ E goto :Disable Game Mod

:Active Game Mode
taskkill /f /im explorer.exe
taskkill /f /im runtimebroker.exe
cd C:\Windows\System32
takeown /f "runtimebroker.exe"
icacls "C:\Windows\System32\RuntimeBroker.exe" /grant Administrators:F
ren runtimebroker.exe runtimebroker.old
start explorer.exe
Reg.exe add "HKLM\SYSTEM\CurrentControlSet\Services\wsearch" /v "Start" /t REG_DWORD /d "4" /f
Reg.exe add "HKCU\Software\Microsoft\Windows\CurrentVersion\Search" /v "SearchboxTaskbarMode" /t REG_DWORD /d "0" /f
sc stop wsearch
taskkill /f /im explorer.exe
taskkill /f /im searchapp.exe
taskkill /f /im SearchHost.exe
cd C:\Windows\SystemApps\Microsoft.Windows.Search_cw5n1h2txyewy
takeown /f "searchapp.exe"
icacls "C:\Windows\SystemApps\Microsoft.Windows.Search_cw5n1h2txyewy\searchapp.exe" /grant Administrators:F
ren searchapp.exe searchapp.old
cd C:\Windows\SystemApps\MicrosoftWindows.Client.CBS_cw5n1h2txyewy
takeown /f "SearchHost.exe"
icacls "C:\Windows\SystemApps\MicrosoftWindows.Client.CBS_cw5n1h2txyewy\SearchHost.exe" /grant Administrators:F
ren SearchHost.exe SearchHost.old
start explorer.exe
cls
pause
exit


:Disable Game Mod
taskkill /f /im explorer.exe
cd C:\Windows\System32
takeown /f "runtimebroker.old"
icacls "C:\Windows\System32\RuntimeBroker.old" /grant Administrators:F
ren runtimebroker.old runtimebroker.exe
start explorer.exe
start runtimebroker.exe
Reg.exe add "HKLM\SYSTEM\CurrentControlSet\Services\wsearch" /v "Start" /t REG_DWORD /d "2" /f
Reg.exe add "HKCU\Software\Microsoft\Windows\CurrentVersion\Search" /v "SearchboxTaskbarMode" /t REG_DWORD /d "1" /f
sc start wsearch
taskkill /f /im explorer.exe
taskkill /f /im searchapp.exe
taskkill /f /im SearchHost.exe
cd C:\Windows\SystemApps\Microsoft.Windows.Search_cw5n1h2txyewy
takeown /f "searchapp.exe"
icacls "C:\Windows\SystemApps\Microsoft.Windows.Search_cw5n1h2txyewy\searchapp.exe" /grant Administrators:F
ren searchapp.old searchapp.exe
cd C:\Windows\SystemApps\MicrosoftWindows.Client.CBS_cw5n1h2txyewy
takeown /f "SearchHost.old"
icacls "C:\Windows\SystemApps\MicrosoftWindows.Client.CBS_cw5n1h2txyewy\SearchHost.old" /grant Administrators:F
ren SearchHost.old SearchHost.exe
start explorer.exe
cls
pause
exit
# Vente
Game MOD
