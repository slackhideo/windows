# Windows Troubleshooting

## Disabling Hibernation
```powercfg -h off```
It removes the gigantic `hiberfil.sys` file.

## Entering Safe Mode
Ctrl + Alt + Del -> Power icon -> Hold shift and click restart

## Removing Page File (fixing "Performance Options dialog box appearing at startup" problem)
In safe mode,
```
cd c:\
dir /a:h
del /a:h pagefile.sys
chkdsk /f
```
Sources:
[Bobby_Lee, Microsoft Community](https://answers.microsoft.com/en-us/windows/forum/all/performance-options-dialog-box-opens-automatically/fb5450de-7330-44ae-acaa-9176aeeefb73#LastReply)
[MajorGeeks](https://forums.majorgeeks.com/threads/performance-option-dialog-box-appear-at-startup.291303/)

## Determining the Actual Size of the WinSxS Folder
```Dism.exe /Online /Cleanup-Image /AnalyzeComponentStore```
Source:
[Microsoft Learn](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/determine-the-actual-size-of-the-winsxs-folder?view=windows-10)

## Cleaning Up the WinSxS Folder
```Dism.exe /Online /Cleanup-Image /StartComponentCleanup```
Source:
[Microsoft Learn](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/clean-up-the-winsxs-folder?view=windows-10)
