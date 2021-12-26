# windows-terminal-settings.json
Setting (json) file for Windows Terminal

Please, do remember to insert your own guid's into each of the relevant settings.
The guids' used on my machine have been stripped from the setting file and replaced with the text "Requires new guid".
Use a pwoershell window and issue the command new-guid. 
Copy the new guid and paste into the relevant section for each of the settings. You have to do this for each section.

For the icons, copy the icons downlaoded from this repository to a relevant folder in your %USERPROFILE% and copy the path to the folder and the relevant icon into the section marked "path to icon".

Finally, find and copy the path to your source code folder (it will be in the location bar in Windows Explorer) and paste it into the startingDirectory command, marked with the text "path to source code folder"

If you are using QT MSVC, then it is a good idea to run vcvarsall.bat
To do this, open either a powershell window or a command line window, as an administrator, and navigate to C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Auxiliary\Build (for Visual Studio 2022 Community Edition), then run vcvars64.bat by entering the command ./vcvars64.bat and pressing enter. 

After completing this, you can navigate to C:\Qt\6.2.2\msvc2019_64\bin, open qtenv2.bat and amend the file to read:

@echo off  
REM echo Setting up environment for Qt usage...  
set PATH=C:\Qt\6.2.2\msvc2019_64\bin;%PATH%  
REM cd /D C:\Qt\6.2.2\msvc2019_64  
cd /D %USERPROFILE%\Projects  
REM echo Remember to call vcvarsall.bat to complete environment setup!  

You can do the same for the mingw qtenv2.bat file located in the mingw_xx folder. 

Keep the lines marked with REM; deleting them does, occasionally, cause problems. 

You can, of course, change the colorScheme to suite your own needs.
