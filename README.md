# CH5 Basic example

Just has a couple of buttons that show a couple of "sub pages"

# Installation
First you will need to install node.js from https://nodejs.org

Then open a cmd window as admin and run the command;
    npm install -g @crestron/ch5-utilities-cli

# VS Code Extension
In VS Code, install the Crestron Components CH5 extension.
Close and reopen VS Code after this step.

# Setting up the project
Open the folder containing the project in VS Code.
Open a termial window in VS Code
If this is the first time using VS Code and if it says Windows Powershell at the top of the terminal window run the command;
 Set-ExecutionPolicy RemoteSigned

# These install the required files to run a Crestron CH5 project
Now run the commands;
 npm install @crestron/ch5-crcomlib
 npm install @crestron/ch5-theme

# Build project archive for loading to the touch panel
If you've built the project before you may need to delete the 'dist' directory from your folder, it wouldn't run for me if it already existed...
In the terminal run the command (instead of C:\CH5\CH5-Basic use the filepath of the folder the index.html file is in);
ch5-cli archive -p CH5-Test-Project -d C:\CH5\CH5-Basic -o dist

This will create the .ch5z file that needs to be loaded to the touchpanel

# Load project to touch panel
In the termial window run the command, replace  ip_address_of_touchpanel with the touchpanels IP address...;
 ch5-cli deploy -H ip_address_of_touchpanel -t touchscreen dist/CH5-Test-Project.ch5z

 