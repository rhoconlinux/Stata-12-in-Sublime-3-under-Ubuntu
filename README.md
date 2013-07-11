Stata-12-in-Sublime-3-under-Ubuntu
==================================

This explains how to run do-files from Sublime 3 under Ubuntu 12.04.  It was tested with Stata 12 for Linux. 

What we need (Stata12 and Sublime3)

1) I'm assuming we have already properly installed Stata 12 (meaning running in /usr/local/stata12/), more info on how to install Stata 12 in Ubuntu at http://rhoconlinux.wordpress.com/2013/06/05/como-instalar-stata-12-en-ubuntu-linux-12-04-tambien-en-elementary-os/ -although it is in spanish you may use google translate to follow the tutorial-

2) We need Sublime 3 properly installed, see how to at <url>http://www.webupd8.org/2013/07/sublime-text-3-ubuntu-ppa-now-available.html </url>

3) we need symbolic links for xstata and stata commands, so they will be able to run at the system level. To do so, run in a terminal
<code>sudo ln -s /usr/local/stata12/xstata /usr/local/bin/xstata && sudo ln -s /usr/local/stata12/stata /usr/local/bin/stata</code>

4) You need to download and install this in order to see stata code under Sublime: https://github.com/rpowers/sublime_stata


The tweek
=========

Replace the content of <i><b>Stata.sublime-build</i></b> with

<code>
{  
	"cmd": ["xstata do $file"],
    "file_regex": "^(...*?):([0-9]*):?([0-9]*)",
	"selector": "source.stata",
	"shell": true,
}
</code>

Done! :)
