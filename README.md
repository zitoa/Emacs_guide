# Background
GNU Emacs is the most widely used Emacs text editor, developed by Richard Stallman at MIT. It is also known as "the extensible and self-documenting text editor". GNU Emacs is written in C and Emacs Lisp (Elisp). Emacs Lisp is a Lisp-based scripting language used by Emacs for implementing most of its customizing and extension functions. GNU Emacs works on most OSs, including DOS, Windows, and the Unix-like OSs such as Linux, Solaris, macOS. On Unix-like OSs, it is part of the OS installation package. GNU Emacs runs on both GUI(s) and text terminals.

An Emacs session contains buffers. Buffers are frames partitioned from the whole Emacs screen. Emacs frames do not overlap or 'collide' each other. A buffer has its own delimited space and may operate independently from other buffers. Each buffer may contain a scroll bar, a "header line" at the top and a "mode line" at the bottom. Theoretically there is no upper limit to the number of buffers that can be opened in Emacs. A buffer can display text files, codes, images, and the output of an invoked Emacs command. Differently from buffers created by the user, buffer's names created by Emacs have usually asterisks on each end. The bottom edge of an Emacs frame contains the *status bar*, also called the "mode line", which may give information on the current state on that window. The Emacs "minibuffer" (a small frame at the bottommost area of the Emacs screen) is a special-purpose buffer used to perform operations such as editing, reading files, invoking commands etc. The minibuffer has function analogue to a dialog-box in a GUI. When it is used to store the output of Emacs commands (tipically short string of text) the "minifuffer" is called the "echo area". Buffer configuration can be extensively customized in Elisp. In programming, a commonly adopted interface includes a frame to display the source code, flanked by another to display either output, debugger, or documentation pages.

# Configuration and packages installation
When you launch Emacs, it finds an initialization file (init file). The init file is a Lisp (*.el*) configuration file that specifies the instructions for configuring and starting Emacs. By default, Emacs will look for the following 3 files: $HOME/.emacs, $HOME/.emacs.el, $HOME/.emacs.d/init.el. If one of these file exists, Emacs will use it for initialization. The idea is to assign to the current user its own initialization file. The user-name that Emacs uses is specified by the environmental variables $LOGNAME and $USER. The $HOME directory accessed by Emacs is that corresponding to that user-name. You can instruct Emacs to do not load the init file (as default), by setting *--no-init-file* or *-q*. You can also instruct Emacs to look into another user's directory, by setting *--user USER_NAME*.  
Type *emacs --h* from your command line to view all starting options.  

As example, I uploaded a very basic init file. It instructs to: 
1) use the MELPA (Milkypostman’s Emacs Lisp Package Archive) archive to install packages (~4000 packages)  
2) use *global-company-mode* package - here coupled to *ggtags* package to autocomplete C++/python/R code  
3) use default variables and faces/themes.  

Type *M-x list-packages* to open the 'Emacs Packages Menu', which lists the available packages along with version and status (one of "built-in", "available", "installed"). If you want to install or uninstall a package, move the cursor on the package's name and click 'Enter'. You can then click on 'install' or 'disinstall'. To install/uninstall multiple packages, press *i/u* on all packages you want to install/unistall; for downloading and installation, then press *x*. Many packages have dependencies; Emacs will download and install the uninstalled dependencies when required. Be careful when installing packages - always check they are released from known and trusted archives. Maintainers of package archives usually sign the package by using cryptographic keys. By default, Emacs should be able to verify a package's signature. However, you can also install unsigned packages if you trust the source. After installation, you will find the package's folder and its README under the folder 'elpa', tipically located under the same path as your init file. Installed packages are loaded and available after the Emacs session is restarted, with no need of additional configuration steps. However, if *--no-init-file* or *-q* is invoked, Emacs does not load the packages at startup. Package loading at startup can be disabled by setting the variable *package-enable-at-startup* to *nil*. Other variables with roles in loading packages are *package-initialize* (instructs to load specific packages needed for the processing of the init file; this sets *package-enable-at-startup* to nil), and *package-load-list* (instructs to load only specified version of packages while ignoring all other versions if present).

# Usage
Emacs is well known as the 'keyboard-based' text editor. Learning Emacs can be boring and painful at beginning, but I think efforts will be paid back - working with Emacs improves performance and efficiency. Commands in Emacs are controlled by the 'Ctrl' and the 'META' keys. In Microsoft and Linux, by default, the 'Alt' key is the 'META' key. On MacOS, it's either ⌥ option or ⌘ command, depending on the Emacs distribution. The 'Esc' key can also be used to invoke the 'META' key. Whilst the 'Ctrl' is often (but now always) held down while putting another character, the 'META' key does not need to be held down. When talking about Emacs commands, C- refers to 'Ctrl', M- to 'META', and ESC to the 'Esc' key. Thus:
  
1) C-'chr' means hold down the 'Ctrl' key while typing 'chr' (e.g: C-s: hold down the 'Ctrl' key and type s).
2) C-'chr_1' 'chr_2' means hold down the 'Ctrl' key while typing 'chr_1'; release 'Ctrl' and type 'chr_2'.
3) M-'chr' means hold down the 'META' key while typing 'chr' (e.g: M-x: hold down the 'META' key and type x).

Below, I list the most used Emacs commands:

- C-x C-f &emsp; find, open, or create a file  
- C-x C-s &emsp; save file  
- C-x o   &emsp; move cursor to another open buffer;
- C-x C-d &emsp; list directory  
- C-x d &emsp; start DirEd (Directory Editor)  
- C-x b &emsp; switch buffer  
- C-x C-b &emsp; show buffers list  
- C-x k &emsp; kill buffer  
- C-z &emsp; suspend buffer  
- C-x C-c &emsp; close Emacs session  
- C-x C-w &emsp; write all content in the current buffer to another file  
- C-x C-v &emsp; find another file and open it  
- C-x i &emsp; insert content of another file at cursor position  
- C-u 'char' &emsp; repeat 'char' 4 times at the cursor position  
- C-g &emsp; quit the the previously typed Emacs command  
- C-x u &emsp; undo previous action  
- C-d &emsp; delete a char  
- M-d &emsp; delete word  
- C-k &emsp; delete entire line  
- M-w &emsp; copy selected region  
- C-y &emsp; paste selected region  
- C-a &emsp; move cursor to the beginning of line  
- C-e &emsp; move cursor to the beginning of line  
- C-f &emsp; forward char
- C-b &emsp; backward char
- C-p &emsp; previous line
- C-n &emsp; next line
- C-v &emsp; one page up
- M-v &emsp; scroll down one page  
- C-k &emsp; delete the marked strings or rest of line
- M-w &emsp; delete the marked region
- C-t &emsp; transpose two consecutive chars (after placing the cursor on the second char)  
- M-t &emsp; transpose the two words (after placing the cursor in the middle of the two words)  
- C-x C-t &emsp; transpose two lines (after placing the cursor on the second line)  
- M-u &emsp; make all chars in a word uppercase (after placing the cursor at beginning of the word)  
- M-l &emsp; make all chars in a word lowercase (after placing the cursor at beginning of the word)  
- M-x &emsp; center-region / center-line / center-paragraph / indent-region (useful for programming)   
  
#### Windows management and session customization  
- C-x 0 &emsp; delete only window hosting the cursor  
- C-x 1 &emsp; keep only the window hosting the cursor while close all others  
- C-x 2 &emsp; split window orizzontally  
- C-x 3 &emsp; split window vertically  
- C-x o &emsp; move cursor to another window (if this exists)  
- C-x 4 f &emsp; find and open file in other window  
- C-x 5 f &emsp; find and open file in other Emacs frame  
- C-x 5 o &emsp; move cursor to another Emacs frame (if this exists)  
- M-x 'speedbar' &emsp; open a separate window that list all user's directories  
- M-x 'shell' &emsp; start shell terminal below in a separate buffer  
- M-x 'customize-themes' &emsp; list available for session customization  

#### Emacs help  
- C-h t &emsp; open a window with the Emacs tutorial  
- C-h i &emsp; open a windom with the Info Directory  
- C-h k &emsp; provide description of the command invoked  
- C-h l &emsp; list the last command typed  
- C-h v &emsp; show Emacs variable value and description  
- M-x 'doctor' &emsp; open your Emacs psychotherapist


