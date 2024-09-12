---
title:      "OpenLoco Object Editor"
tagline:    "Initial announcement"
author:     "Benjamin Sutas"
date:       2024-09-13 01:00:00 +1000
layout:     single
classes:    wide
categories: news
---

Hi everyone. Editing and creating objects in Locomotion/OpenLoco has always been a pain. Locotool, the previous tool used to create objects, is outdated and buggy, and there are no other alternatives. To remedy this, I've made a new program, simply titled the "Object Editor", which aims to make it simple and easy to edit any object in the game via a clean and modern UI.

Apart from being just an editor, the program also acts as a client for the "object service", an online web service I've made that stores every Locomotion game object (aka dat file) that we know about, and lets you download them. Ever had that problem of missing objects and not being able to load a scenario? That problem is now gone. You can read about it more [here](https://github.com/OpenLoco/ObjectEditor/blob/master/ObjectService/README.md), but for now all you need to do to access it is click the `Online` tab in the editor.

You can download the latest release of the object editor [here](https://github.com/OpenLoco/ObjectEditor/releases).

## Main Features

As of the writing of this blog post, the latest version of the editor is `3.2.1`. The main features currently available are:

- Editing
  - Property/hex viewer for all objects
  - Flag editing support
  - Can save object types back to `dat` file format (albeit with no encoding, though that isn't necessary)
  - Can display image table and string table of all objects (and sound data for SoundObject), and allow editing of them
  - Vehicle animation previewer
- `G1.dat` loading/viewing/exporting
- Online mode
  - Can connect to the object repository to view and download any object stored in it
  - Automatic upload of 'undiscovered' dat files (ie dat files that don't exist in the object repository)
  - View associated metadata such as tags, authors, modpacks, etc
- Editor
  - Cross-platform
  - Dark mode

 ![image](https://github.com/user-attachments/assets/80cad57e-fa53-475b-90e3-3f72f7e7b0d3)
