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

# Test install with Pip3

After collapsing the directory structure, the module will build just fine with pip3.  Here's how I pip installed to my local install destination directly from the git repo.

```
pip3 install --user git+git://github.com/sanelson/py3exiv2.git@fix_libboost_python_build#egg=py3exiv2
```

Output from the installation process

```
Collecting py3exiv2 from git+git://github.com/sanelson/py3exiv2.git@fix_libboost_python_build#egg=py3exiv2
  Cloning git://github.com/sanelson/py3exiv2.git (to revision fix_libboost_python_build) to /tmp/pip-install-3ft5n2gu/py3exiv2
Branch 'fix_libboost_python_build' set up to track remote branch 'fix_libboost_python_build' from 'origin'.
Switched to a new branch 'fix_libboost_python_build'
Building wheels for collected packages: py3exiv2
  Running setup.py bdist_wheel for py3exiv2 ... done
  Stored in directory: /tmp/pip-ephem-wheel-cache-ww8603z_/wheels/3a/07/68/ba3032131fbf748328b794931ce18e25c844e7a41343ccb966
Successfully built py3exiv2
Installing collected packages: py3exiv2
Successfully installed py3exiv2-0.7.1
```
