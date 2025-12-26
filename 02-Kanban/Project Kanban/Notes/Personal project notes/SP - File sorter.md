---
"Type:": Programming project
Phase: Probing for potential
---
---
### 14/12/2025
<u>24/12/2025 - 10:53pm: Starting project</u> 

Completed the following code chunk achieving:
- Intuitive folder selection
- Identification of folders vs files in the selected directory

```python
import os

from tkinter import filedialog

"""
importing libraries, both are built in. os is for interacting with the operating system

tkinter is python's tk (originally writte in C for Tcl whatever the fuck that is) interface

that lets puthon use this toolkit originally developed for C through a translation layer
"""

#ask for directory to sort through a nice UI :)

path = filedialog.askdirectory()
print(path)

#Inspecting every item in the folder, restoring its full path, checking if that path leads to a folder

#and if leads to a folder the folder name is listed.

for item in os.listdir(path):
    f_path = os.path.join(path,item) #is this really needed?
    if os.path.isdir(f_path):
        print(item)
```

