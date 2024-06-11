# Rush issue repro

Issue reproduction repo for microsoft/rushstack#4777

## Steps

*I've done each of these in a separate commit, so you can look at the commit history and GitHub Actions logs as well.*

1. **`rush init`**
2. **run `rush update` to create scripts** &mdash; *The `common/scripts` directory is not included in `rush init`.*
3. **add a project so `rush install` works properly** &mdash; *`rush install` will complain if there's no dependencies & thus no shrinkwrap.*
4. **add a workflow that uses `rush install`**
5. **upgrade `rushVersion` to 5.125.1** &mdash; *✅ This is the last working version.*
6. **upgrade `rushVersion` to 5.126.0** &mdash; ***❌ CI fails on this one for unclear reasons.***
