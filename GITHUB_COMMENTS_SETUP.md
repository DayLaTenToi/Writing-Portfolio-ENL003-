# GitHub Professor Comments Setup

This site is designed to stay free on GitHub Pages and store Professor Mode comments in:

```txt
content/professor-comments.txt
```

Saved comments use this exact format:

```txt
In "[name of essay]" at the part "[the part that he highlighted]" professor said that "[his comment]"
```

Example:

```txt
In "Essay 1 First Draft" at the part "To be honest, when I first read Maya Angelou's poetry, I didn't like it." professor said that "This opening is personal and direct."
```

## What to Configure

Open `index.html` and find:

```js
const GITHUB_COMMENTS_CONFIG = {
    owner: '',
    repo: '',
    branch: 'main',
    path: 'content/professor-comments.txt',
    token: ''
};
```

For GitHub Pages, the site can usually infer `owner` and `repo` automatically. If saving does not work, fill them in manually:

```js
owner: 'your-github-username',
repo: 'your-repository-name',
```

## The Free All-GitHub Save Method

GitHub requires a token to let a website write into a repository file.

For the quickest demo, leave `token: ''`. After Professor Nick enters the passcode `ENL003`, the site will ask for a GitHub write token the first time he saves a comment. The token stays in that browser tab only.

For the simplest short-run demo, you can paste the token directly into `token: ''`, but anyone who can inspect the page code can see it.

## Token Permissions

Create a fine-grained GitHub personal access token with access only to this repository and permission:

```txt
Contents: Read and write
```

That is enough for the site to append lines to `content/professor-comments.txt`.

Professor Mode can also delete comments. Deleting removes the matching formatted line from the same `content/professor-comments.txt` file and uses the same GitHub token permission.
