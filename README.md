## How it all began....
Sunday, 24. December 2017, my Ubuntu 17.10 boots into emergency mode every time because of some apparmor initialisation problem that no question on askubuntu seems to address or resolve. Funnily there were more questions about this on Redhat and Fedora forums. Secondly I haven't been able to run spacy for a while because of Cython dependency problems that probably creeped in while upgrading to 17.10. Lastly, my laptop, HP Omen seems to be heating way more than it ought to while running Linux and I couldn't figure why. 


## Home Sweet Home
Because I had initially installed Ubuntu on my SSD with my home as a seperate partition on my Hard Disk, the first task involved restoring that partition as home. 
This was helpful :
	https://help.ubuntu.com/community/Partitioning/Home/Moving

First things first:
```
sudo apt update
sudo apt upgrade
```
#### Difference between apt and apt-get :
*tl;dr* **apt**, introduced in 16.04 is a newer alternative to “Apt-get.” More efficient, more secure, and more user friendly. 
[Source](https://www.maketecheasier.com/apt-vs-apt-get-ubuntu/)


#### Difference between update and upgrade :
- ```apt-get update``` updates the list of available packages and their versions, but it does not install or upgrade any packages.
- ```apt-get upgrade``` actually installs newer versions of the packages you have. After updating the lists, the package manager knows about available updates for the software you have installed. This is why you first want to update.

[Source](https://askubuntu.com/questions/94102/what-is-the-difference-between-apt-get-update-and-upgrade) 

# git init
Apparently Ubuntu 17.04 doesn't come with git pre-installed. Sigh. 
```
sudo apt install git
git init Noobuntu
```
So we have a repository, now for a markdown editor to write all this down. 
Download the [deb package](https://remarkableapp.github.io/files/remarkable_1.87_all.deb) for [Remarkable](https://remarkableapp.github.io/index.html). 
Install with 
```
sudo dpkg -i remarkable_1.87_all.deb
sudo apt-get install -f
```

# Bash is boring. Installing [zsh + Oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
```
# Installing zsh
sudo apt install zsh
# Installing oh-my-zsh to tweak zsh
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```
To change your [Theme](https://github.com/robbyrussell/oh-my-zsh#themes) : 
```gedit ~/.zshrc``` and replace ZSH_THEME with any theme name from [here](https://github.com/robbyrussell/oh-my-zsh/wiki/themes)

If you're using a theme with powerline characters, like *agnoster*. you'll need to install [them](https://github.com/powerline/fonts) 
```
git clone https://github.com/powerline/fonts.git --depth=1
cd fonts
./install.sh
cd ..
rm -rf fonts
```
and change your terminal's font in 
```Edit > Profile Preferences > Custom Font```

To set zsh as the default terminal
```chsh -s $(which zsh)```

# Let the tweaks begin
Install [Unity Tweak Tool](apt://unity-tweak-tool)

Since I personally dislike the Unity launcher, I'm going to hide the launcher and replace it with it a Mac-like dock.
```sudo apt install docky```
If you'd like Docky to start as soon you boot, add it to your **Startup Applications** (search  in Dash)
#### Changing Themes
Download the theme's zip file and paste it in ```/usr/share/themes/```
What I use : https://github.com/natanfelles/Numix-dark

#### Changing Icons
Download the zip of the icon pack and paste it in ````/usr/share/icons/```
What I use : https://github.com/DarkknightAK/breeze-icon-theme

#### Changing Fonts
Get fonts from https://www.dafont.com/.
Unzip and install the otf/ttf files.
Change required font in the Fonts section of Unity Tweak Tool.
What I use : https://www.dafont.com/roboto.font

