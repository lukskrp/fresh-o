# fresh-o

fresh-o is a hard fork of [Fresh](https://github.com/sinelaw/fresh), the terminal
text editor by Noam Lewis and contributors. It was taken at Fresh **v0.5.9**
(`d9c76f7b1`, tagged `v0.5.9` here too) and is developed independently.

- **Why:** Fresh is capable but not at 1.0 yet, and fresh-o needs fixes on its own
  schedule. fresh-o is the editor of [TulsiOS](https://github.com/lukskrp/TulsiOS)
  (its `EDITOR`, ADR 0031).
- **Name:** the project is fresh-o; the command stays `fresh`, so it works the same
  whether or not it's the default editor, and existing habits and scripts keep working.
- **Licence:** GPL-3.0-or-later, as Fresh. Fresh's copyright notices and history are
  kept; fresh-o's changes are under the same licence.

## What differs from Fresh

| Change | Since |
| --- | --- |
| The update check and the anonymous telemetry it sends (`check_for_updates`) and in-editor self-update (`self_update`) are **off by default**. They talk to Fresh's servers and releases, not fresh-o's. Turn them on in the config if you want them. | 0.5.9 |
| Repository and homepage metadata point here. | 0.5.9 |

Add a row for each change fresh-o makes, newest last.

## Following Fresh without depending on it

Fresh is a git remote here, nothing more:

```sh
git remote add upstream https://github.com/sinelaw/fresh   # once
git fetch upstream --tags
git log --oneline v0.5.9..upstream/master                  # what Fresh did since the fork
git cherry-pick <commit>                                   # take only what you want
```

When fresh-o has diverged too far for a commit to apply, reimplement the idea instead
of forcing the patch. Credit Fresh in the commit message either way
(`Cherry-picked from Fresh <commit>` / `Idea from Fresh <commit>`).

## Releases

Tags are `v<fresh base>-o<n>`, for example `v0.5.9-o1` for the first fresh-o
release on the 0.5.9 base. The crate version stays Fresh's base version until
fresh-o makes a release of its own numbering.
