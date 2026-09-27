# IT Administration Repair Toolkit v4

## Files
| File | Purpose |
|---|---|
| `IT_Toolkit.bat` | Double-click this. Gets admin rights, starts the engine. |
| `IT_Toolkit.ps1` | The engine. Keep it next to the .bat. |
| `Plugins\` | Your own `.ps1` add-ons. They show up under **[P] Plugins**. |
| `targets.txt` | Optional list of computer names for the fleet tools. Created on first use. |
| `Logs\` | Daily logs, `Tickets\`, `Fleet\` CSVs, reports. Created automatically. |

## First run
1. If you downloaded the files, right-click each one > **Properties** > tick **Unblock**.
2. Double-click `IT_Toolkit.bat` and approve the admin prompt.
3. Try **[D] Dry Run** first. It shows what each change *would* do without doing it.

## Settings (top of IT_Toolkit.ps1)
- `$LogSecrets` - `$true` also writes BitLocker keys / Wi-Fi passwords to the log.
- `$LowDiskGB`, `$LogKeepDays`, `$ThrottleLimit`, `$UpdateUrl`.

## Remote PCs (domain)
Needs: a domain-joined admin PC, local admin rights on targets, and WinRM enabled
on the targets (off by default on Windows 10/11). See **Remote & Fleet > Remoting Setup Help**.

## Cloud (Intune / Entra)
Needs the Microsoft Graph PowerShell modules (the toolkit offers to install them)
and an admin account allowed to read managed devices, run device actions, and
read BitLocker keys.

## Safety
- Every change asks first. Risky ones default to **No**.
- Restore points are offered before repairs.
- Ticket summaries never contain secrets.
