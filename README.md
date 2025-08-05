# Network
### IP Scanner

https://www.advanced-ip-scanner.com/download/

# Wacom

[Download driver](https://www.wacom.com/start/intuos)
```
Wired connect to PC
Wacom Tablet Properties - Mapping - Untick "Use Windows Ink"
```
# Boot up Dell PC
### Safe Mode
Windows 10
<ul>
	<li>Shart</li>
	<li>Power</li>
	<li>Shift + Click Restart</li>
</ul>
Windows 11
<ul>
	<li>Setting</li>
	<li>Update & Security</li>
	<li>Recovery</li>
	<li>Restart now</li>
	<li>Troubleshoot</li>
	<li>Advance options</li>
	<li>Startup Settings</li>
	<li>Restart</li>
</ul>







### Diagnostics
```
	Turn on machine
	Tab F12 key when see dell logo
	Select Diagnostics
	Result "No error found"

```
### Load default bios
```
	1. Restart your computer
	2. Once the Dell logo appears, press F2 repeatedly until the BIOS menu opens
	3. In the BIOS menu, locate Load defaults, and Confirm
		Setting -> General -> Battery Information -> Restore setting
	4. Exit the BIOS by pressing Exit or F10 and confirming with Enter
```

### Boot into the Windows Recovery Environment
# Enable check update on Acrobat
<ul>
	<li>Opening Registry Editor (Windows).</li>
	<li>Navigating to: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Acrobat Reader\<version>\FeatureLockDown</li>
	<li>Creating or modifying the bUpdater DWORD value:</li>
	<li>Set it to 1 to enable updates.</li>
</ul>

# Run
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1. User account: reset admin password
```
	netplwiz
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2. Change PC name 
```
	sysdm.cpl
```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3. Control Panel Power setting
```
	powercfg.cpl
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4. Stop, start Symantec
```
	Smc -stop
	Smc -start	
```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 5. Delete Port
```
	printmanagement.msc
	>> Print Servers 
	>> <Computer's name> 
	>> Ports
	>> Delete any port you want to
```

# CMD

## I. Windows

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1. Check windows version and ram
```
	systeminfo
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2. Reboot
```
	shutdown /r /t 0
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3. Shutdown
```
	shutdown /s /t 0
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4. Get CPU name
```
	wmic cpu get name

```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 5. Get Hard drive info
```
	wmic diskdrive get model, size, name, sialnumber, status
```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 6. Get dell service tag
```
	wmic bios get serialnumber
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7. Get bios version
```
	wmic bios get biosversion
```


### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8. Get current edition of windows
```
	dism /online /get-currentedition
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Switch user
```
	tsdiscon
```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 9. Diagnosis
```
	DISM /Online /Cleanup-Image /CheckHealth
```
```
	DISM /Online /Cleanup-Image /ScanHealth
```
```
	DISM /Online /Cleanup-Image /RestoreHealth
```
RestoreHealth from iso file: (replace D: by iso drive)
```
	dism /Get-WimInfo /WimFile:D:\sources\install.wim
```
Replace :1 with the correct index number from the previous step.
```
	DISM /Online /Cleanup-Image /RestoreHealth /Source:D:\sources\install.wim:1 /LimitAccess
```
```
	DISM /Online /Cleanup-Image /RestoreHealth /Source:D:\sources\install.wim /LimitAccess
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Should reboot, run ScanHealth and RestoreHealth couple time to see is there any error

```
	Net Stop bits
	Net Stop wuauserv
	Net Stop appidsvc
	Net Stop cryptsvc
	Ren %Systemroot%\SoftwareDistribution\DataStore DataStore.bak
	Ren %Systemroot%\SoftwareDistribution\Download Download.bak
	Ren %Systemroot%\System32\catroot2 catroot2.bak
	Del "%ALLUSERSPROFILE%\Application Data\Microsoft\Network\Downloader\qmgr*.dat"
	Net Start bits
	Net Start wuauserv
	Net Start appidsvc
	Net Start cryptsvc
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 10. Use the System File Checker tool to repair missing or corrupted system files
```
SFC /scannow
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A quick tip: If errors were found, you might want to run the command about three times to make sure
that everything is fixed correctly.

```
	chkdsk /r
	chkdsk /f
```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 11. Add printer 
```
	rundll32 printui.dll,PrintUIEntry /il
```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 12. Remove printer 
```
	printui /s /t2
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 13. Remove printer driver update in Windows Update
<ul>
	<li>gpedit.msc</li>
	<li>Computer Configuration</li>
	<li>Administrative Templates</li>
	<li>Windows Components</li>
	<li>Windows Update</li>
	<li>Do not include drivers with windows update</li>
	<li>Enable</li>
</ul>

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 14. By pass microsoft account in windows setup 
```
Shift + F10 : Open terminal

C:\> netsh interface show interface

C:\> netsh interface set interface name="Wi-fi" admin=disabled

C:\> OOBE\BYPASSNRO

C:\> netsh interface set interface name="Wi-fi" admin=enabled
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 15. Check SUM
```
certutil -hashfile "filename.ext" SHA512
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 16. Upgrade Office 365
```
"C:\Program Files\Common Files\microsoft shared\ClickToRun\OfficeC2RClient.exe" /update user
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 17. Check using IP
```
for /L %i in (1,1,254) do @ping -n 1 -w 100 192.168.1.%i >nul && echo 192.168.1.%i is active
```
```
arp -a
```

### Activate windows server 2022 VM
Not key sensitive
```
DISM /Online /Set-Edition:Serverstandard /AcceptEula /Productkey:XXXXX-XXXXX-XXXXX-XXXXX-XXXXX
```
### Copy files and folders
```
	robocopy
```
## II. Installation
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1. Node js

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [Download Node Js](https://nodejs.org/en/download/)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; reboot computer

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2. Install typescript:
```
	npm install -g typescript
```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3. Check typescript compiler version:
```
	tsc –v
	tsc --version
```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4. Run js file:
```
	Node <file.js>
	tsc.ts | node main.js
```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 5. VSCode
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Package: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Auto Import
	
## III. Angular
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1. Install Angular CLI
```
	npm install -g @angular/cli
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2. Create new project
```
	ng new <Project name>
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3. Create component 
```
	// Angular generate component
	ng g c <component name>	
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4. Create service 
```
	// Angular generate service
	ng g s <service name>	
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 5. Create pipe 
```
	// Angular generate pipe
	ng g p <pipe-name>
```

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 6. Install bootstrap
```
	npm install bootstrap --save 
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; src/style.css
```
		@import "~bootstrap/dist/css/bootstrap.css";
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7. Install bootstrap icon
```
	npm i bootstrap-icons
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; or
```
	npm i bootstrap-icons --save
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; src/style.css
```
		@import "~bootstrap-icons/font/bootstrap-icons.css";
```

## IV. Git
```
	git init
	git add .
	git commit -m "first commit"
	git remote add orgin https://github.com/trankimtu/angular-favorite.git
	git push -u origin master
```
## V. Enagle Manual Check Update Acrobat reader
change bUpdate to 1
```
Computer\HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown
```
# Windows Server
## I. Computer Management
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1. Create Share drive
```
File Explorer
To assign file share permissions by using File Explorer:

Open File Explorer.

Select and hold (or right-click) the D:\SymStore\Symbols folder and select Properties.

Select the Sharing tab.

Select Advanced Sharing.

In Advanced Sharing, select the Share this folder checkbox, and then select Permissions.

In Share Permissions, select Everyone, and then select Remove.

Select Add and enter the users or groups you want to access the file share.

For each user or group you add, select Allow to assign Full Control, Change, or Read permissions.

Select Apply, and then select OK.

Select OK, and then select Close.

Computer Management
To assign file share permissions by using Computer Management:

Select and hold (or right-click) Start and select Computer Management.

In the console tree, select System Tools > Shared Folders > Shares.

Select and hold (or right-click) and select New > Share.

In Create A Shared Folder Wizard, select Next.

For Folder path, enter D:\SymStore\Symbols, and then select Next.

Select Next.

In Shared Folder Permissions, select Customize permissions, and then select Custom.

In Share Permissions, select Everyone, and then select Remove.

Select Add and enter the users or groups you want to access the file share.

For each user or group you add, select Allow to assign Full Control, Change, or Read permissions.

Select Apply, and then select OK.

Select Finish twice.
```
### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2. Force close shared opened file
```
Computer Management
> System tools
>> Shared Folders
>>> Open Files
Find the file, right click > Close Open File
```
## II. Active Directory Users and Computers
```
Create group, manage permission
```
