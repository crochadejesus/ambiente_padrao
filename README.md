# Source.list
```
deb http://deb.debian.org/debian/ stretch main non-free contrib
deb-src http://deb.debian.org/debian/ stretch main non-free contrib

deb http://deb.debian.org/security/ stretch/updates main contrib non-free

deb http://security.debian.org/debian-security stretch/updates main contrib non-free
deb-src http://security.debian.org/debian-security stretch/updates main contrib non-free

# stretch-updates, previously known as 'volatile'
deb http://deb.debian.org/debian/ stretch-updates main contrib non-free
deb-src http://deb.debian.org/debian/ stretch-updates main contrib non-free

# stretch-backports, previously on backports.debian.org
deb http://deb.debian.org/debian/ stretch-backports main contrib non-free
deb-src http://deb.debian.org/debian/ stretch-backports main contrib non-free

```

# Configuração padrão de um Debian
```
$ sudo apt-get install apt-transport-https dirmngr curl msmtp-mta evince evince-common geany-common \
geany-plugin-addons geany-plugin-autoclose geany-plugin-automark geany-plugin-codenav \
geany-plugin-commander geany-plugin-ctags geany-plugin-debugger geany-plugin-defineformat \
geany-plugin-insertnum geany-plugin-macro geany-plugin-markdown libgconf-2-4 aptitude gconf2-common \
geany-plugins geany-plugins-common dia dia-common dia-gnome dia-libs dia-rib-network dia-shapes dia2code \
git git-man git-all git-completion git-review kdiff3 flatpak openshot blender inkscape flowblade \
liberror-perl patch rsync pkg-config erlang libicu-dev libmozjs185-dev libcurl4-openssl-dev libuv1 \
make gcc autoconf libtool automake build-essential fakeroot curl ttf-mscorefonts-installer -y
```

## Mono
```
Debian 9 (i386, amd64, armhf, armel)

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
echo "deb https://download.mono-project.com/repo/debian stable-stretch main" | sudo tee /etc/apt/sources.list.d/mono-official-stable.list
sudo apt update
sudo apt install mono-devel
```

## Monodevelop
```
Debian 9 (i386, amd64, armhf, armel)

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
echo "deb https://download.mono-project.com/repo/debian vs-stretch main" | sudo tee /etc/apt/sources.list.d/mono-official-vs.list
sudo apt update
sudo apt-get install monodevelop
```

Pacotes necessários para compilar Monodevelop a partir do GitHub
```
libglib2.0-cil  libglib2.0-cil-dev  libgtk2.0-cil  libgtk2.0-cil-dev  libwebkit1.1-cil  monodoc-base  monodoc-browser  monodoc-manual  monodoc-gtk3.0-manual  libgnome2.24-cil  libgnome2.0-cil-dev  libart2.0-cil  libart2.0-cil-dev  libgconf2.0-cil  libgnome-vfs2.0-cil  libgnome-vfs2.0-cil-dev  libgnome2.0-cil-dev  libgnome2.24-cil  libgconf2.0-cil-dev  libgcrypt20-dev  libgpg-error-dev  libssh2-1-dev  libnuget-core-cil  nuget
```
Install de referenceassemblies-pcl
http://download.mono-project.com/repo/debian/pool/main/r/referenceassemblies-pcl/
```
$ sudo apt-get install gtk-sharp2 gtk-sharp2-examples gnome-sharp2 libssh2-1-dev fsharp cmake -y
$ cd ~/Workspace/fontes/dotnet
$ git clone https://github.com/mono/monodevelop.git
$ cd monodevelop
$ git submodule update --init --recursive

$ cd ~/Workspace/fontes/dotnet/monodevelop
$ git tag // Comando para ver as últimas tags criadas
$ git checkout monodevelop-7.3.2.12
$ ./configure --profile=stable
$ make
$ sudo make install
```

## NodeJS
```
For Node.js 10:

curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
```

## LibreOffice
### Remover LibreOffice padrão
Baixar última versão do LibreOffice do site oficial https://www.libreoffice.org/.
Baixar o torrent que é mais rápido.
Tanto o main installer quanto a interface translated português (Brasil).
```
$ cd ~/Downloads
$ tar xvzf LibreOffice_6.1.2_Linux_x86-64_deb.tar.gz
$ cd LibreOffice_6.1.2_Linux_x86-64_deb/DEBS
$ sudo dpkg -i *
```

## Java
Acessar o site http://www.oracle.com/technetwork/java/javase/downloads/ para abaixar uma versão do JRE.
```
$ cd ~/Downloads/
$ sudo dpkg -i jdk-11_linux-x64_bin.deb
```
Segundo o tutorial do [Viva o Linux](https://www.vivaolinux.com.br/artigo/Instalacao-do-Java-da-Oracle-em-distros-Debian-like/)


## CouchDB

#2.1. Installation on Unix-like systems
This manual can acessed by http://docs.couchdb.org/en/latest/install/unix.html#installation-from-source
Download the fonts in: http://mirrors.up.pt/pub/apache/couchdb/source/2.2.0/apache-couchdb-2.2.0.tar.gz

#2.1.2. Dependencies
You should have the following installed:
```
Erlang OTP (>=R61B03, =<19.x)
ICU
OpenSSL
Mozilla SpiderMonkey (1.8.5)
GNU Make
GNU Compiler Collection
libcurl
help2man
Python (>=2.7) for docs
Python Sphinx (>=1.1.3)
```
It is recommended that you install Erlang OTP R16B03-1 or above where possible. You will only need libcurl if you plan to run the JavaScript test suite. And help2man is only need if you plan on installing the CouchDB man pages. Python and Sphinx are only required for building the online documentation. Documentation build can be disabled by adding the --disable-docs flag to the configure script.

Debian-based Systems
You can install the dependencies by running:
```
sudo apt-get --no-install-recommends -y install \
    build-essential pkg-config erlang \
    libicu-dev libmozjs185-dev libcurl4-openssl-dev
```
Be sure to update the version numbers to match your system’s available packages.

#2.1.4. Installing
Once you have satisfied the dependencies you should run:
```
tar xvzf apache-couchdb-2.2.0.tar.gz
cd apache-couchdb-2.2.0/
./configure
```
If you wish to customize the installation, pass --help to this script.
If everything was successful you should see the following message:
```
==> configuring couchdb in rel/couchdb.config
You have configured Apache CouchDB, time to relax. Relax.
```

To build CouchDB you should run:
```
make release
```
Try gmake if make is giving you any problems.
If everything was successful you should see the following message:
```
... done
You can now copy the rel/couchdb directory anywhere on your system.
Start CouchDB with ./bin/couchdb from within that directory.
```

#2.1.5. User Registration and Security
You should create a special couchdb user for CouchDB.
On many Unix-like systems you can run:
adduser --system \
        --shell /bin/bash \
        --group --gecos \
        "CouchDB Administrator" couchdb

You must make sure that:
The user has a working POSIX shell
The user’s home directory is wherever you have copied the release. As a recommendation, copy the rel/couchdb directory into /opt/couchdb or /home/couchdb.
You can test this by:
Trying to log in as the couchdb user
Running pwd and checking the present working directory
Copy the built couchdb release to the new user’s home directory:
cp -R /path/to/couchdb/rel/couchdb /opt/couchdb

Change the ownership of the CouchDB directories by running:
chown -R couchdb:couchdb /opt/couchdb


Change the permission of the CouchDB directories by running:
find /opt/couchdb -type d -exec chmod 0770 {} \;


Update the permissions for your ini files:
chmod 0744 /opt/couchdb/etc/


2.1.6. First Run
You can start the CouchDB server by running:
sudo -i -u couchdb couchdb/bin/couchdb


This uses the sudo command to run the couchdb command as the couchdb user.
When CouchDB starts it should eventually display the following message:
Apache CouchDB has started, time to relax.


Relax.
To check that everything has worked, point your web browser to:
http://127.0.0.1:5984/_utils/index.html


From here you should verify your installation by pointing your web browser to:
http://localhost:5984/_utils/verify_install.html


2.1.7. Running as a Daemon
CouchDB no longer ships with any daemonization scripts.
The CouchDB team recommends runit to run CouchDB persistently and reliably. According to official site:
runit is a cross-platform Unix init scheme with service supervision, a replacement for sysvinit, and other init schemes. It runs on GNU/Linux, *BSD, MacOSX, Solaris, and can easily be adapted to other Unix operating systems.
Configuration of runit is straightforward; if you have questions, contact the CouchDB user mailing list or IRC-channel #couchdb in FreeNode network.
Let’s consider configuring runit on Ubuntu 16.04. The following steps should be considered only as an example. Details will vary by operating system and distribution. Check your system’s package management tools for specifics.
Install runit:
sudo apt-get install runit


Create a directory where logs will be written:
sudo mkdir /var/log/couchdb
sudo chown couchdb:couchdb /var/log/couchdb


Create directories that will contain runit configuration for CouchDB:
sudo mkdir /etc/sv/couchdb
sudo mkdir /etc/sv/couchdb/log


Create /etc/sv/couchdb/log/run script:
#!/bin/sh
exec svlogd -tt /var/log/couchdb


Basically it determines where and how exactly logs will be written. See man svlogd for more details.
Create /etc/sv/couchdb/run:
#!/bin/sh
export HOME=/home/couchdb
exec 2>&1
exec chpst -u couchdb /home/couchdb/bin/couchdb


This script determines how exactly CouchDB will be launched. Feel free to add any additional arguments and environment variables here if necessary.
Make scripts executable:
sudo chmod u+x /etc/sv/couchdb/log/run
sudo chmod u+x /etc/sv/couchdb/run


Then run:
sudo ln -s /etc/sv/couchdb/ /etc/service/couchdb


In a few seconds runit will discover a new symlink and start CouchDB. You can control CouchDB service like this:
sudo sv status couchdb
sudo sv stop couchdb
sudo sv start couchdb


Naturally now CouchDB will start automatically shortly after system starts.
You can also configure systemd, launchd or SysV-init daemons to launch CouchDB and keep it running using standard configuration files. Consult your system documentation for more information.


2.7.1. Single Node Setup
A single node CouchDB 2.0 installation is what most users will be using. It is roughly equivalent to the CouchDB 1.x-series. Note that a single-node setup obviously doesn’t take any advantage of the new scaling and fault-tolerance features in CouchDB 2.0.
After installation and initial startup, visit Fauxton at http://127.0.0.1:5984/_utils#setup. You will be asked to set up CouchDB as a single-node instance or set up a cluster. When you click “Single-Node-Setup”, you will get asked for an admin username and password. Choose them well and remember them. You can also bind CouchDB to a public address, so it is accessible within your LAN or the public, if you are doing this on a public VM. Or, you can keep the installation private by binding only to 127.0.0.1 (localhost). The wizard then configures your admin username and password and creates the three system databases _users, _replicator and _global_changes for you.
Alternatively, if you don’t want to use the “Single-Node-Setup” wizard and run 2.0 as a single node with admin username and password already configured, make sure to create the three three system databases manually on startup:
curl -X PUT http://127.0.0.1:5984/_users

curl -X PUT http://127.0.0.1:5984/_replicator

curl -X PUT http://127.0.0.1:5984/_global_changes
