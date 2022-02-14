# install github

brew install git


# #checking version of GIT

git --version


# installomg GH CLI
brew install gh
gh --version
brew upgrade gh


# Generating a new SSH key
ssh-keygen -t ed25519 -C "email"

# Adding your SSH key to the ssh-agent
1. Start the ssh-agent in the background.

eval "$(ssh-agent -s)"

# First, check to see if your ~/.ssh/config file exists in the default location.
open ~/.ssh/config

# Check the file
vi ~/.ssh/config

# If the file doesn't exist, create the file.
touch ~/.ssh/config

# edit file and add a few lines
vi ~/.ssh/config
--- cut ---
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
--- cut ---


# Add your SSH private key to the ssh-agent and store your passphrase in the keychain
ssh-add -K ~/.ssh/id_ed25519


2. Adding a new SSH key to your GitHub account
pbcopy < ~/.ssh/id_ed25519
# and paste to your GitHub account

# !!!!!
but it will NOT work
# !!!!!

# Generating a new SSH key
ssh-keygen -o -C "email"

# # # # Users/sergiy/.ssh/id_rsa.
# # # # Your public key has been saved in /Users/sergiy/.ssh/id_rsa.pub.
vi ~/.ssh/config
--- cut ---
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
--- cut ---

# Add your SSH private key to the ssh-agent and store your passphrase in the keychain
ssh-add -K ~/.ssh/id_rsa

2. Adding a new SSH key to your GitHub account
pbcopy < ~/.ssh/id_rsa.pub
# and paste to your GitHub account

3. now we can use 
# Adding our user name
git config --global user.name "user.mname"
# adding our email address
git config --global user.email "email"
# To check the configuration
git config --global --list

# View your remote repositories
git remote -v

# Init git repo locally
git init

# creating a new file
touch day1lab1.md
touch README.md

# adding the file
git add .

# checking the status
git status

# Stage and commit all changes
git commit -a -m "this is my very first commit"

# adding remote repo
git remote add origin git@github.com:ssheff/class.git

# creating a new repo on GitHub - NOT FOR THE DEMO LIVE! - this will create the repo in github.
curl -u USERNAME:PASSWORD https://api.github.com/user/repos -d '{"name":"class"}' 


# manually creting GitHub repo

1. navigate to your github account

2. create new

3. neter the name of the repo that you would like to have

4. it will give you few options on how to start working with it

 - create a new repository on the command line:

--- code ---
echo "# class" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:ssheff/class.git
git push -u origin main
--- code ---

 - push an existing repository from the command line
git remote add origin git@github.com:ssheff/class.git
git branch -M main
git push -u origin main

- #  lastly, let's modify our file and poush it to the repo
vi test.md 
add .
git commit -a -m "this is my very first comimt"
git push -u origin main

# navigate back to the GitHub URL anc check

# We have learned how to work with Git and GitHub

