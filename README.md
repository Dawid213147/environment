# Vagrant package

## Installation instructions

* Create folder 'project' which will include the following subfolders:
  * ansible
  * iam
  * workflow
  * handbook
  * dataprovider
  * front
  * translation
* Pull this repo into ansible folder
* Install Vagrant and VirtualBox
* Install vagrant plugins using (from windows command line):
  vagrant plugin install vagrant-hostmanager vagrant-vbguest vagrant-cachier
* In bash or SourceTree terminal go to ansible folder and run vagrant up
