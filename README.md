# SmallTtricks, or Not So Small
Small tricks to make computers eaiser to work with

## Back and Forward mouse key/button in Microsoft Remote Desktop 
Simpley put, AHK (auto hot key) with script 
```
#Left::Browser_Back
#Right::Browser_Forward
``` 
See https://superuser.com/questions/696589/mouse-with-forward-back-buttons-and-remote-desktop </br>
Or download and run the RDP_Key.exe file in this deposite. 

## Make Python work for ArcGIS Pro and Visual Studio Code
ArcGIS Pro comes with Python 3.x 64 bit preinstalled and ArcMap is still with Python 2.7 32 bit. Many GIS folks have ArcMap, ArcGIS Pro installed on their computers. And they also use generic Python programming to automate many GIS works without using ESRI stuff like ArcPy. Making all of them live together causes a lot of trouble and headache (one reason many prefer R to Python). Some tried to use Anaconda to avoid this, but with varied success and luck. The Python 3 with ArcGIS Pro also has Jupyter Notebook, which is super handy for interactive works in Python. Overall, there are a few scenatios for GIS users on Windows Machine (ArcMap and ArcGIS Pro have no Mac OS X versions).

### Stick with ArcGIS Pro's Python 3
In this scenario, there is no need to install another version of Python or Anacondo to make things complex. Just stay with what ArcGIS pro installed. But to make things easier to work with, expose the ArcGIS Pro Python to the system. First, make sure you use the right Python 3 tools (Python Interactive Terminal, IPython, Jupyter Notebook). If you also have ArcMap, which means Python 2.7 has been installed (Python (command line), IDEL (Python GUI)). Also know which version you are using. It is much more convenient to add the Python 3 into the system path, so whenever we type python on command line we will run the Python 3 version that we intended to run (unless you really want to use the older Python 2.7). 

Search "environment" and shoot "Edit the System Environment Variables", add ```C:\Program Files\ArcGIS\Pro\bin\Python\envs\arcgispro-py3``` to the System Path (yours might be different). If you see other versions of Python are also in the Path, remove them so the system and yourself will not be confused.

Of course, ESRI people do not want you to leave ArcGIS products and choose those powerful geospatial packages in Python such as geopandas. Therefore, we must install those packages by ourselves, which is where the frustruation comes from. But the process is no different from what we would do with a freshly installed Python 3. Just run ```python -m pip install packagename``` to install them. As we all know, Python packages are in the hell of dependency networks. Quite often, we need to compile and install some other pacakges first. If you have specific problems with a package, just Google it. More often, using a pre-compiled packages such as those at https://www.lfd.uci.edu/~gohlke/pythonlibs would solve the problem.

### Switch to Visual Studio Code
For those serious Python progammers, Jupyter Notebook is more like a toy and a learning tool, not a real production environment. Today, many choose Visual Studio Code (yes, it is an open source product from Microsoft, which many of us hated for obvious reasons for many years). It is a very powerful tool and much better programming environment for programmers. We just need to install the Python extension in Visual Studio Code. To do so, we must first add the Python that we want to use to the environment variable (System) PATH as explained earlier. Once VS Code can locate Python through the system Path, things are pretty easy: just search and install the Python extension inside VS Code. And the VS Code will also promote us to install the PyLint, with which we can greatly imporve our codeing efficiency. This is the solution that I would recommend. 

Of course, we still need to install extra Python packages that we need just as above mentioned. For example ```python -m pip install pysal``` will install the popular PySAL package. ```python -m pop install Fiona-1.8.4-cp36-cp36m-win_amd64.whl``` will install Fiona, which is required for GeoPandas. Similarly, ```python -m pip install GDAL-2.3.3-cp36-cp36m-win_amd64.whl``` installs GDAL, a dependency of Fiona. 

General steps:
- make sure the default Python is what you intend to use (type ```python``` or ```python --version``` on command line). If it is not, edit the System Environment Settings -> System PATH and make sure it includes the correct python path. 
- be extra cautious if you have two identical Python versions on the same computer. Such as ArcGIS pro installed Python 3.6 and then Anaconda installed another Python 3.6 in a different folder. If python shows version 3.6, you still need to make sure what you are changing or installing packages to is where you want it to happen.
- use the ```python -m install packagename``` to install a package. If the package needs other packages, you will see the complaints or errors. Then install those packages first. 
- if packages require compiling and you do not want to go through the complex configuration and compilation process, just download the precompiled wheels (whl files) and install them directly. 
- in the end, you will see the lovely message like ```Successfully installed geopandas-0.4.0```.  
- but this is not the real end yet. In Python environment, use ```help("modules")``` to see if the package is really installed (be patient). And also use command/function like ```help("geopandas")``` to see if the specific package can be intialized correctly. Or course, the ultimate test is to run lines of real code using the package and see if the code does the right work.

### Use other options, including Anaconda
Other options are essentially using Python installations that are independent from ArcMap Python 2.7 or ArcGIS Pro Python 3.x. Just remember not to mess around with the ArcGIS folders and paths (You can always check the system path envrionment variable). One simple trick that works most times is not to install Python or Anaconda to the ```Programming Files``` folder, which help, not guarantee though, avoid possible interference among these systems. Personally, I do not like these extra installations, but Anaconda does bring the benefit of installing packages with minimal efforts. So, if you hate searching around to fix Python package installation problems and errors, this could be handy for you. I really want to mention R again on this.

## Internet and DNS issues with Lubuntu and Ubuntu in Windows
Today, many take adantage of the Windows 10 Linux Subsystems (WLS) and Oracle VirtualBox to allow a Linux system to live in a Windows environment. However, some experienced the Internet issue where Ubuntu or Lubuntu has no active network connections. Quite often, this is a DNS issue. 
- In VirturlBox, I found the network will start working if we try to update the software. The update will fail of course becuase of Internet problem. But after that, the Internet will magically come back. This does not really solve the problem. But for those who just use Lubuntu occasionally, it is a very nice workaround and could save us a lot of time. 
- For WLS, it is little bit harder to fix the problem. Essentially, we need to manually change the ```nameserver``` in ```/etc/resolv.conf```. For example, add the line ```nameserver 8.8.8.8``` and ```nameserver 8.8.4.4``` to the file. Those two DNS are Google's public name servers, which work well with Ubuntu. 

## Exchange Email Server Size Limitation

Most organizations using Exchagn server impose size limitations on email storage. Periodically, we are asked to delete old emails to release some space. But emails are kinda like our digital life and keeping them permanently may serve some purposes in the future. The basic strategy is using Outlook (Express) to export older emails to a PST file and then delete them from the web-version email. 

Just one trick. By default, the Outlook only synchronizes with the server for the emails within one year (the server administrator might make this even shorter). We have to change the default setting to make Outlook synch all emails. Otherwise, emails older than one year will not be exported. Go to account setting, click on the email account and set "Mail to keep offline" to all.  
