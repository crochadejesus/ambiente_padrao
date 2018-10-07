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


Pacotes necessários para compilar Monodevelop a partir do GitHub

libglib2.0-cil  libglib2.0-cil-dev  libgtk2.0-cil  libgtk2.0-cil-dev  libwebkit1.1-cil  monodoc-base  monodoc-browser  monodoc-manual  monodoc-gtk3.0-manual  libgnome2.24-cil  libgnome2.0-cil-dev  libart2.0-cil  libart2.0-cil-dev  libgconf2.0-cil  libgnome-vfs2.0-cil  libgnome-vfs2.0-cil-dev  libgnome2.0-cil-dev  libgnome2.24-cil  libgconf2.0-cil-dev  libgcrypt20-dev  libgpg-error-dev  libssh2-1-dev  libnuget-core-cil  nuget

Install de referenceassemblies-pcl
http://download.mono-project.com/repo/debian/pool/main/r/referenceassemblies-pcl/

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
```
$ sudo aptitude purge libreoffice libreoffice-avmedia-backend-gst \
libreoffice-base libreoffice-base-core libreoffice-base-drivers \
libreoffice-calc libreoffice-common libreoffice-core libreoffice-draw \
libreoffice-gtk libreoffice-help-en-us libreoffice-impress \
libreoffice-java-common libreoffice-l10n-pt-br libreoffice-math \
libreoffice-report-builder-bin libreoffice-sdbc-firebird libreoffice-sdbc-hsqldb \
libreoffice-style-galaxy libreoffice-style-tango libreoffice-writer -y
```

Baixar última versão do LibreOffice do site oficial https://www.libreoffice.org/.
Baixar o torrent que é mais rápido, usar a extensão Torrent Tornado do Firefox.
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
