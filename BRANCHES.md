# Testing and upstream changes

The source repository is the fork at https://github.com/Nadhila-dot/docs.

- `codex/testing`: personal testing and GitHub Pages preview configuration. No CtrlPanel custom domain file is included.
- `codex/ctrlpanel-pr`: changes intended for pull requests to `Ctrlpanel-gg/docs:main`. Keep `public/CNAME` set to `ctrlpanel.gg` and retain the upstream deployment workflow.

The separate https://github.com/Nadhila-dot/Nadhila-dot.github.io repository hosts the preview at https://nadhila-dot.github.io/. Its `main` branch mirrors the testing branch and builds, tests, and deploys through GitHub Actions.

To publish committed testing changes from this checkout:

```sh
git switch codex/testing
git push fork codex/testing
git push pages codex/testing:main
```

These commands upload source; builds run on GitHub, not on this machine.

Move reviewed application/content commits to `codex/ctrlpanel-pr` with cherry-pick. Do not merge the testing branch wholesale: its domain removal, Pages workflow, and this branch guide are personal preview configuration. Push the PR branch to the fork, then open a pull request against `Ctrlpanel-gg/docs:main`.

Remote names: `origin` is CtrlPanel upstream, `fork` is the personal source fork, and `pages` is the personal Pages hosting repository. Keep local branches tracking the fork; do not push directly to upstream.
