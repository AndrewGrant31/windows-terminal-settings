# windows-terminal-settings.json
settings.json file for Windows Terminal

Please, do remember to insert your own guid's into each of the guid settings - marked with the text: your-guid .
The guids' used on my machine have been stripped from the setting file and replaced with the text "your-guid".
Use a PowerShell window and issue the command new-guid. 
Copy the new guid and paste into the relevant section for each of the settings. You have to do this for each section.

For the icons, copy the icons downloaded from this repository to a relevant folder in your %USERPROFILE% and copy the path to the folder and the relevant icon into the section marked "path to icon".

Finally, find and copy the path to your source code folder (it will be in the location bar in Windows Explorer) and paste it into the startingDirectory command, marked with the text "path to source code folder"

If you are using QT MSVC, then it is a good idea to run vcvarsall.bat
To do this, open either a powershell window or a command line window, as an administrator, and navigate to C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Auxiliary\Build (for Visual Studio 2022 Community Edition), then run vcvars64.bat by entering the command ./vcvars64.bat and pressing enter. 

The [the version number] is the folder immediately under the Qt folder. It will follow the convention of Version_Major.Version_Minor.Version_Patch

After completing this, you can navigate to C:\Qt\[the version number]\msvc2019_64\bin, open qtenv2.bat and amend the file to read:

**@echo off  
REM echo Setting up environment for Qt usage...  
set PATH=C:\Qt\[the version number]\msvc2019_64\bin;%PATH%  
REM cd /D C:\Qt\[the version number]\msvc2019_64  
cd /D %USERPROFILE%\\[The folder where you write your projects]  
REM echo Remember to call vcvarsall.bat to complete environment setup!  **

You can do the same for the mingw qtenv2.bat file located in the mingw_xx folder. 

Keep the lines marked with REM; deleting them does, occasionally, cause problems. 

If you have Visual Studio 2019 or 2022 installed, run the vcvarsall.bat file. 
To run the vcvarsall.bat file, use the terminal or command line, as Administrator, navigate to C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Auxiliary\Build (if you are using the standard install path for Visual Studio 2019/2022) and type at the prompt:
.\vcvarsall.bat and then choose your platform type from the list provided and retype amended the correct platform type. 
For example, on my current computer I type:
.\vcvarsall.bat amd64 
press enter and let it do it's thing.

You can, of course, change the colorScheme to suite your own wishes.

## License
Use this file as you wish, there is no guarantee of merchantability, fitness and comes with no warranty at all. 
