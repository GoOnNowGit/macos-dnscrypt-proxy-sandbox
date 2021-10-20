# macos-dnscrypt-proxy-sandbox
![workflow](https://github.com/goonnowgit/macos-dnscrypt-proxy-sandbox/actions/workflows/main.yml/badge.svg)

MacOS sandbox for dnscrypt-proxy
## Install
#### Install dnscrypt-proxy (if you haven't already)
```
brew install dnscrypt-proxy
```
#### Clone this repo
```
git clone https://github.com/GoOnNowGit/macos-dnscrypt-proxy-sandbox.git
cd macos-dnscrypt-proxy-sandbox
```
#### Copy the LaunchDaemon plist
```
sudo cp goonnowgit.dnscrypt-proxy.plist /Library/LaunchDaemons
```
#### Copy the sandbox file to a location of your choosing (in this case $HOME)
```
cp dnscrypt-proxy.sb "${HOME}"
```
#### Start the via launchctl
```
sudo launchctl load -w /Library/LaunchDaemons/goonnowgit.dnscrypt-proxy.plist
```
#### Or just do it manually
```
sudo sandbox-exec -f "${HOME}"/dnscrypt-proxy.sb /usr/local/opt/dnscrypt-proxy/sbin/dnscrypt-proxy --config /usr/local/etc/dnscrypt-proxy.toml
```

## How I Started
### I started by accumulating *.sb files across the system
```
mkdir sandbox_files
sudo find / -xdev -name "*.sb" -type f -exec cp {} sandbox_files \; 2>/dev/null
```

`*` Disclaimer: This is still a work in progress and is ultimately for fun and research purposes...

`*` Also, as Apple states in their sandbox files: 
```
WARNING: The sandbox rules in this file currently constitute
Apple System Private Interface and are subject to change at any time and
without notice.
```
