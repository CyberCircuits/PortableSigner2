Sorry, I've got no install package for Linux right now.

Meanwhile you get an install script.
All you have to do is the following:

1. Install a suitable Java Runtime (example here is Debian / Ubuntu):
    $ sudo apt install --reinstall default-jre-headless tzdata-java
2. unpack PortableSigner-Generic-x.x.xxx.zip:
    $ mkdir /tmp/PortableSigner
    $ cd /tmp/PortableSigner
    $ wget https://downloads.sourceforge.net/project/portablesigner/portablesigner/2.0-Release/PortableSigner-Generic-2.0.38c0573.zip
    $ unzip PortableSigner-Generic-2.0.38c0573.zip
3. Install with install script:
    $ sudo sh ./linux-install.sh
    $ sudo chmod ugo+x /usr/local/PortableSigner/PortableSigner.sh
4. Ready! Try it (argument "-n"" means command line):
    $ /usr/local/bin/PortableSigner -n


The best would be to have a RPM and DEB with the right dependencies.


At the moment, I can give a small support how to run the package under
Ubuntu 9.04. It should be very similar on all other flavors of Linux or
BSD.

What you need:
1. A Java Runtime and on older releases the JCE unrestricted Security policy.
2. The PortableSigner package ;-)

1. Java JRE package.
    You should install the following Java related Ubuntu Desktop:
    # sudo apt install --reinstall default-jre-headless tzdata-java
2. I made an install script "linux-install.sh" which does simply the following:
    make dir /usr/local/PortableSigner
    copy program, lib and needed files in this dir
    symbolic link to /usr/local/bin/PortableSigner (the commandline client!)
    symbolic link to /usr/share/applications/portablesigner.desktop
        (now the program is in the application menu category "Office")
