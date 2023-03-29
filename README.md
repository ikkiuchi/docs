# Rubyist Documentation Ruby 开发者文档

Documentation list:

- [Development Norm 开发规范](development-norm)
- [Zero Rails Development Guide 基于 ZR 框架的开发指南](zero_rails-development-guide)

# How To

## 贡献对（Zero Rails）框架的改动

Add remote if you never do it before:

    $ git remote add my_app <TempRepoURL>

then:
```bash
git fetch my_app master # or pull
# git branch -va

git checkout my_app/master
git checkout -b my_app/BRANCH_NAME # like: fix_test_david_180808
git log --stat master # and copy the commits' hashes you want to cherry-pick
git cherry-pick [-n or --no-commit] <HASH>.. # you can also do `rebase` or `merge`

# after checked
git push my_app BRANCH_NAME # THEN create a merge request
```

cherry pick partly (only specific files):

```bash
git cherry-pick -n <HASH>..
git reset # unstage
git add -p
git commit
```

## 更新（Zero Rails）框架新发布的改动

```bash
git fetch my_app master # or pull
# git branch -va

git checkout -b BRANCH_NAME # like: zr_updating_david_180808
git merge my_app/master
```

# Common List

## Git

- `git reset --<soft/hard> HASH`
- `git stash` and `git stash apply`
- `git rm --cached FILE`
- `git cherry-pick SHA`
- `git diff [--cached] | wc -l`
- `git diff <branch>..<branch> [-- <filename>]`

## Linux

- `ps -ef | grep X`
- `tail -f -LINES FILE`

## Rails in console (pry hirb)

- `wtf?(???...)`
- https://github.com/mperham/sidekiq/wiki/API

    ```ruby
    ss = Sidekiq::ScheduledSet.new
    jobs = ss.select {|retri| retri.klass == 'SomeWorker' } # TODO
    jobs.each(&:delete)
    ```

## Docker

- `docker history`

## MySQL

## Pg
