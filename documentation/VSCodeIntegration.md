# VS Code integration features

** !!! SUBJECT TO CHANGE !!! **

## Tasks
There are a number of supported tasks that you can utilize to speed up your workflow.
You can access a list of the available tasks by hitting `CTRL+P` then type in `task` followed by
a `SPACE` in the popup. Alternatively, you can assign a keyboard shortcut to this list. To assign a
keyboard shortcut, go to `File -> Preferences -> Keyboard Shortcuts`. In the file `keybindings.json`,
add something similar to this:
```json
{
    "key": "ctrl+shift+r",
    "command": "workbench.action.tasks.runTask"
}
```
As you may have noticed, when you opened up the preferences, VS Code opened up two files. The one to the
left is the default settings. Make you sure you search for the desired keyboard shortcut to make sure
it's not occupied by some other command (if it is, you can always reassign it). Here are the available tasks:

* **build:**
This task will perform code analysis and build the entire project. magic will query the file
`vscode_build.json` for build parameters. This file must be located in the project root folder. This task
can by default be accessed using the keycommand `CTRL+SHIFT+B`.

* **compile current file:**
Compiles the current file.

* **test current file:**
Runs the associated test for the currently opened file. For example, if you are working on the file
`Quaternion.ooc` and run this task, magic will compile and run `QuaternionTest.ooc`. This task can by default
be accessed using the keycommand `CTRL+SHIFT+T`. magic will query `vscode_test.json` for the required parameters.
This file must be located in the project root folder.

* **test project:**
This task will run the entire test suite. magic will query `vscode_test.json` for the required parameters.
This file must be located in the project root folder.

* **analyze current file:**
Performs code analysis on the file you are currently working on. Note that this will bypass `.magicignore`.

* **analyze project:**
Performs code analysis on the entire project. To prevent magic from analyzing certain files or folders, you can
add them in `.magicignore`, which must be located in the project root folder.