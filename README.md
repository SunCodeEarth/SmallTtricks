# SmallTtricks
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
ArcGIS Pro comes with Python 3.x preinstalled and ArcMap still with Python 2.7. Many GIS folks have ArcMap, ArcGIS Pro installed on their computers. And they also use Python programming to automate many works. This causes a lot of trouble and headache (one reason many prefer R to Python). Some tried to use Anaconda to avoid this, but with varied success and luck. The ArcGIS Pro moved to Python 3 and it also installs  Jupyter Notebook. There are a few scenatios for GIS users.

### Stick with ArcGIS Pro Python 3
In this scenario, there is no need to install another version of Python or Anacondo to make things complx. Just stay with what ArcGIS pro installed. But to make things easier to work with, expose the ArcGIS Pro Python to the system. First, make sure you use the right Python 3 tools. If you also have ArcMap, which means Python 2.7 has been installed. Also know which version you are using. It is much more convenient to add the Python 3 into the system path, so whenever we type python on command line we will run the Python 3 version that we intended to run. 

Search "environment" and shoot "Edit the System Environment Variables", add ```C:\Program Files\ArcGIS\Pro\bin\Python\envs\arcgispro-py3``` to the System Path. If you see other versions of Python are also in the Path, remove them so the system and yourself will not be confused.

Of course, ESRI people do not want you to leave ArcGIS products and choose those powerful geospatial packages in Python such as geopandas. Therefore, we must install those packages by ourselves, which is where the frustruation comes from. But the process is no different from what we would do with a freshly installed Python 3. Just run ```python -m pip install packagename``` to install them. As we all know, Python packages are in a hell of dependency networks. Quite often, we need to compile and install some other pacakges first. If you have specific problems with a package, just Google it. 

### Visual Studio Code
For those serious progammers, Jupyter Notebook is more like a toy and learning tool, not a real production environment. Today, many choose Visual Studio Code (yes, it is a open source product from Microsoft, which many of us hate for obvious reasons years ago). 
