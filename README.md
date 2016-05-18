# Source.list
```
deb http://debian.pop-sc.rnp.br/debian/ jessie main non-free contrib
deb-src http://debian.pop-sc.rnp.br/debian/ jessie main non-free contrib
deb http://sft.if.usp.br/debian/ jessie main non-free contrib
deb-src http://sft.if.usp.br/debian/ jessie main non-free contrib

deb http://security.debian.org/ jessie/updates main contrib non-free
deb-src http://security.debian.org/ jessie/updates main contrib non-free

# jessie-updates, previously known as 'volatile'
deb http://debian.pop-sc.rnp.br/debian/ jessie-updates main contrib non-free
deb-src http://debian.pop-sc.rnp.br/debian/ jessie-updates main contrib non-free
deb http://sft.if.usp.br/debian/ jessie-updates main contrib non-free
deb-src http://sft.if.usp.br/debian/ jessie-updates main contrib non-free

# jessie-backports, previously on backports.debian.org
deb http://debian.pop-sc.rnp.br/debian/ jessie-backports main contrib non-free
deb-src http://debian.pop-sc.rnp.br/debian/ jessie-backports main contrib non-free
deb http://sft.if.usp.br/debian/ jessie-backports main contrib non-free
deb-src http://sft.if.usp.br/debian/ jessie-backports main contrib non-free
```

# Configuração padrão de um Debian
```
$ sudo aptitude install msmtp-mta evince-gtk eric libav-tools libavcodec-extra-56 \
libavformat-ffmpeg56 libavcodec-ffmpeg-extra56 geany-abi-69 geany-abi-71 geany-common \
geany-plugin-addons geany-plugin-autoclose geany-plugin-automark geany-plugin-codenav \
geany-plugin-commander geany-plugin-ctags geany-plugin-debugger geany-plugin-defineformat \
geany-plugin-devhelp geany-plugin-doc geany-plugin-extrasel geany-plugin-gendoc \
geany-plugin-geniuspaste geany-plugin-git-changebar geany-plugin-gproject \
geany-plugin-insertnum geany-plugin-latex geany-plugin-lipsum geany-plugin-lua \
geany-plugin-macro geany-plugin-markdown geany-plugin-miniscript \
geany-plugin-multiterm geany-plugin-numberedbookmarks geany-plugin-overview \
geany-plugin-pairtaghighlighter geany-plugin-pg geany-plugin-pohelper \
geany-plugin-prettyprinter geany-plugin-prj geany-plugin-projectorganizer \
geany-plugin-py geany-plugin-scope geany-plugin-sendmail geany-plugin-shiftcolumn \
geany-plugin-spellcheck geany-plugin-tableconvert geany-plugin-treebrowser \
geany-plugin-updatechecker geany-plugin-vc geany-plugin-webhelper \
geany-plugin-xmlsnippets geany-plugins geany-plugins-common python3-virtualenv \
python python-gtk2 python-zope.interface python-psycopg2 python-imaging \
python-reportlab postgresql postgresql-client postgresql-contrib python-dateutil \
python-mako python-gudev python-poppler python-webkit python-twisted-core \
python-setuptools pep8 pyflakes python-mock python-twisted-web librsvg2-common \
python-xlwt pylint python-storm python2.7 python-setuptools python-genshi \
python-pygments python-babel python-tz python-psycopg2 postgresql-9.4 apache2 \
libapache2-mod-wsgi libapache2-mod-python docutils pgadmin3 dia dia-common \
dia-gnome gettext intltool dia-libs dia-rib-network dia-shapes dia2code \
git git-all git-completion git-el git-review xsltproc kdiff3 emacs24 \
emacs24-bin-common emacs24-common chromium chromium-l10n cmake binutils \
libasan1 make gcc g++-4.9 autoconf libtool automake build-essential \
gettext libgdiplus bluefish bluefish-plugins gksu libgksu2-0 libgtop2-7 libgtop2-common \
python-glade2 python-notify python-wicd rfkill wicd wicd-daemon wicd-gtk curl ttf-mscorefonts-installer -y
```

## Mono
```
$ sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
$ echo "deb http://download.mono-project.com/repo/debian wheezy main" | sudo tee /etc/apt/sources.list.d/mono-xamarin.list
$ echo "deb http://download.mono-project.com/repo/debian wheezy-apache24-compat main" | sudo tee -a /etc/apt/sources.list.d/mono-xamarin.list
$ echo "deb http://download.mono-project.com/repo/debian wheezy-libjpeg62-compat main" | sudo tee -a /etc/apt/sources.list.d/mono-xamarin.list
$ echo "deb http://download.mono-project.com/repo/debian wheezy-libtiff-compat main" | sudo tee -a /etc/apt/sources.list.d/mono-xamarin.list
$ sudo apt-get update
$ sudo aptitude install mono-4.0-gac mono-4.0-service mono-addins-utils \
mono-apache-server4 mono-basic-dbg mono-complete mono-csharp-shell mono-dbg \
mono-devel mono-dmcs mono-fastcgi-server4 mono-fpm-server mono-gac mono-gmcs  \
mono-mcs mono-profiler mono-runtime mono-runtime-common mono-runtime-dbg \
mono-runtime-sgen  mono-tools-devel mono-tools-gui mono-utils mono-xbuild \
mono-xsp mono-xsp4 mono-xsp4-base mono-tools-devel mono-tools-gui \
monodoc-gtk3.0-manual monodoc-gtk2.0-manual monodoc-hexbox-manual monodoc-http \
monodoc-newtonsoft-json-manual monodoc-nunit-manual -y
```

## Monodevelop
```
$ sudo aptitude install libglib2.0-ci libglib2.0-cil-dev gtk-sharp2 gtk-sharp2-examples gnome-sharp2 libssh2-1-dev referenceassemblies-pcl -y
$ cd ~/Workspace/fontes/dotnet
$ git clone https://github.com/mono/monodevelop.git
$ cd monodevelop
$ git submodule update --init --recursive

$ cd ~/Workspace/fontes/dotnet/monodevelop
$ git tag // Comando para ver as últimas tags criadas
$ git checkout monodevelop-6.1.0.817
$ ./configure --profile=stable
$ make
$ sudo make install
```

## NodeJS
```
$ cd ~/Workspace/fontes/
$ git clone https://github.com/nodejs/node.git
$ cd node
$ git tag // Comando para ver as últimas tags criadas
$ git checkout v6.1.0
$ ./configure
$ make
$ sudo make install
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

Abaixar última versão do LibreOffice do site oficial https://www.libreoffice.org/.
Abaixar o torrent que é mais rápido, usar a extensão Torrent Tornado do Firefox.
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
