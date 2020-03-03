to install the menu run this command

powershell -command "Invoke-WebRequest -Uri 'https://raw.githubusercontent.com/rl-msft/sqlerrorloghelper/master/setup.reg' -OutFile $env:temp\setup.reg"
regedit.exe /s "%temp%\setup.reg"


to uninstall, run this command

powershell -command "Invoke-WebRequest -Uri 'https://raw.githubusercontent.com/rl-msft/sqlerrorloghelper/master/uninstall.reg' -OutFile $env:temp\uninstall.reg"
regedit.exe /s "%temp%\uninstall.reg"


Notes:
- There is no special installation required, just simple reg update and it will add new menu under windows right click context menu, all submenu items PowerShell scripts are hosted on network share which would allow me to update those scripts if needed and those changes would reflect to anyone using the menu without any user action.
- There is no modification happening to any file, processed file will be added as new file with the same as the original file with action name taking against it
  for example if you process a file named below errorlog.1 you will see new processed file name errorlog.1.logins_removed.OUT
- For now, I opted out from adding any progress bar to the PowerShell scripts since I have seen progress bar code was actually adding more cycles and eventually made any file processing slower, so, For now, when you select any option in the mean you should notice windows task PowerShell icon appears, once the icon disappear this is your indicate that processing has completed and you can open processed file.
