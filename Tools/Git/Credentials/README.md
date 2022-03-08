# Github credentials stored

## In Github

Go to:

> `Settings -> Developer Settings -> Personal Access Tokens`

Select "[Generate new token](https://github.com/settings/tokens/new)"

Insert "Note" to fast and easy identification.

Select adequate expiration date.

On "Select scopes" select adequate authorization, but it's essential select:

- ` public_repo - Access public repositories`

Make sure to copy the new personal access token. You won’t be able to see it again!

## On one shell

Run this command to set the store for helper:

```shell
git config --global credential.helper store
```

- On home user create `.gitconfig` file:

```yaml
[user]
	name = <Your Git user>
	email = <Your Git email>
[credential]
	helper = store --file ~/.git-credentials
```

- And the file `.git-credentials`:

```
https://<your git user>:<ghp_{access token generated above}>@github.com
```

***That's all folks!!!***