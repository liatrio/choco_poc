```
# Powershell


# Allow internet sourced script execution of signed scripts
Set-ExecutionPolicy AllSigned -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))


# Auto-confirm-yes always
choco feature enable -n allowGlobalConfirmation


choco install vscode -y
choco install git -y

# Disable/enable source
choco source enable --name chocolatey
choco source disable --name chocolatey

# Add source
choco source add -n liatrio -s="https://artifactory.liatr.io/artifactory/api/nuget/choco-local"

# Create a new package template 
choco new test1 -a --version 0.0.1 maintainername="'myusername'"


```