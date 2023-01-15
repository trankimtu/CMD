# Wacom
```
Wired connect to PC
[Download driver](https://www.wacom.com/start/intuos)
Wacom Tablet Properties - Mapping - Untick "Use Windows Ink"
```

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

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7. Diagnosis
```
	DISM /Online /Cleanup-Image /CheckHealth
	DISM /Online /Cleanup-Image /ScanHealth
	DISM /Online /Cleanup-Image /RestoreHealth
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Should reboot, run ScanHealth and RestoreHealth couple time to see is there any error

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8. Use the System File Checker tool to repair missing or corrupted system files
```
	SFC /scannow
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A quick tip: If errors were found, you might want to run the command about three times to make sure
that everything is fixed correctly.

```
	chkdsk /r
```


### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 9. Add printer 
```
	rundll32 printui.dll,PrintUIEntry /il
```

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

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7. Diagnosis
```
	DISM /Online /Cleanup-Image /CheckHealth
	DISM /Online /Cleanup-Image /ScanHealth
	DISM /Online /Cleanup-Image /RestoreHealth
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Should reboot, run ScanHealth and RestoreHealth couple time to see is there any error

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8. Use the System File Checker tool to repair missing or corrupted system files
```
	SFC /scannow
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A quick tip: If errors were found, you might want to run the command about three times to make sure
that everything is fixed correctly.

```
	chkdsk /r
```


### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 10. By pass microsoft account in windows setup 
```
Shift + F10 : Open terminal

C:\> netsh interface show interface

C:\> netsh interface set interface name="Wi-fi" admin=disabled

C:\> OOBE\BYPASSNRO

C:\> netsh interface set interface name="Wi-fi" admin=enabled
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

## Git
```
	git init
	git add .
	git commit -m "first commit"
	git remote add orgin https://github.com/trankimtu/angular-favorite.git
	git push -u origin master
```
