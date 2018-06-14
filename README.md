# ghpush - A short expect script to simplify the "git push origin master" step

On UNIX/Linux when running the git command line:

```
git push origin master
```

you can be prompted for your github username and password.

What the `ghpush` script does is automate this by supplying the username
and password.

It gets the password from the environment variable `GHPASS`.  This must
be set before running the `ghpush` script.  One way to set the
`GHPASS` environment variable is with the `setpw.sh` which you can find here:

* [Set Windows/UNIX/Linux environment variables with a password but keep the password hidden](https://github.com/andycranston/setpw)

Here is a typical run of ghpush:

```
$ ghpush
spawn git push origin master
Username for 'https://github.com': andycranston
Password for 'https://andycranston@github.com':
Everything up-to-date
$
```

## Installing

Copy the `ghpush.exp` script to a directory in your PATH renaming
it to `ghpush` - something similar to:

```
cp ghpush.exp $HOME/bin
cd $HOME/bin
mv ghpush.exp ghpush
chmod a+x ghpush
```

---------------------------------------------
End of README
