# Pipper

<h3> What is Pipper? </h3>

Pipper is a simple Python module useful to easily install missing imported libraries <b>through pip</b> without having to do it manually.

* * * 

<h3> Features </h3>

* Works with Windows, Linux and OS X
* Automatic operating system recognition
* Automatic retrieving of pip executable's path 
* Automatic installation of pip if it is not already installed 

<h3> Usage </h3>

```python
from pipper import pip_install_module

try:
  import module_name
except:
  pip_install_module("module_name")
```

<h3> Examples of use </h3>

##### Very basic example
```python
from pipper import pip_install_module

try:
  import requests
except:
  pip_install_module("requests")
  import requests
```

##### More sophisticated example considering you have not downloaded pipper yet
```python
import sys
import urllib
import subprocess

def download(file_url,local_filename):
	web_file = urllib.urlopen(file_url)
	local_file = open(local_filename, 'w')
	local_file.write(web_file.read())
	web_file.close()
	local_file.close()

def solve_dependencies(module_name,download_url=None):
	try:
		from pipper import pip_install_module
	except:
		print "[!] pipper not found in the current directory.. Downloading pipper.."
		download("https://raw.githubusercontent.com/D35m0nd142/Pipper/master/pipper.py","pipper.py")
		from pipper import pip_install_module

	if(download_url is not None):
		print "\n[*] Downloading %s from '%s'.." %(module_name,download_url) 
		download(download_url,module_name)
		if(sys.platform[:3] == "win"): # in case you are using Windows you may need to install an additional module
			pip_install_module("win_inet_pton")
	else:
		pip_install_module(module_name)
    
try:
	import requests
except:
	solve_dependencies("requests")
	import requests
  
try:
	import socks
except:
	solve_dependencies("socks.py","https://raw.githubusercontent.com/D35m0nd142/LFISuite/master/socks.py")
	import socks
```

<h3> Dependencies </h3>

* Python <b>2.7</b>.x
* Python extra modules: urllib, subprocess

<br>
Author: <b>D35m0nd142</b><br>
Follow me: https://twitter.com/d35m0nd142
