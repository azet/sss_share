## `sss_share`
shamir secret sharing & GnuPG to share secrets among parties (majority
needed to decrypt).

*example*: sensitive material is collected on a server and needs to be
shared with an outside party that only has access if a majority of the
personell allowed to view such material agrees to see it.

*example*: you want to send your diary or a secret message  to all of your 
friends in case you die (ZOMG), but no single person alone should be able
to read it. You select a group of friends (e.g. five) and send them your
secret, if more than half of them agree to decrypt they are able to read
it.

Your friends will recieve a symmetrically encrypted message wrapped in a
GPG mail and part of
the key that decrypts this message. Hence only the specified recipient
can view their share of the key that decrypts the message. Everyone gets the
same encrypted message (ciphertext) within the GPG mail. This trivial 
script builds upon [secretshare](https://github.com/sellibitze/secretshare) and
[GnuPG](https://www.gnupg.org) and can be used to retrieve the key collectively 
which then can be used to decrypt your shared, secret message with GnuPG. It's 
available as a git submodule in this repo. Just initialize and update. You'll need 
[rust](https://www.rust-lang.org) to compile.

Keep in mind that it's very improbable that this method will be useful
with recipients unfamiliar with the technology used here.

**NO WARRANTY WHATSOEVER!**

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
./share a@example.org b@example.org c@example.org <<<JFKs_true_assasin.txt
```

### LICENSE
CC0 1.0 Public Domain Dedication:
https://creativecommons.org/publicdomain/zero/1.0/
