## `sss_share`
shamir secret sharing & GnuPG to share secrets among parties (majority
needed to decrypt).

example: sensitive material is collected on a server and needs to be
shared with an outside party that only has access if a majority of the
personell allowed to view such material agrees to view it.

example: you want to send your diary or a secret message  to all of your 
friends in case you die (ZOMG), but not a single person should be able
to read it. You select a group of friends (e.g. five) and send them your
secret, if more than half of them agree to decrypt they are able to read
it.

Your friends will recieve a symmetrically encrypted secret and part of
the key that decrypts this secret in a GPG mail. This trivial script builts upon [secretshare](https://github.com/sellibitze/secretshare) and GnuPG
and can be used to retrieve the key which decrypts the shared message
with GnuPG. It's available as a git submodule in this repo. Just
initialize and update. You'll need [rust](https://www.rust-lang.org) to
compile.

**NO WARRANTY WHATSOEVER! :)** 

..It's also unlikely that this project will
be maintained much. It's a (very) quick hack that didn't fit on a
GitHub gist.

### usage
pipe any file or message to `stdin` and specify the recipients as arguments:

```
echo "share a secret among my friends" | ./share peter@noname.cc \
robin@noname.cc justin@noname.cc jaqueline@noname.cc"
```

```
./share a@example.org b@example.org c@example.org <<<JFKs_true_assasin
```

### LICENSE
CC0 1.0 Public Domain Dedication:
https://creativecommons.org/publicdomain/zero/1.0/
