update archinstall
`pacman -Sy archinstall`

wget and curl package

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

