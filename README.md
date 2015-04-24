# WebPageTest Private Instance with Vagrant

Easily create your own WebPageTest Private Instance with Vagrant.

WebPagetest is used for measuring and analyzing the performance of web pages.

WebPagetest Private Instance : [official documentation](https://sites.google.com/a/webpagetest.org/docs/private-instances)

## Requirements

Install:
- [Git](http://git-scm.com/)
- [Virtual Box](https://www.virtualbox.org/)
- [Vagrant](https://www.vagrantup.com/)

(Optional)
- [cmder](http://gooseberrycreative.com/cmder/) (terminal with SSH for Windows)

## Install the server

Open a terminal in your favorite path.

### Clone the project from GitHub

> $ mkdir webpagetest
> $ cd webpagetest  
> $ git clone https://github.com/NicoPennec/vagrant-webpagetest.git  
> $ cd vagrant

### Init Box Vagrant

> $ vagrant box add hashicorp/precise32

### Configuration behind a proxy (optional)

> $ vagrant plugin install vagrant-proxyconf

Edit the `Vagrantfile` file:

- config.proxy.http     = "`http://your_proxy_:8080`"
- config.proxy.https    = "`http://your_proxy:8080`"
- config.proxy.no_proxy = "localhost,127.0.0.1"

### Update your hosts

Edit your `hosts` configuration file:

- Linux: `/etc/hosts`
- MacOS: `/private/etc/hosts`
- Windows: `C:\Windows\System32\drivers\etc\`

> 127.0.0.1   webpagetest

### Run the VM

> $ vagrant up

#### (Optional)

Open a SSH connection:
> $ vagrant ssh

Logout the SHH connection
> vagrant@webpagetest:~$ logout

### Open your WebPageTest Private Instance

[http://webpagetest:8080/](http://webpagetest:8080/)

### Stop the VM

> $ vagrant halt
