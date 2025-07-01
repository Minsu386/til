[[PopOS]]


### Update the OS
----
`sudo apt update && sudo apt upgrade -y`

### Clean up kernal
----
`sudo apt autoremove -y`
`sudo apt autoclean -y`

### ZSH
----
`sudo apt install zsh`
### Oh-My-ZSH
----
Install ZSH before Oh-My-ZSH

[Oh-My-ZSH][https://github.com/ohmyzsh/ohmyzsh]
```wget
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/
install.sh -O -)"
```

### Version Control
----
`sudo apt-get install git`

Once the installation is complete, verify the Git version by running
`git --version`

Now that Git is installed, it is ready to be configured. Setup your name and email address for Git to associate your commits
`git config --global user.name "<username>"`
`git config --global user.email "<email>"`

[Generate SSH for Github][https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent]
````shell
ssh-keygen -t ed25519 -C "your_email@example.com"
````

start SSH agent
```shell
$ eval "$(ssh-agent -s)"
```

Add SSH to ssh-agent
```shell
ssh-add ~/.ssh/id_ed25519
```

[Add SSH to Github][https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account]
```shell
$ cat ~/.ssh/id_ed25519.pub
# Then select and copy the contents of the id_ed25519.pub file
# displayed in the terminal to your clipboard
```



### NeoVim
----
```
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim.appimage
chmod u+x nvim.appimage
./nvim.appimage
```

```
./nvim.appimage --appimage-extract
./squashfs-root/AppRun --version

# Optional: exposing nvim globally.
sudo mv squashfs-root /
sudo ln -s /squashfs-root/AppRun /usr/bin/nvim
nvim
```

If you are in the file explorer mode, you can use:

> `d` for creating a directory
> 
> `%` for creating a new file

You can get into the explorer mode with issuing a command `:Ex` or `:Sexplore` or `:Vexplore`


#### NeoVim Configuration
----

### [[nvim KeyMaping]]
----
`<leader> = Space`
vim's Tree map - `<leader>pv`
(Fuzzy Finder) tree /w/ preview - `<leader>pf`

	live-grep is required for grep search
	[live-grep from BurntSushi][https://github.com/Burntsushi/ripgrep]  
	`curl -LO https://github.com/BurntSushi/ripgrep/releases/download/13.0.0/ripgrep_13.0.0_amd64.deb`
	`sudo dpkg -i ripgrep_13.0.0_amd64.deb`

Grep Search - `<leader>ps`

# Remember
----
nvim-lint and how to configure for python and other languages.