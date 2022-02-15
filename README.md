# Custom Windows Prompt
This one-liner will make your windows command prompt beautiful. In combination with what I like to call "batchrc" (like bashrc), this makes a perfect command prompt experience.

# How to create a "batchrc" profile - Step by Step
- Press the windows key and type "cmd"
- If you find anything that is called "cmd" except cmd.exe (from System32) itself, go to there and delete or rename it (it's usually shortcuts you have to delete/rename)
- Press the windows key and type "cmd"
- Go to the location of cmd.exe (it should be the first entry)
- Create a shortcut for it. It will ask you if you want to create the shortcut on the desktop, click yes.
- Press windows key + r
- Type shell:startup
- Go up on folder (press Alt+Up)
- Move the cmd shortcut from the desktop to the folder you've just gone up (this is the user start menu)
- Rename the shortcut to "cmd" or "CMD" if you like
- Select the shortcut (should be already)
- Press Alt+Enter for changing its properties
- Change target to `%SystemRoot%\System32\cmd.exe /k ""%Userprofile%\batchrc.cmd""` (notice the double double quotes)
- Press Enter/Close the dialogue
- Open explorer and go to `%Userprofile%`
- Download batchrc.cmd form this repo into that directory
- Press the windows key and type "cmd"
- If "cmd" is the first entry and below the name "cmd" it says "App", then you've done everything right. If it doesn't say "App", then it's just the normal cmd.exe from System32. If the latter happens, wait 1-2 minutes (this should be plenty). If it still doesn't work, either you did something wrong or your windows does things mine doesn't.

batchrc.cmd is now you new custom cmd profile! You can type anything here, just don't do `SETLOCAL EnableDelayedExpansion`. This for some reason breaks variables inside batchrc.cmd completely and I don't know why. If you still do it, don't close it with `ENDLOCAL`. Because setting `prompt` just changes a variable, making batchrc local with `SETLOCAL` and `ENDLOCAL` just reverts pretty much any changes and settings you've done once batchrc is done executing.
In batchrc, you can now define variables, CALL functions, batch macros, your prompt (of which there is a beautiful preset given in this repo's batchrc.cmd), your default location, window size (`mode con cols=10 lines=10`), title, autorun routines and much more!
