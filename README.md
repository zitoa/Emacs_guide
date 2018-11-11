# Background
GNU Emacs is the most used Emacs text-editor, conceived and developed by Richard Stallman at MIT. It is also known as GNUMACS and as "the extensible and self-documenting text editor". Its extensibility and flexibility make GNU Emacs a very powerful text-editor. GNU Emacs is written in C and Emacs Lisp (Elisp). Emacs Lisp is a Lisp-based scripting language used by Emacs for implementing most of its customizing and extension functions. GNU Emacs is implemented on most OS(s), including DOS, Windows, and the Unix-like OS such as Linux, Solaris, macOS. On Unix-like OS(s), it is part of the OS installation package. GNU Emacs runs on both GUI(s) and text terminals.

An Emacs session is conducted in a buffer. Buffers are tiled frames partitioned from the whole Emacs screen. Emacs frames are tiled and do not overlap or 'collide' with other open frames. A buffer has its own delimited space and operates independently from other buffers. Each buffer contains a scroll bar, a "header line" at the top and a "mode line" at the bottom. Many buffers can be opened, and theoretically there is no upper limit to the number of buffers that can be opened in Emacs. A buffer can display text files, codes, image files, and also the output of an invoked Emacs command. Importantly, names of buffers created by Emacs usually have asterisks on each end. This allows to  distinguish these buffers from user's created buffers. The bottom edge of an Emacs frame contains the *status bar*, also called the "mode line", which may give information on the current state on that window. The bottommost area is the "minibuffer", used to perform operation associated with an Emacs command (e.g text to target in a isearch or commands below). The minibuffer has analogue function to a dialog-box in a GUI. When it is used to store the output of Emacs commands (tipically short string of text, although the lenght of allowed text is customizable), the "minifuffer" is called the "echo area". Buffer configuration can be extensively customized in Elisp. In programming, a commonly adopted interface includes a frame to display the source code with another to display the output of code, and may be another displaying a debugger or a code documentation page.

Add only 2-3 sentences on major mode, minor mode, batch mode.

# Configuration and packages installation
When you open Emacs, it finds an initialization file. This a Lisp (*.el*) configuration file that specifies the instructions to configure and start an Emacs session. By default, Emacs will look for the following 3 files: $HOME/.emacs, $HOME/.emacs.el, $HOME/.emacs.d/init.el. If one of these file exists, Emacs will use it for initialization. The idea is to assign to the current user its own initialization file. The user-name that Emacs uses is specified by the environmental variables $LOGNAME and $USER. The $HOME directory accessed by Emacs is that corresponding to the that user-name. While these are its default behaviours, you can instruct Emacs to do not load the default initialization file (--no-init-file or -q) or look into another user's directory (--user, -u USER_NAME). Type *emacs --h* from your command line to view all starting options.

As an example in this context, I uploaded a basic initialization file. It instructs to: 
1) make available the MELPA (Milkypostman’s Emacs Lisp Package Archive) archive to install Emacs packages (~4000 packages); 
2) autocomplete code by using *global-company-mode* package - here coupled to *ggtags* package to autocomplete C++ code.
3) use default variables and faces/themes.
You can extensively modify it by adding more configuration options that fit to your needs.

Type *M-x list-packages* to open the 'Emacs Packages Menu'. This lists the available Emacs packages along with version, status (mostly one of "built-in", "available", "installed") for each of them. If you want to install or disinstall a package, move the cursor on the package name and click <Enter>. You can then click on <install> or <disinstall>. Another easy way to install packages, particularly useful when multiple packages have to be installed, is to press *i* to mark for installation all packages, *u* to mark for disinstallation and *x* to download and install them. Lots of packages depends on other packages; when installing a package who has dependencies, Emacs will download and install also the uninstalled dependencies. Remember to install packages with caution, and always check if they are released from known and trusted archives. Maintainers of package archives usually sign the package by using cryptographic keys. By default, Emacs should be able to verify a package's signature when installing it, although this behaviour can be changed allowing the installation of unsigned packages. After installation, you will find the package's folder and its readme.txt under the folder elpa, which is tipically located in the same path as your initialization file. Installed packages are usually loaded and available after the Emacs session is restarted, and there is no need of additional configuration steps. However, if *--no-init-file or -q* is invoked, Emacs does not load the packages at startup. The package loading at startup can be disabled by setting the variable *package-enable-at-startup* to *nil*. Other variables who play roles in packages loading are *package-initialize* who explicitly tells Emacs to load specific packages (needed for the processing of the initialization file; note that this will set *package-enable-at-startup* to nil), and *package-load-list* who tells Emacs to load only that version of the specified package while ignoring all other versions if present. 

# Usage
Emacs is well known as the "keyboard-based" text editor. Although learning Emacs can be boring and painful at beginning, I think it is really worth, and efforts will be well paid back. Working with Emacs improves performance and efficiency. Commands in Emacs are controlled by the 'Ctrl' and the 'META' keys. GNU Emacs for Microsoft and Linux by default make the 'Alt' key do be the 'META' key. On the Mac OS X, it's either ⌥ option or ⌘ command, depending on the emacs distribution. The 'Esc' key can also be used to invoke the 'META' key. Whilst the 'Ctrl' is often (but now always) held down while putting another character, the 'META' key does not need to be held down. When talking about Emacs commands, C- refers to 'Ctrl', M- to 'META', and ESC to the 'Esc' key. Thus:
  
1) C-'chr' means hold down the 'Ctrl' key while typing the character 'chr' (e.g: C-s: hold down the 'Ctrl' key and type s).
2) M-'chr' means hold down the 'META' key while typing the character 'chr' (e.g: M-x: hold down the 'META' key and type x).

Below, I list the most used Emacs commands:

C-x C-f   find file, open a given file or create a file  
C-x C-s   save file  
C-x o     move cursor" to another open buffer  
C-x C-d   list directory  
C-x d     start DirEd (Directory Editor)  
C-x b     switch buffer  
C-x C-b   show buffers list  
C-x k     kill buffer  
C-z       suspend buffer  
C-x C-c   close Emacs session  
C-x C-w   write all content in the current buffer to another file  
C-x C-v   find another file and open it  
C-x i     insert content of another file at cursor position  
C-u 'char'  repeat <char> 4 times at the cursor position  
C-g       quit the the previously typed Emacs command  
C-x u     undo previous action  
C-d       delete a char  
M-d       delete word  
C-k       delete entire line  
M-w       copy selected region  
C-y       paste selected region  
C-a       move cursor to the beginning of line  
C-e       move cursor to the beginning of line  
M-v       scroll down one page  
