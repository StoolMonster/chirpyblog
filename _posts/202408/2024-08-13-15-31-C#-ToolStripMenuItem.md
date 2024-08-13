---
title: ToolStripMenuItem usage
date: 2024-08-13 15:31:30+0800
categories: [".NET"]
tags: [".net", "ToolStripMenuItem"]
author: <admin> 
---

`ToolStripMenuItem` can be reused across different context menus, toolbars, or menus in your application.

**Important Considerations**:
1. State Synchronization: If the ToolStripMenuItem has state-dependent properties (like Checked or Enabled), changes in one menu will be reflected in all instances where that item is used.
1. Parent-Child Relationship: A ToolStripMenuItem can only have one parent. When you add it to a new menu, <span style="color:red">it is removed from its previous parent</span>.

So, if you want to reused a `ToolStripMenuItem`, it better to add it in the `contextMenuStrip.Opening`.
