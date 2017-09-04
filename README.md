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
<h3> Dependencies </h3>

* Python <b>2.7</b>.x
* Python extra modules: urllib, subprocess

<br>
Author: <b>D35m0nd142</b><br>
Follow me: https://twitter.com/d35m0nd142
