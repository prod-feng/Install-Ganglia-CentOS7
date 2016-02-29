# Install-Ganglia-CentOS7
Install Ganglia on CentOS 7

The following lists the processes that I did to install and configure of ganglia-3.7.2 on CentOS, kernel 3.18.21-17.el7.x86_64.

1 . Download the source file.

2 . Untar the source file:

 > tar zxf ganglia-3.7.1.tar.gz
 
 > tar zxf ganglia-web-3.7.1.tar.gz
 
Before comipiling the source code, you may need to install some extra packages, for example, RRDtool, pkg-config, and their -devel packages too.

3. First, compile and install ganglia core package:

  >  ./configure --with-gmetad --with-python
  
  > gmake
  
  > gmake install
  
4 . Second, install  ganglia-web package.

Edit the Makefile to set the appropriate DIR whereyou want to put the web pakage, update the USER account to run the web service(CentOS: apache). Then run:

> gmake install

That's it! 

If your have firewall running on your server, you may need to enable TCP port: 8651, 8652, and UDP 8649.

For SElinux, you may also need to set the right thing for the TCP/UDP port and also the file/folder property for web service. Or you can simply disable SElinux.


  
