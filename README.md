# Source

The original bazaar repository is hosted via Launchpad.net

https://launchpad.net/py3exiv2

# Why?

The pip install of this module was failing on Ubuntu linux due to the setup being unable to find libboost_python.  Others have run into this same problem so I wanted to try to find the root cause and fix.

# Cloning the repo

Cloned from Launchpad.net locally
```
bzr branch lp:py3exiv2 py3exiv2
```

Created an empty github repository and pushed the bzr repo into it.
```
bzr push --lossy -v git@github.com:sanelson/py3exiv2.git,branch=master
```

The push command complained about losing data and would not push without the "--lossy" option.  I assume this means some tags, etc are gone.

User enaut cloned the same repo here https://github.com/enaut/py3exiv2

> It is done using git clone "bzr::lp:py3exiv2"
>
> This command requires https://github.com/felipec/git-remote-bzr to be installed

# Building

During testing I built the module by changing to the py3exiv2 directory (root level setup.py is non-functional in its current location and may just need to be removed).


```
cd py3exiv2
```

I then ran a local install of the module so as not to pollute my system python libraries while testing.

```
python3 setup.py install --prefix=~/.local
```
