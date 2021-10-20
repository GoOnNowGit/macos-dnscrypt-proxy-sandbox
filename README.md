# macos-dnscrypt-proxy-sandbox
![workflow](https://github.com/goonnowgit/macos-dnscrypt-proxy-sandbox/actions/workflows/main.yml/badge.svg)

MacOS sandbox for dnscrypt-proxy

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
