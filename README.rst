##########
TerraMICRO
##########

Mission 1 of the TerraHAB Project.

For Developers
==============

How to build the documentation locally
--------------------------------------
1. Clone the repository.

.. code-block:: shell
   git clone git@github.com:TerraHAB/TerraMICRO.git
   cd TerraMICRO
   git checkout -b your-new-branch

2. Install dependencies
I highly recommend using VS Code with the reStructuredText extension, including its recommended additional extensions (such as a linter and such) -- without this extension i wouldn't be able to figure out why things aren't working
To build/preview the docs locally, a few setup steps are required:

.. code-block:: shell
   pip install sphinx sphinx_rtd_theme

you may also need to give the reStructuredText extension the absolute path to sphinx on your machine. 
``which sphinx-build`` will give you the path.

3. Get busy writing!
Start editing the ``.rst`` files within ``TerraMICRO/docs`` with whatever you want.
for help styling your text, use this awesome guide https://developer.lsst.io/restructuredtext/style.html#

4. Build the docs 
Build the docs locally by going to the docs folder and executing ``make html``