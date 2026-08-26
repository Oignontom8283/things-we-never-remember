# Extract Windows Spotlight Lock Screen Wallpapers

Purpose: Automatically retrieve and save high-resolution Windows Spotlight lock screen wallpapers to your Desktop.

## Step 1: Open PowerShell
Press `Win + X` and select "Terminal" or "PowerShell" (or search for "PowerShell" in the Start Menu).

## Step 2: Run the Command
Copy and paste the following single command into PowerShell and press Enter:

```powershell
$d="$env:USERPROFILE\Desktop\SpotlightImages"; New-Item -ItemType Directory -Force -Path $d | Out-Null; Get-ChildItem "$env:LOCALAPPDATA\Packages\Microsoft.Windows.ContentDeliveryManager_cw5n1h2txyewy\LocalState\Assets" | Where-Object {$_.Length -gt 100KB} | ForEach-Object -Begin {$i=1} -Process { Copy-Item $_.FullName "$d\Spotlight_$i.jpg"; $i++ }; Write-Host "Successfully exported $($i-1) images to: $d"; Invoke-Item $d
```

## Step 3: Done!
The exported images will automatically open in a new folder on your Desktop ("SpotlightImages").