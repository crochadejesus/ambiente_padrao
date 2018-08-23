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
$ sudo apt-get install apt-transport-https msmtp-mta evince evince-common geany-common \
geany-plugin-addons geany-plugin-autoclose geany-plugin-automark geany-plugin-codenav \
geany-plugin-commander geany-plugin-ctags geany-plugin-debugger geany-plugin-defineformat \
geany-plugin-devhelp geany-plugin-doc geany-plugin-extrasel geany-plugin-git-changebar \
geany-plugin-insertnum geany-plugin-macro geany-plugin-markdown geany-plugin-miniscript \
geany-plugin-numberedbookmarks geany-plugin-overview geany-plugin-shiftcolumn \
geany-plugin-tableconvert geany-plugin-treebrowser \
geany-plugin-updatechecker geany-plugin-vc geany-plugin-webhelper \
geany-plugins geany-plugins-common postgresql postgresql-client postgresql-9.4 apache2 \
pgadmin3 dia dia-common dia-gnome dia-libs dia-rib-network dia-shapes dia2code \
git-all git-completion git-el git-review kdiff3 flatpak \
make gcc autoconf libtool automake build-essential fakeroot curl ttf-mscorefonts-installer -y
```

## Mono
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
echo "deb http://download.mono-project.com/repo/debian stretch main" | sudo tee /etc/apt/sources.list.d/mono-official.list
sudo apt-get update
sudo apt-get install mono-devel mono-complete mono-dbg mono-xsp4 referenceassemblies-pcl
```

## Monodevelop
```
Debian 9 (i386, amd64, armhf, armel)

sudo apt install apt-transport-https dirmngr
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

Optional: install build tools

To compile and install native addons from npm you may also need to install build tools:

sudo apt-get install -y build-essential
```

## Bower, Grunt, Gulp, Yeoman e varios geradores
```
$ sudo npm install -g grunt-cli gulp-cli bower yosay yeoman-environment yeoman-doctor yeoman-character user-home \
update-notifier titleize tabtab string-length sort-on root-check repeating read-pkg-up parse-help package-json opn \
npm-keyword meow lodash insight inquirer humanize-string got fullname figures cross-spawn-async configstore cli-list chalk \
async twig supports-color glob yo generator-karma generator-angular generator-webapp generator-aspnet generator-bootstrap
```
Se não conseguir instalar o yo de forma alguma com os comandos acima tente executar
```
$ sudo npm install n -g
$ sudo n stable
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
$ tar xvzf LibreOffice_5.1.1_Linux_x86-64_deb.tar.gz
$ cd LibreOffice_5.1.1.3_Linux_x86-64_deb/DEBS
$ sudo dpkg -i *
```

## Java
Acessar o site http://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html para abaixar uma versão do JRE.
```
$ sudo apt-get --install-recommends install java-package
$ cd ~/Downloads/java
$ make-jpkg jre-8u92-linux-x64.tar.gz
$ sudo dpkg -i oracle-java8-jre_8u92_amd64.deb
```
Segundo o tutorial do [Viva o Linux](https://www.vivaolinux.com.br/artigo/Instalacao-do-Java-da-Oracle-em-distros-Debian-like/)


## IRPF
```
$ chmod +x IRPF2016Linux-x86_64v1.2.bin
$ chmod +x Receitanet-1.07-x64.bin
$ ./IRPF2016Linux-x86_64v1.2.bin
$ ./Receitanet-1.07-x64.bin

```

