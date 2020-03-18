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
