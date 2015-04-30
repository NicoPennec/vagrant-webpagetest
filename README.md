# WebPageTest Private Instance with Vagrant

## About

Easily create your own local WebPageTest Private Instance with Vagrant.

WebPagetest is used for measuring and analyzing the performance of web pages.

WebPagetest Private Instance : [official documentation](https://sites.google.com/a/webpagetest.org/docs/private-instances)

## Project Status

This project is still in progress
- WPT Server: __ready__ _(Vagrant VM)_
- WPT Agent: __in progress__

## Requirements

Install:
- [Git](http://git-scm.com/)
- [Virtual Box](https://www.virtualbox.org/)
- [Vagrant](https://www.vagrantup.com/)

Optional for Windows:

- [cmder](http://gooseberrycreative.com/cmder/) (terminal with SSH)

## Install

Open a terminal in your favorite path.

### Clone the project from GitHub

```sh
$ git clone https://github.com/NicoPennec/vagrant-webpagetest.git  
$ cd vagrant-webpagetest/vagrant/
```

### Vagrant configuration behind a proxy (optional)

```sh
$ vagrant plugin install vagrant-proxyconf
```

Edit the `Vagrantfile` file:

- config.proxy.http     = "`http://your_proxy_:8080`"
- config.proxy.https    = "`http://your_proxy:8080`"
- config.proxy.no_proxy = "localhost,127.0.0.1"

### Update your hosts

Edit your `hosts` configuration file:

- Linux: `/etc/hosts`
- MacOS: `/private/etc/hosts`
- Windows: `C:\Windows\System32\drivers\etc\`

```sh
127.0.0.1   webpagetest
```

### Init the VM

```sh
$ vagrant provision
```

### Run the VM

```sh
$ vagrant up
```

### Play with your local WebPageTest

[http://webpagetest:8080/](http://webpagetest:8080/)

### Stop the VM

```sh
$ vagrant halt
```
