When you using a developing machine, please configure your clients for pull-requests with signing commits.

> nano ~/.bashrc
```!bash
export GPG_TTY=$(tty)
```

> gpg --list-secret-keys --keyid-format=long
```
root@host:/# gpg --list-secret-keys --keyid-format=long
/root/.gnupg/pubring.kbx
------------------------
sec   rsa3072/AABBCCDDEEFFGGHH 2023-11-01 [SC]
      AABBCCDDEEFF000000000000
uid                 [ultimate] Firstname Lastname <your@email.tld>
ssb   rsa3072/AABBCCDDEEFF0000 2023-11-01 [E]

```

> git config --global --edit
```!ini
# This is Git's per-user configuration file.
[user]
        name = Username
        email = your@email.tld
        signingkey = AABBCCDDEEFFGGHH
[credential]
        helper = store
[commit]
        gpgsign = true
[gpg]
        program = gpg
```
