# "Pure Code" PowerShell Theme

A minimal Oh My Posh theme based on Pure, optimized for development and Git readability.

## Preview

```text
D:\docs\code\oh-my-posh-pure-code git:master ≢ dirty:?1 | staged:+1  3.012s 
❯ git status
```

## Install

```powershell
$ompThemesDirectory = Join-Path $env:LOCALAPPDATA 'Programs\oh-my-posh\themes'
$ompConfig = Join-Path $ompThemesDirectory 'pure-code.omp.json'
$ompThemeUrl = 'https://raw.githubusercontent.com/seigtm/oh-my-posh-pure-code/refs/heads/master/pure-code.omp.json'

New-Item -ItemType Directory -Path $ompThemesDirectory -Force | Out-Null
Invoke-WebRequest -Uri $ompThemeUrl -OutFile $ompConfig

oh-my-posh init pwsh --config $ompConfig | Invoke-Expression
```

## PowerShell profile snippet

Add this to your `$PROFILE`:

```powershell
# Oh-My-Posh with Pure Code theme:
$ompConfig = Join-Path $env:LOCALAPPDATA 'Programs\oh-my-posh\themes\pure-code.omp.json'

if ((Get-Command oh-my-posh -ErrorAction SilentlyContinue) -and (Test-Path -LiteralPath $ompConfig)) {
    oh-my-posh init pwsh --config $ompConfig | Invoke-Expression
}
```
