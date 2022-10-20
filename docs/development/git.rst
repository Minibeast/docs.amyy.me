Git
====
.. image:: /_static/img/git.png
    :alt: git - the stupid content tracker

Setting up Git remote repository on Linux
------------------------------------------
Making a Git remote repository is self-explanatory, although 
one issue I did encounter was related to how Git reacts when 
trying to switch branches to the one you're actually on.

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

Once the local changes are pushed, the remote repository is not 
completely set up yet. It expects the default branch to be 
called ``master``, and if it's anything different it won't be 
happy. Normally, this wouldn't be an issue, just checkout the 
other branch (which will be there assuming it worked). However, 
attempting to do so throws ``fatal: this operation must be run 
in a work tree``. To fix this, run the checkout command with 
the flag ``--work-tree=<path-to-project>``.
