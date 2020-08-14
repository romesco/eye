Home
===============================
.. toctree::
   :hidden:

   quickstart
   hardware/index
   ros_configuration/index
   algorithms/index
   faqs
   license

Contributing
^^^^^^^^^^^^^
1. Pull the repo:
::
    git clone https://github.com/romesc-CMU/eye.git

2. For rendering locally while editing:
::
    pip install -U sphinx
    pip install -U sphinx-autobuild
    # now in a background terminal window (or tmux pane), do:
    cd eye/
    sphinx-autobuild docs _build/html -b html -p 8009

3. Browse to:
::
    http://localhost:8009
        

4. Make some edits. The changes will autobuild:
::
    vim docs/algorithms/ssd.rst

5. Push those edits back:
::
    git add .
    git commit -m '<something witty>'
    git push origin master

6. Check out the instant online update at:
::
    https://o_eye.rtfd.io

**Also:**
`Very helpful link to read about formatting of .rst files <https://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html#inserting-code-and-literal-blocks>`_

Primary Contributors:
^^^^^^^^^^^^^^^^^^^^^^

** Ramon (Yiren) Qu **
** Adit Jha **

