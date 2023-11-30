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
sudo apt install neovim
```


#### NeoVim Configuration
----

