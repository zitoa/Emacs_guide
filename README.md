# Background
Write here a 10 rows description.  
Emacs is a text-editor originally developed by.
Emacs is written in Lisp & C, 
The GNU Emacs is implemented in C, but also provides widely accessible Emacs-Lisp interfaces.
Follows a short guide on how to configure and use Emacs.

# Configuration and packages installation
When you open Emacs, it finds an initialization file. This a Lisp (*.el*) configuration file that specifies the instructions to configure and start an Emacs session. By default, Emacs will look for the following 3 files: $HOME/.emacs, $HOME/.emacs.el, $HOME/.emacs.d/init.el. 
If this file exists, Emacs will find and use it for initialization. While this is its default behaviour, you can instruct Emacs to do not load the default initialization file (--no-init-file or -q) or look into another user's directory (--user, -u USER). Type *emacs --h* from your command line to view all starting options.
This is achievied by setting *inhibit-default-init* (verify this), which tells Emacs to do not load the init.el as by default.
# Usage
.....
