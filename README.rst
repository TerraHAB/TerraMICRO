.. _readme:

##########
TerraMICRO
##########

*Mission 1 of the TerraHAB Project.*

TerraMICRO is a high altitude balloon technology demonstration mission. The key
objectives of this mission are to validate the `µHAB avionics architecture
<https://github.com/RIT-Space-Exploration/uHAB>`_, experiment with core
technologies which enable long duration flights, and collect high quality
images from high altitudes.

----------------------------------

For Developers
==============

.. warning::
   The following steps are **Unix commands only.** If you are on a Windows
   machine, I recommend installing a Linux distribution from the Windows App
   Store (such as Ubuntu, which I have tested with this). Visual Studio Code
   has sophisticated tools for developing on Windows Subsystem for Linux this
   way.

How to build the documentation locally
--------------------------------------

#. **Clone this repository.**

   .. code-block:: shell

      git clone git@github.com:TerraHAB/TerraMICRO.git
      cd TerraMICRO
      git checkout -b your-new-branch


#. **Install Sphinx dependencies.**

   .. code-block:: shell

      pip install -r docs/requirements.txt

   I highly recommend using Visual Studio Code with the reStructuredText
   extension, including its recommended additional extensions (a linter and
   such)--- without this extension I wouldn't be able to figure out why things
   aren't working you may also need to give the reStructuredText extension the
   absolute path to ``sphinx-build`` on your machine. The command ``which
   sphinx-build`` will give you the path.


#. **Get busy writing!**

   Start editing the ``.rst`` files within ``TerraMICRO/docs`` with whatever
   you want. for help styling your text, use
   `this awesome guide <https://developer.lsst.io/restructuredtext/style.html#>`_
   or `this other awesome guide <https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst>`_.


#. **Build the docs.**

   .. code-block:: shell

      cd docs
      make html

   This compiles the reStructuredText (``.rst``) into HTML. View the rendered
   docs by opening ``docs/_build/html/index.html`` in your browser or using
   a VS Code extension preview window.
