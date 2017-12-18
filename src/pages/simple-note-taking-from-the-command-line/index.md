---
title: Simple note taking from the command line
date: "2017-09-30T21:07:37.145Z"
---

This is a simple function that can be called from the command line, just like if it was a regular command. It is a quick way of taking notes and storing them in a text file.

Just add the following lines to your `~/.bashrc`:
```
# My function to take quick notes on useful commands
notes() {
    echo $1 >> $HOME/notes.md
}
```
It can be used like this:
```
$ notes "my_command -which -I -want -to remember"
```

You can read your notes like this:
```
$ more ~/notes.md
```