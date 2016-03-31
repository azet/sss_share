## `sss_share`
"shamir secret sharing and GnuPG to send shares of secrets to different
parties (majority needed to decrypt)"

this trivial script builts upon [secretshare](ttps://github.com/sellibitze/secretshare). It's available as a git submodule in this repo. Just initialize and update. You'll need 
`rustc` to compile: https://rust-lang.org

### usage
pipe any file or message into stdin and specify recipients as arguments:

```
echo "share a secret among my friends" | ./share peter@noname.cc \
robin@noname.cc justin@noname.cc jaqueline@noname.cc"
```

```
./share a@example.org b@example.org c@example.org <<<secrefile
```
