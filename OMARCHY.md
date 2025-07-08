wifi setup:
`iwctl`
`device list`
`station wlan0 get-networks`
`station wlan0 connect "your ssid"`


update archinstall
`pacman -Sy archinstall`

wget and curl package

github email
`38228979+Minsu386@users.noreply.github.com`

Update 1Password public key
```
curl -sS https://downloads.1password.com/linux/keys/1password.asc | gpg --import
```

public key Spotify
```
curl -sS https://download.spotify.com/debian/pubkey_C85668DF69375001.gpg | gpg --import
```

public key dropbox
```
gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys FC918B335044912E

```

or 
`gpg --recv-keys 1C61A2656FB57B7E4DE0F4C1FC918B335044912E`

install omarch
`wget -qO- https://omarchy.org/install | bash`
