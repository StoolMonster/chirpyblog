---
title: Setup python for sublime text
date: 2024-08-09 10:56:30+0800
categories: ["Sublime Text"]
tags: ["sublime text", python] # TAG names should always be lowercase
author: <admin> 
---

Setup python environment in Sublime Text.

Select ``Tools -> Build System -> New Build System`` in sublime text. This will open a new build system config file. In that file delete everything and paste this:

```json
{
    "cmd": ["PATH TO YOUR DESIRED PYTHON INTERPRETER","-u", "$file"],
    "selector": "source.python",
    "file_regex": "^\\s*File \"(...*?)\", line ([0-9]*)"
}
```

Example path:

```json
"cmd": ["D:/MyPrograms/anaconda3/python.exe","-u", "$file"]
```

Save this file.

Select the new build system you just created in ``Tool -> Build System -> [your new system]``.

Open a python script, type ``Ctrl+B``, or ``Ctrl+shift+p``, then find ``Build with: xxx`` and press ``Enter`` to build the python script.

## References

<https://stackoverflow.com/a/64581299>

