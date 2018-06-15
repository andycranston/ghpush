# ghpush - A short expect script to simplify the "git push origin master" step

On UNIX/Linux when running the git command line:

```
git push origin master
```

you can be prompted for your github username and password.

What the `ghpush` expect script does is automate this by supplying the github
username and github password.

The github username is extracted from the $HOME/.gitconfig file.
In particular it looks for the line:

```
name = githubusername
```

in the `[user]` stanza.

The github password is read from the `GHPASS` environment variable.
This must be set before running the `ghpush` script.  One way to set
the `GHPASS` environment variable is with the `setpw.sh` which you can
find here:

* [Set Windows/UNIX/Linux environment variables with a password but keep the password hidden](https://github.com/andycranston/setpw)

Here is a typical run of the `ghpush` expect script:

```
$ ghpush
spawn git push origin master
Username for 'https://github.com': andycranston
Password for 'https://andycranston@github.com':
Everything up-to-date
$
```

## Pre-requisites

Tcl and expect must be installed.

The file:

```
/usr/local/bin/expect
```

must be the expect executable or be a link to the expect executable.

I developed the `ghpush` expect script using:

* Tcl version 8.6.6
* expect version 5.45.3

running on Lubuntu.

## Installing

Copy the `ghpush.exp` script to a directory in your PATH renaming
it to `ghpush` - something similar to:

```
cp ghpush.exp $HOME/bin
cd $HOME/bin
mv ghpush.exp ghpush
chmod a+x ghpush
```

## Running

Whenever you would type:

```
git push origin master
```

instead just type:

```
ghpush
```

Easy :-]

## Just cache your credentials?

Yes there are many other ways to supply the usernamne and password
including having the credentials cached or stored using various encryption
methods.

The `ghpush` expect script is just a different approach.

One advantage of the `ghpush` expect script `is that the github password
is only stored in the GHPASS environment variable for the duration of
that login session.  As long as you keep the session secure (i.e. do
not leave your workstation unattended) then your password is safe.

---------------------------------------------
End of README
