---
layout: page
title: Emacs
permalink: /emacs/
---

# Zolomon's Page of Useful Emacs Tricks

0.  `C-q C-j` to insert a newline, can be used in `M-x eval-expression`, [look here for an example](http://emacs.stackexchange.com/a/16624/8629).
1. Bookmarks `C-x r l` to list, `C-x r m` to make a new bookmark and `C-x r b` to jump to a bookmark. Both files and directories can be bookmarked.
2. [Neotree](https://github.com/jaypei/emacs-neotree), a tree directory visualizer
3. [Projectile](https://github.com/bbatsov/projectile), working with files in projects
4. [Popwin](https://github.com/m2ym/popwin-el), use popups instead of buffers
5. [switch-window](https://github.com/dimitri/switch-window), choose buffers by number
6. [Hyde](https://github.com/nibrahim/Hyde), working with Jekyll
7. [Auto-fill-mode][auto-fill-mode]: Automatically insert whitespace at `(fill-column)` set by `C-x f`.
8. Rename files with `rename-file`.
9. [Occur][occur]: to search for lines in a buffer matching a regexp.
10. [web-mode][web-mode]: to work with web related stuff. `C-c C-f` to fold tags.

### Copy the whole buffer
<script src="https://gist.github.com/61ef174234d41276a7cb.js?file=copy-buffer.el" type="text/javascript"></script>

[auto-fill-mode]: http://www.emacswiki.org/emacs/AutoFillMode
[occur]: http://emacswiki.org/emacs/OccurMode
[web-mode]: http://web-mode.org/

### Wrapping text according to `fill-column`

If you have text that you would like to be formatted, use `M-q` which by default is bound to `fill-paragraph`.
