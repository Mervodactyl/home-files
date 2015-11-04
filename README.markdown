# Home dotfiles

This contains all my home file configurations (in particular my vim setup) so that I can share it across computers. Before you go diving in, please be aware that there are a few pre-requisites:

### Essential Pre-installations:

check out [badassify](http://jilles.me/badassify-your-terminal-and-shell/)

##### Oh My ZSH ([link](http://ohmyz.sh/))

Internal Terminal 'theme', replaces standard Bash interface

```bash
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

##### zsh-syntax-highlighting

Colours your commands within the Terminal window

```bash
cd ~/.oh-my-zsh && git clone git://github.com/zsh-users/zsh-syntax-highlighting.git  
```
then fire up the editor again and open ~/.zshrc and add the following line to the end of the file: 

```bash
source ~/.oh-my-zsh/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh  
```
run 'source ~/.zshrc' for the changes to take effect or restart

Don't forget its your '~/.zshrc' file which contains your alises, shortcuts, and theme settings

##### Tmux

Used to screen share remote Terminals and more

```bash
brew install tmux
```
##### z

This is a shortcut for when you want to change directories (replaces 'cd' for 'z')

```bash
brew install z
```
##### Git (via homebrew)

Keeps updated this way rather than installed on the mac manually

```bash
brew install git
```
##### Vim (via homebrew)

Vim, ta da

```bash
brew install vim
```

In the cases of Oh My ZSH, Tmux and z, you will get annoying errors if you don't have these programs installed as my config files expect them to be there. If you don't want all the extra chuff and are just after my sexy Vim setup, go ahead and grab the `.vimrc` and `.vimrc.bundle` files, install Vundler, run `:PluginInstall` and away you go!

We are also installing Git and Vim via homebrew because it makes it easier to upgrade both, and also my path (which you will be copying via the `.zshrc` file will be looking for the homebrew installations first.


This repo is designed to work with [homesick](https://github.com/technicalpickles/homesick) which handles all my symlinking for me automatically. Much of the configuration is inspired by [Thoughtbot's dotfiles](https://github.com/thoughtbot/dotfiles).

##### HomeSick

To install, first install [homesick](https://github.com/technicalpickles/homesick):

    gem install homesick

Next step is to FORK this repository. Clone it to your local machine, and make sure you do a find-and-replace across the entire repo for `Merve` and replace it with the name of your User folder. Then go into the .gitconfig file and make sure you change your Git username and email address to your relevant details, unless you want me taking credit for your commits :)

Now commit and push back up to your remote fork. At this point, I would advise you delete the clone on your local machine as you will be re-cloning this via `homesick` so to avoid confusion it's best to have just one version of the repo cloned locally.

Next, use the homesick command to clone this repository:

    homesick clone git@github.com:Mervodactyl/home-files.git
    
You might see the following:
```bash
    home-files has a .homesickrc. Proceed with evaling it? (This could be destructive)
```
Just type 'y' or 'yes'. You can now link its contents into your home dir:

    homesick symlink home-files

run the rc file to get vundler installed:

    homesick rc home-files

and restart your terminal.

You can now use the `hup` command to update your home files and install your vim bundles automatically

##### Rubes

Starts a Ruby server within the directory

##### ngrok

creates a secure localHost, so you can demo without deploying, MUST download/login before you can use it
