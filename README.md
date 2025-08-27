# WN10-CC-000205
STIG Implementation WN10-CC-000205

<# .SYNOPSIS Script checks for, and creates if not existing, the AllowTelemetry key in HKLM:\SOFTWARE\Policies\Microsoft\Windows\DataCollection
.NOTES Author : Zachary Williams 
LinkedIn : linkedin.com/in/zacharywilliams05/ 
GitHub : github.com/zacharywilliams05 
Date Created : 2025-08-27
Last Modified : 2025-08-27
Version : 1.0 CVEs : 
N/A Plugin IDs : N/A 
STIG-ID : WN10-CC-000190

.TESTED ON 
Date(s) Tested : 
Tested By : 
Systems Tested : 
PowerShell Ver. :

.USAGE PS C:> .\WN10-CC-000205.ps1 #>

```powershell
# Define the registry path and value
$registryPath = "HKLM:\SOFTWARE\Policies\Microsoft\Windows\DataCollection"
$valueName = "AllowTelemetry"
$valueData = 0

# Check if the registry path exists, if not, create it
if (-not (Test-Path $registryPath)) {
    New-Item -Path $registryPath -Force
}

# Set the registry value
Set-ItemProperty -Path $registryPath -Name $valueName -Value $valueData -Type DWord

# Output confirmation
Write-Host "Registry value '$valueName' set to $valueData in '$registryPath'."
```
