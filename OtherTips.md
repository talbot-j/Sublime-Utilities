# Other Helpful Tips

## Ubuntu Default File Association Issues:
On a Ubuntu installation, Sublime Text was not listed as a application option to use.
I was going to create my own sublime.desktop file, but noticed that a /usr/share/applications/sublime_text.desktop already existed.  I couldn't figure out why then it wasn't working.  I tried using the gedit.desktop file as a guide to modify the sublime version but no dice...  thanks to ["agustaf"](https://askubuntu.com/users/326686/agustaf) with his answer [here](https://askubuntu.com/questions/732464/sublime-text-not-showing-in-nautilus-open-with-menu).  A cached version exists locally and once the content of the /usr/share/applications/sublime_text.desktop was copied to the ~/.local/share/applications/sublime_text.desktop and the database updated everything worked.  I also removed the depreciated OnlyShowIn=Unity;  (thanks to running desktop-file-validate ~/.local/share/applications/sublime_text.desktop - a useful tool to insure everything I changed and moved didn't break anything).

so in short:
1. Copy the contents of /usr/share/applications/sublime_text.desktop to ~/.local/share/applications/sublime_text.desktop -> sudo cp ...
2. update the database by typing -> sudo update-desktop-database