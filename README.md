# tkgeometry

Before the compilation:
  Be sure to have a working version of root active: this means that you have root and root-config in your path.
  If you are on lxplus, or on any other comuter with afs mounted you can obtain this by executing
  # source /afs/cern.ch/sw/lcg/app/releases/ROOT/5.26.00/x86_64-slc5-gcc34-opt/root/bin/thisroot.sh
  or
  # source /afs/cern.ch/sw/lcg/app/releases/ROOT/5.26.00/x86_64-slc5-gcc34-opt/root/bin/thisroot.csh
  depending on the shell you are using. Also you probably want to put this line in your .bashrc or .tcshrc,
  as it will be needed in order to execute the program afterwards

Compilation
  Simply type:
  # make
  This will build the needed programs and put them in the ./bin directory. A few libraries are required:
  * boost_filesystem
  * boost_regex
  * the root library set

Install
  If the make command runs properly you can install the program with the script
  ./install.sh
  =========If this is the first time that you install the tkgeometry===========
     A few questions will be asked:
     1) You will need to provide the destination directory for the www output of the program (proabably
  something like /afs/cern.ch/user/y/yourname/www/layouts) this directory needs to be writable by you
  and readable by the web server.
     The style files will be copied during the installation to that directory (for example
  /afs/cern.ch/user/y/yourname/www/layouts/style ). If the style files get changed during the development
  a new ./install.sh will be needed to get this propagated to the output.
     Alternatively, you can choose to make a symbolic link between the source directory style directory and
  the layout directory. This avoids the need of repeating the ./install.sh at every update of the style files
  but in order to do this the source directory should also be within the reach of the web server.
     2) The target XML directory is also required (this typically is the source_tkgeometry/xml). The program
  requires some files to be in that directory in order to work properly.
     3) The set of momentum values to be used for the simulation
  =============================================================================

Update
  To get the latest development version (usually UNSTABLE) you simply type
  # svn up
  # make
  # ./install.sh

