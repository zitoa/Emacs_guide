# Background
Write here a 10 rows description.  
Emacs is a text-editor originally developed by.
Emacs is written in Lisp & C, 
The GNU Emacs is implemented in C, but also provides widely accessible Emacs-Lisp interfaces.
Follows a short guide on how to configure and use Emacs.

# Configuration and packages installation
When you open Emacs, it finds an initialization file. This a Lisp (*.el*) configuration file that specifies the instructions to configure and start an Emacs session. By default, Emacs will look for the following 3 files: $HOME/.emacs, $HOME/.emacs.el, $HOME/.emacs.d/init.el. If one of these file exists, Emacs will use it for initialization. The idea is to assign to the current user its own initialization file. The user-name that Emacs uses is specified by the environmental variables $LOGNAME and $USER. The $HOME directory accessed by Emacs is that corresponding to the that user-name. While these are its default behaviours, you can instruct Emacs to do not load the default initialization file (--no-init-file or -q) or look into another user's directory (--user, -u USER_NAME). Type *emacs --h* from your command line to view all starting options.

As an example in this context, I uploaded a basic initialization file. It instructs to: 
1) make available the MELPA (Milkypostman’s Emacs Lisp Package Archive) archive to install Emacs packages (~4000 packages); 
2) autocomplete code by using *global-company-mode* package - here coupled to *ggtags* package to autocomplete C++ code.
3) use default variables and faces/themes.
You can extensively modify it by adding more configuration options that fit to your needs.

Type *M-x list-packages* to open the 'Emacs Packages Menu'. This lists the available Emacs packages along with version, status (mostly one of "built-in", "available", "installed") for each of them. If you want to install or disinstall a package, move the cursor on the package name and click <Enter>. You can then click on <install> or <disinstall>. Another easy way to install packages, particularly useful when multiple packages have to be installed, is to press *i* to mark for installation all packages, *u* to mark for disinstallation and *x* to download and install them. Lots of packages depends on other packages; when installing a package who has dependencies, Emacs will download and install also the uninstalled dependencies. Remember to install packages with caution, and always check if they are released from known and trusted archives. Maintainers of package archives usually sign the package by using cryptographic keys. By default, Emacs should be able to verify a package's signature when installing it, although this behaviour can be changed allowing the installation of unsigned packages. After installation, you will find the package's folder and its readme.txt under the folder elpa, which is tipically located in the same path as your initialization file. Installed packages are usually loaded and available after the Emacs session is restarted, and there is no need of additional configuration steps. However, if *--no-init-file or -q* is invoked, Emacs does not load the packages at startup. The package loading when Emacs is started can be disabled by setting the variable *package-enable-at-startup* to *nil*. Other variables who play roles in packages loading are *package-initialize* and *package-load-list*. 
  
tell some more.....3 sentences?

# Usage
Below I provide a list of the main keyboard keys used in Emacs, along with their functions.
