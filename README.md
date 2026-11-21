# apt

Signed apt repository for mentaldesk packages, served at https://mentaldesk.github.io/apt.

```sh
curl -fsSL https://mentaldesk.github.io/apt/key.asc | sudo tee /etc/apt/keyrings/mentaldesk.asc >/dev/null
echo "deb [signed-by=/etc/apt/keyrings/mentaldesk.asc] https://mentaldesk.github.io/apt stable main" \
  | sudo tee /etc/apt/sources.list.d/mentaldesk.list
sudo apt update && sudo apt install tuicode
```

Every release of a package rewrites this repo from its release run, using
[a-team's `release-publish.yml`](https://github.com/mentaldesk/a-team/blob/main/.github/workflows/release-publish.yml).
Don't commit here by hand: each publish replaces the history with a single commit.
