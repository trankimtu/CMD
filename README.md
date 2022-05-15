# CMD

## Windows
### Check windows version and ram
```
systeminfo
```

### Get CPU name
```
wmic cpu get name

```
### Get Hard drive info
```
wmic diskdrive get model, size, name, sialnumber, status
```

### Get dell service tag
```
wmic bios get serialnumber
```

### Diagnosis
```
DISM /Online /Cleanup-Image /CheckHealth
DISM /Online /Cleanup-Image /ScanHealth
DISM /Online /Cleanup-Image /RestoreHealth
```
Should reboot, run ScanHealth and RestoreHealth couple time to see is there any error

### Use the System File Checker tool to repair missing or corrupted system files
```
SFC /scannow
```
A quick tip: If errors were found, you might want to run the command about three times to make sure
that everything is fixed correctly.

```
chkdsk /r
```

## Installation
### Node js
```
https://nodejs.org/en/download/
```
### Install typescript:
```
  npm install -g typescript
```

### Check typescript compiler version:
```
	tsc –v
	tsc --version
```

### Run js file:
```
	Node <file.js>
	tsc.ts | node main.js
```

## Angular
### Create new project
```
	ng new <Project name>
```
### Create component 
```
	// Angular generate component
  ng g c <component name>	
```
### Install bootstrap
```
npm install bootstrap --save 
```
src/style.css
```
@import "~bootstrap/dist/css/bootstrap.css";
```
### Install bootstrap icon
```
npm i bootstrap-icons
```
or
```
npm i bootstrap-icons --save
```
src/style.css
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
