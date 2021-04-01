#### Remove last commit from remote repo:
```
git reset HEAD^
git push origin +HEAD
```

#### Git config
```
git config --global --edit
```

#### Signing commits without exposing email
https://docs.github.com/en/github/authenticating-to-github/managing-commit-signature-verification <br />
1. Use `git log` to find your username and email
2. Generate GPG key (4096 bits) with your username and email using `gpg --full-generate-key`
3. Get the GPG key using `gpg --armor --export <key_id>` and paste it here: https://github.com/settings/keys
4. Tell Git about user info using `git config --global user.signingkey <key_id>`, `git config --global user.email <email>` and `git config --global user.name <username>`
5. `git commit -S -m <msg>` <br />
Some userful GPG commands: \
```
gpg --full-generate-key
gpg --list-secret-keys --keyid-format LONG  # Find key_id
gpg --armor --export <key_id>
gpg --list-keys
gpg --delete-secret-key <key_id>
gpg --delete-key <key_id>
```