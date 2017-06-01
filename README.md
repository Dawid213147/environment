# Vagrant package for 4human system

## Who's responsible for

* Krzysztof Kąkol <kkakol@pgs-soft.com>

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

## Usage

* You can log in to local ubuntu machine by using vagrant ssh
* Pull all repos to correct folders (named after the repo names)
* You will have automatically the following subdomains set up:
  * iam.4human.srv
  * workflow.4human.srv
  * dataprovider.4human.srv
  * handbook.4human.srv
  * front.4human.srv
  * translation.4human.srv
  * supervisor.4human.srv
  * queue.4human.srv
* The above point will work as long as you follow the build instructions for the app parts you're interested in

## RabbitMQ

This playbook installs RabbitMQ on the virtual machine. RabbitMQ management console is available under:
http://192.168.56.133:15672
http://queue.4human.srv
user: admin
password: password

## Supervisor

It is used to manage processes like queue consumer.
Supervisor web interface is available under:

[Supervisor](http://192.168.56.133:9001)
* supervisor.4human.srv
* user: supervisor
* password: supervisor4human

## How to fix 504 nginx error

```apacheconfig
#/etc/php/7.1/fpm/pool.d/www.conf

pm = dynamic
pm.max_children = 70
pm.start_servers = 20
pm.min_spare_servers = 20
pm.max_spare_servers = 35
pm.max_requests = 5000
```
