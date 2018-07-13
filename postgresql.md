https://blog.2ndquadrant.com/compiling-postgresql-extensions-visual-studio-windows/

https://adrianhenke.wordpress.com/2008/12/05/create-lib-file-from-dll/

http://okbob.blogspot.com/2015/02/plpgsqlcheck-is-available-for-microsoft.html

When working with 3rd party win dll’s you somtimes miss the according .lib file required to compile against it. There is a MS KB article showing how to generate a .lib file from a .dll, however the required steps are not described detailed enough I think. So here is my quick guide:

Open the Visual Studio Command Prompt, you find its shortcut in Start->Programs->Microsoft Visual Studio->Tools. Now run the dumpbin command to get a list of all exported functions of your dll:


dumpbin /exports C:\yourpath\yourlib.dll

This will print quite a bit of text to the console. However we are only interested in the functions:




Now copy all those function names (only the names!) and paste them into a new textfile. Name the nextfile yourlib.def and put the line “EXPORTS” at its top. My yourlib.def file looks like this:


Now from that definition file, we can finally create the .lib file. We use the “lib” tool for this, so run this command in your Visual Studio Command Prompt:


lib /def:C:\mypath\mylib.def /OUT:C:\mypath\mylib.lib

That’s it, happy coding 🙂
