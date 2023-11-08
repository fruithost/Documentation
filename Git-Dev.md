When you using a developing machine, please configure your clients for pull-requests with signing commits.

> nano ~/.bashrc
```!bash
export GPG_TTY=$(tty)
```

[Create an new GPG-Key](https://docs.github.com/de/authentication/managing-commit-signature-verification/generating-a-new-gpg-key) and follow the instructions:
> gpg --full-generate-key

List the keys:
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

Export the generated key with:
> gpg --armor --export AABBCCDDEEFFGGHH

And add them to [https://github.com/settings/gpg/new](https://github.com/settings/gpg/new).

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
