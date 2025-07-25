This is a template repository for implementing further modifications in *mods.cs*.
**If you're only interested in obtaining a modified version and not actually implementing any mods, you need to move to a repository that extends this repository.**

To implement your own template simply press *Use this template* on Github and create your own repository.

Then simply add this template repository as a remote upstream to keep the docker files and tools synchronized.

Now you can use the docker image and tools inside to implement modifications using monocecile in *mods.cs*.

Here's a quick guide to the workflow and tools:

Inside of the tools folder there are 2 tools: *init.sh* and *modify.sh*.
Both have an alias defined for easier invocation:
    init
(1) Downloads the unmodified XAPK from apk pure.
(2) Creates a folder *unmodified* and populate it with 3 subfolders *bin*, *il* and *decompiled*, which contain the respective files of the games source code. These are essential for implementing new modifications. This requires that there is exactly a single ***.xapk* in the folder.
Check out *tools/init.sh* for the concrete implementation and definitions.
**Important: the docker container runs *init* by default when starting so you do not have to explicitly run this, unless you need to reobtain these resources on the run.**

    mod
or
    modify
Implements the monocecile modifications defined in *mods.cs* by replacing the current **.xapk* with the modified one.
Check out *tools/modify.sh* for the concrete implementation and definitions.

To actually implement modifications use monocecil. This allows you to manipulate the **.dll* binaries which define the games logic at runtime.




