# Copy Environment When Switching User

In CLI switching to a user can be done with this command:

```bash
sudo su otheruser
```

By adding a `-` after su it will start the shell as a login shell and will have the user environment set up.

```bash
sudo su - otheruser
```

---------

**Refs**

1. From [man su](https://man7.org/linux/man-pages/man1/su.1.html)

```
-, -l, --login
  Start the shell as a login shell with an environment similar to a real login:
    - clears all the environment variables except TERM and variables specified by --whitelist-environment
    - initializes the environment variables HOME, SHELL, USER, LOGNAME, and PATH
    - changes to the target user's home directory
    - sets argv[0] of the shell to '-' in order to make the shell a login shell
```
