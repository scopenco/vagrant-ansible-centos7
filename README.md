# Vagrant CentOS 7 Environment with Ansible provisiover

### Desciprion

This Vagrant Environment deploy CentOS 7 VM for local development.  
By default `src` directory mount to `/opt/src` and user home directory mount to `/opt/Home`.

### Requirments

* Parallels Desktop or VirtualBox
* [Vagrant](https://www.vagrantup.com/downloads.html) 1.7.0 or higher
* Ruby 2.3 or higher

### Usage
* Install Ansible
* Clone git repository
* `vagrant plugin install vagrant-parallels` for Parallels Desktop only
* `vagrant up`
* run `bundle install && kitchen converge` to create, provision and test VM in Test Kitchen

### Authors

* Author:: Andrei Skopenko (andrei@skopenko.net)
