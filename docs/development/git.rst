Git
====
.. image:: /_static/img/git.png
    :alt: git - the stupid content tracker

Setting up Git remote repository on Linux
------------------------------------------
An important thing to note when setting up a "local" remote 
repository is that a remote repository is different from a 
local repository. A repository, while technically can work as 
both a working copy and the origin, does not work very... 
intended. To get it working, I created a blank repository to 
act as the origin, then made another folder (in ``/var/www``) 
that cloned the folder (yes, Git will let you set an origin 
to a path on the system directly).

On the server, create a folder for the repository. Then create 
a ``.git`` folder. Then, in that folder, run ``git init --bare``. 
After this, on the local repository, add the origin using SSH 
syntax: ``<username>@<hostname>:<path-to-project>``. You will 
need an SSH key set up for the user on the server, the same key 
used in GitHub will work fine, including the 
`same setup process <https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent>`_ 
(obviously, instead of copying the public key into GitHub, just 
add it to the ``.ssh/authorized_keys`` file). Important note: 
The "path to project" is the folder above the ``.git`` folder 
created earlier.

UPDATE: This probably isn't needed in actuality, the repository 
can probably just exist without a ``.git`` folder. Keeping this 
listed as it's the current set up for the Docs repository.
