# Installfest Step 1: General Mac Development Tools


If you do not yet have an account for the Mac App Store, follow the instructions on Apple Support to <a href="https://support.apple.com/kb/PH11499?locale=en_US" target="_new">create a Mac App Store account</a>.

## Operating System and Command Line Tools

Before class starts, we suggest you upgrade your operating system to OS X Mavericks (10.9), Yosemite (10.10) or El Capitan (10.11).  If you're on an older machine with 4GB or less of memory, please stick to OS X Mavericks.  Also, **if Apple releases a newer version of OS X while you're in WDI; please don't update until your instructors say it's ok.**

To check what version of OS X you are running:

1. Click the apple icon in the top left of your screen. 

2. Select "About This Mac" from the dropdown menu.

3. Read the version information from the window that pops up.

If you are not using Maverick, Yosemite, or El Capitan, detailed instructions for upgrading your operating system are available through Apple support: <a href="https://www.apple.com/support/osx/upgrade/" target="_new">How to upgrade to OS X Yosemite</a>.

> Please let an instructor know if you're using an older version of OS X or if your system has less than 2 GB of memory.

### Install Command Line Tools from the Terminal

1. Open the Terminal application.
2. In your Terminal, type `xcode-select --install`, and a new window and installer will appear. 
	3. Note: If you see an error saying that Command Line Tools are already installed, you are all set, and can move on to the Homebrew steps.
3. Follow the instructions in the installer. 


### Install Command Line Tools through Xcode (Older Versions of OS X)

**Only follow these steps if you were not able to install Xcode Command Line Tools with the instructions above.** If you must run a version of OS X before Mavericks, you will need to install Command Line Tools that come from Xcode.

1. Open the Mac App Store and install Xcode.
2. Open Xcode.
3. Inside the Xcode menu, choose Preferences > Downloads > Install The Command Line Tools.
4. Follow the instructions in the installer.

## Homebrew

<a href="http://brew.sh/" target="_new">Homebrew</a> is a *package manager* for OS X.  We'll use to quickly download and install other tools we use, or to update already installed tools. 

1. Open the Terminal application, and run `which brew` to check if you have Homebrew installed already. The `which` Terminal command shows where on your computer a program is installed. If it is installed, the Terminal will output a file path. If it is not installed, the Terminal won't output anything.

2. **Only if you do not have Homebrew installed**, run the command below to install Homebrew. Wait while Homebrew downloads and installs.

	```bash
	ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	```

	If you run into problems, you may need to run `rm -rf /usr/local/Cellar /usr/local/.git` and then retry the command above.

3. Run `brew update` to update Homebrew.

4. Run `brew doctor` in your Terminal to check that Homebrew and any current packages are installed correctly. If there are issues, `brew doctor` will list suggestions for how to fix them.  Follow these suggestions one by one. If you're not sure what to do, **ask!**

5. Based on the errors in the step above, you may need to edit your `~/.bash_profile` to include the path to Homebrew if `brew doctor` shows warnings.  If in doubt ask for help here.

	```bash
	bash echo 'export PATH="/usr/local/bin:/usr/local/sbin:~/bin:$PATH"' >> ~/.bash_profile
	```

6. Let's install our first package with Homebrew, `tree`!  This package adds a command to your Terminal that displays files in a tree view (instead of a list view like `ls`).  Enter the following command in your Terminal:

	```bash
	brew install tree
	```

7. Run the Terminal command `tree` to see a tree view of all the files inside your current directory!

## Git

You should already have git installed and have an account on GitHub from Fundamentals. If not, sign up for an account on <a href="http://www.github.com" target="_new">http://www.github.com</a>. We will be using github.com to track code and for collaboration. 

### Confirm Install

1. To check whether git is installed on your system, run the Terminal command `which git`. The output should be a directory path like `/usr/bin/git`; this is where git is installed on your machine.


2. **Only if you do not have git installed,** run the following command in your Terminal:

	```
	brew install git
	```

### Configure Git

Configuring your git settings to help GitHub track your contributions and to make it easier and smoother to commit. 

1. Use the following three `git config` commands to configure your git user information and have git "cache" (remember) it. We use the `--global` (or `-g`) option to make the configuration apply to all repositories.
  
	```
	git config --global user.name "YOUR-USERNAME"
	git config --global user.email YOUR-EMAIL-ADDRESS
	git config --global credential.helper cache
	```

1. Generate a SSH key for GitHub. This will allow you to use GitHub from your Terminal without entering your login information every time you push.

    <a href="https://help.github.com/articles/generating-an-ssh-key" target="_new">Generating SSH Keys (via GitHub.com)</a>

<details>
<summary>Sublime Text 3 - preferred text editor</summary>
## Sublime Text 3

__We understand some Developers prefer Atom or another text editor, but our instructional materials often reference Sublime. You may certainly use another text editor in class, but our instructional materials reference Sublime, so we recommend installing it for the sake of consistency.__

1. Use the following link to <a href="https://download.sublimetext.com/Sublime%20Text%20Build%203103.dmg">download Sublime Text 3 for Mac.)</a>. To install for another system go [here](https://www.sublimetext.com/3)

2. Open the downloaded file.

3. Follow the installation instructions (drag Sublime Text 3 to your Applications folder).

4. Open the Sublime Text 3 application. 

### Add Package Control

Sublime Text has its own very popular package manager called Package Control. We'll use it to add extra features to Sublime Text, including a web development shortcut package called Emmet and a JavaScript syntax helper jshint.

1. Follow <a href="https://packagecontrol.io/installation" target="_new">Package Control's  "simple installation" instructions</a> to add Package manager to your Sublime Text. When you paste the large block of text, make sure you:
   -  use the Sublime Text 3 version, and 
   -  enter the text into the bottom rectangle of the Sublime Text console.

2. We access Package Control through the Sublime Text command palette. Open the palette by pressing `cmd+shift+p` from within Sublime Text. Type `Package Control`  in the command palette to see the list of things Package Control can do.


### Add Packages

1. Let's install our first package, Emmet.  Select `Package Control: Install Package` to bring up the list of available packages. 

2. Select `Emmet` from the list, and Package Control will install it for you!  (Start typing "Emmet" in the search bar to narrow down the list.)

The other package we plan to add, jshint, requires Node.js.  We'll get to it in the next set of instructions, linked at the bottom of this file.

### Access Sublime from the Terminal

Sublime Text 3 includes a program that launches Sublime from the Terminal.  We'll use the `ln` command to link that program to a simple `subl` command. 

1. To run a program from the Terminal, it needs to be available on your $PATH. The next step assumes `/usr/local/bin` is in your $PATH, so let's check that.  Run the following command from the Terminal to see your current $PATH:
	
	```
	echo $PATH
	```

1. Run the following command in your Terminal to set up the link:
	```
	ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
	```

2. Type `subl . ` in the Terminal, and Sublime Text 3 should open!

### Configure git to use Sublime

When you forget to enter a commit message in the Terminal, git opens a text editor and reminds you to add a commit message.

1. Run the following command in the Terminal to configure git to open Sublime Text instead of the default text editor:
	
	```
	git config --global core.editor "subl"
	```

</details>


## Chrome
1. If you don't already have it, <a href="https://support.google.com/chrome/answer/95346?hl=en" target="_new">download and install the Chrome web browser</a>.

## Slack
You should already have Slack installed and have an account from Fundamentals. You can run Slack in the browser without downloading anything. If you prefer, <a href="https://slack.com/downloads" target="_new">download Slack here</a>.

## Window management

While programming it's pretty common to need to place two or three windows next to each other.  We'll install a program that gives us shortcut keys to do this. 
This step is optional.

1. Download https://raw.github.com/onsi/ShiftIt/master/ShiftIt.zip
2. Extract it and drag the application into your `Applications` directory.
3. Double-click the ShiftIt icon in `Applications` and follow the instructions to enable the accessibility options.

ShiftIt offers a few shortcut keys like:
* Move window to the left-half: Command+Option+Control+LeftArrow
* Move window to the right-half: Command+Option+Control+RightArrow
* **M**aximize a window: Command+Option+Control+**M**

You can try this now.

### Dash

[Download Dash](https://kapeli.com/dash) a fantastic application that organizes API documentation for developers. We'll use it more later as we dive deeper into the rich world of languages, frameworks, and libraries.

### Shortcut keys

By the way, developers LOVE shortcut key combinations.  All of the shortcut keys listed above have special abbreviations.  If you have time later, you can read about those abbreviations and some shortcut key combinations <a href="https://support.apple.com/en-us/ht201236" target="_new">here</a>.  You should now see the ShiftIt icon in your menu-bar (at the top of your screen).


[ON TO STEP 2:  NODE.JS AND EXPRESS STACK](express-stack.md)


