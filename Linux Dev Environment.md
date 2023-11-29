[[PopOS]]


### Update the OS
----
`sudo apt update && sudo apt upgrade -y`

#### Clean up kernal
----
`sudo apt autoremove -y`
`sudo apt autoclean -y`

#### Oh-My-ZSH
----
[Oh-My-ZSH][https://github.com/ohmyzsh/ohmyzsh]

`sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"`