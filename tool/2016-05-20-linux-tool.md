# Linux Tools






## Handy Tips & Commands


### "&&", "||" and ";" when chaining commands

Assume there is `command1 && command2`.

In this case `command2` will be executed if and only if `command1` returned **zero** exit status.

Similarly, `command1 || command2` can be used to run `command2` only if `command1` returned a **nonzero** exit status.

`;` is just a command separator. Thus `command2` will be executed whatever `command1` returned.



## Reference

- [Linux工具快速教程](http://linuxtools-rst.readthedocs.org/zh_CN/latest/)
