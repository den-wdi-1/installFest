# Installfest Step 3: Ruby on Rails Stack

**Plan overview:**

1. Update your install of the ruby programming language and install rvm to manage versions of ruby.
2. Install Ruby on Rails, a back end web development framework for the ruby programming language.
3. Install PostgreSQL, a database the database we'll use with our Ruby on Rails stack.

## Check Previous Installs

If you have already experimented with ruby or Ruby on Rails before, verify your versions are correct for this upcoming class.

1. In your Terminal, run `ruby --version`.  The output will include the version number of ruby you have installed. **Verify you are running version 2.0+ of Ruby and that it does not say `universal.x86-64`**.  The `universal` build is the one that comes with OS X, we want to use a ruby version supplied by RVM.
2. In your Terminal, run `rails --version`. **Verify you are running version 4 of Ruby on Rails**.
3. In your Terminal, run `rvm list`.  **Verify you have version 1.26.x or greater.**

If you are using an earlier version of RVM, Ruby or Rails, continue with the instructions to get your environment set up. Run these version commands in the Terminal again after you're done to ensure everything is working properly.


## RVM and Ruby

<a href="http://www.rvm.io" target="_new">RVM</a> is a Ruby Version Manager. It lets you easily switch between versions of the ruby programming language for different projects.

1. Run the following command to install both RVM and the latest version of Ruby.

    ```
    \curl -L https://get.rvm.io | bash -s stable --ruby --auto-dotfiles
    ```

**VERY IMPORTANT:**  When the installation is complete type `which ruby` in the terminal. The response should be `~/<your_user_name>/...` NOT `~/usr/...`



## Ruby on Rails 4

Ruby packages are referred to as "gems". 

1. Use the following command to install Rails 4.
    
    ```
    gem install rails
    ```

This might take a few minutes. 
If this causes errors on your machine, ask for help.


## PostgreSQL 

### Postgres

1. Install postgres via Homebrew
  ```bash
  brew install postgres
  ```

2. Configure postgres to start when the system does.

  ```bash
  mkdir -p ~/Library/LaunchAgents

  ln -sfv /usr/local/opt/postgresql/*.plist ~/Library/LaunchAgents
  ```

3. Check that your install worked

    ```bash
    which psql
    ```

## Ruby linter
Let's install one more Atom package; this time it's a linter for ruby code.

1. In the terminal run `apm install linter-ruby`

<details>
<summary>Postico (optional)</summary>
### Postico

Postico is a GUI tool to view the contents of your Postgres database. 

1. Go to <a href="https://eggerapps.at/postico/" target="_new">eggerapps.at/postico/</a> and download the free version.
2. Install it by unzipping the downloaded zip and then dragging `Postico.app` into your `Applications` directory.

</details>


### Congratulations!
This completes Installfest!


