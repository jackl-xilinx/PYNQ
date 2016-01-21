## Ubuntu Scripts

1. *configure_jupyter.sh* : set up the ethernet connection and configure Jupyter to be launched with the DHCP given IP address. A message at the end will provide further instructions

2. *xilinx_proxy.sh* : set or unset the Xilinx internal network proxy

3. *py_package.sh*: run this script to know where to put your packages to be used by Jupyter. The script will create the specified path if it does not exists. To copy the package, you can use [WinSCP](https://winscp.net/eng/download.php) creating a *New Site* with protocol *SFTP*, Host name the ip of the board (that you can get typing `hostname -I` from terminal or executing the *configure_jupyter.sh* script), Port number *22* and User name *xpp*. The password is also *xpp*. If you leave the password entry empty, it will be asked at every log in.
You can obviously copy the package using your method of choice instead.
In this repository, the *pyxi* package is located under /python/pyxi

Remember to run
```
chmod +x <selected_scritp.sh>
```
to make it executable before you launch it.

### Installing `pyxi` easily using pip
an easy alternative to script #3 is to install the pyxi package using `pip` directly (and avoid all the hassle of manually copying files). To do that, simply type from a terminal
```
pip install -e 'git+https://github.com/Xilinx/Pyxi@master#egg=pyxi&subdirectory=python'
```

------------------------------------------------------------------------------------------------------
### Ubuntu Core image for Zybo

latest image available at: [file://xco-smb/gnatale/public/](file://xco-smb/gnatale/public/)

```
LATEST CHANGELOG:
01-20-2016 - <giuseppe.natale@xilinx.com>
             1) Full support for the popular python packages (matplotlib, 
                pandas, numpy, scipy..ecc for a list type `help(modules)` 
                in a python shell)
             2) A first release of pyxi is available and it can be imported 
                from Jupyter. Just remember to launch jupyter with ‘sudo’ 
                (as specified by the message in ./configure_jupyter.h) since 
                we need root permissions to use pyxi. Currently, only 
                on-board device (LEDs, Switches, Buttons) are supported, the
                rest is still there but is leftover from the old release, 
                therefore is not usable.
```