# Installfest Step 2: Node.js and Express Stack

Most of the coding work we do in weeks 4 - 5 will be driven by the back end web development framework <a href="http://expressjs.com/" target="_new">Express</a>. We'll install express as we go, on a project-by-project basis. For now, we'll install other tools we'll use along with Express.

**Plan overview:**

1. Install Node.js, a platform for back end web development with the JavaScript programming language. 
2. Install JSHint and its Sublime Text packages to get realtime JavaScript syntax hints.
3. Install MongoDB, the database we'll use with our Node.js and Express stack. 

## Node.js

1. Install Node.js with homebrew by running the following command in the Terminal.

  ```
  brew install node
  ```

2. Run the Terminal command `which node` to check that Node.js was installed. The Terminal command `node` changes your Terminal into a Javascript REPL ("Read Evaluate Print Loop"), like the right hand side of <a href="http://repl.it" target="_new">repl.it</a>.  Type `control+C` twice to quite out of the REPL and return to the normal Terminal commands.

3. Run the Terminal command `which npm` to check that npm is installed. The Node Package Manager, used through various `npm` commands, is a lot like Homebrew, except we'll use it for Node.js-specific tools instead of for general Mac tools. NPM packages are often called "node modules."

### Nodemon

Nodemon (short for "node monitor") will make our node.js workflow more efficient. 

Install nodemon globally with the following command:
  
  ```
  npm install -g nodemon
  ```

If you see an error about permissions, you can run the following instead:
  
  ```
  sudo npm install -g nodemon
  ```

### JSHint for Sublime Text
It's time to install another Sublime Text package! (If you need a refresher on how to do this, you can go back to [the Mac Dev Tools installFest](https://github.com/den-wdi-1/installFest/blob/master/mac-dev-tools.md).

1. Select `Package Control: Install Package` to bring up the list of available packages.  Select `SublimeLinter` from the list, and Package Control will install it for you.

2. Repeat the step above to install the packages "SublimeLinter-jshint".

3. Follow the <a href="https://github.com/SublimeLinter/SublimeLinter-jshint" target="_new">SublimeLinter-jshint install instructions</a> to set up jshint on your laptop. You've just installed Node.js and npm, so you won't need to repeat that step.

## MongoDB

MonogDB is a popular noSQL database.  We'll use it to store data with our Node.js and Express stack. 

1. Use Homebrew to update all of our brew packages.

  ```bash
  brew update
  ```
2. Run `brew install` for **MongoDB**

  ```bash
  brew install mongodb
  ```

3. Then we'll need a directory for **MongoDB** to save data.

  ```bash
  sudo mkdir -p /data/db
  ```

4. Finally we'll want to make sure we have permission to read and write to this directory.

  ```bash
  sudo chown -R $USER /data/db
  ```

5. Run two commands to check whether the install worked. You should see a file path after each command.

  ```bash
  $ which mongod
  $ which mongo
  ```

<details>
<summary>Optional RoboMongo</summary>
## RoboMongo
__Optional__

RoboMongo is a GUI (Graphical User Interface) tool to let us see the data in our Mongo databases.

1. Go to <a href="https://robomongo.org/download" target="_new">robomongo.org</a> and download the free (community) edition.
2. Install it

</details>


[ON TO STEP 3: RUBY ON RAILS](ruby-on-rails-stack.md)
