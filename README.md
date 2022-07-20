# pwa-studio-installer
Magento's pwa-studio installer using github action. 

This action will download the latest release of the magento [pwa-studio project](https://github.com/magento/pwa-studio/releases) source code and copy it into the github repository calling it.
Or you can simply clone/fork and push the content of this repository to bootstrap a new pwa-studio project. **actions/checkout@v2** is mandatory (v2 and up).
<div align="center">
  <a href="https://www.youtube.com/watch?v=cqI79AKN7Gk"><img src="https://user-images.githubusercontent.com/3765910/154555377-2ab4d165-9bbb-42a4-b6cf-22586156477d.png" alt="install pwa-studio using github actions"></a>
  <span>Install process in video</scan>
</div>


```
name: pwa-studio-install-actions
on: [push]
jobs:
  magento2-install:
    runs-on: ubuntu-latest
    name: 'install & push pwa-studio project'      
    steps:
    - uses: actions/checkout@v2
    - name: 'install fresh  pwa studio code and copy to repo'
      uses: MAD-I-T/magento-actions@v3.12
      with:
        process: 'pwa-studio-install'
        #no_push: 1 //uncomment this to prevent files from getting pushed to repo
```
