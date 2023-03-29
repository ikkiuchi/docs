# Development Norm 开发规范

## Conceptions

1. 重构（refactoring）
    > 1. 根据设计原则和模式 / 基于重构方法进行的代码质量改进
    > 2. 其他能增进可读可维护性的改进：剪影一致、逻辑调整 …
    > 3. 基于项目约定的代码改进：Settings.services、OpenApi …

## Dev processes 开发规程

1. from the newest `msater` check out your feature branch (or check out to `dev`).
2. migration -> model -> factory & model spec ->  
   api doc -> biz error & controller -> api (request) spec
3. **RUN** your spec <==> **FIX** your code
4. write CHANGELOG, and update README if necessary
5. check `git status & git diff` then commit them
6. check out to `staging`, `git merge BRANCH` then push
7. refer to the guide for deployment (staging)
8. testing on staging
9. create a new merge request to `master`
10. deploy (master) and monitor

## Ruby style (choose what you agree)

1. [rubocop ruby style guide](https://github.com/rubocop-hq/ruby-style-guide) / [中文](https://github.com/JuanitoFatas/ruby-style-guide/blob/master/README-zhCN.md)
2. [airbnb ruby style guide](https://github.com/airbnb/ruby)
3. [代码质量规范参考](https://mubu.com/doc/gCbk7Pv_p)

## Rails practices

1. [Rails 信条](https://rubyonrails.org/doctrine/zh_cn)

TODO: model comment, permitted, error, api doc, generators

## Dev constraints 开发约束【须遵循】

1. 待办事项使用 TODO 注释、需要改进的暂时性code 使用 TODO HACK 注释。FIXME 须提 JIRA 或 ISSUE。
2. 调用外部系统服务有关配置统一放在 Settings.services 下。
...

## Git Norm

### Work flow

```markdown
feature branch -> staging (test env branch)  
      ↓[merge request]  
    master
```

### prefixes of commit message 提交信息前缀

single line message example: `git commit -m '[feat] something & [docs] update readme'`

multi-line message example: `git commit`
```markdown
[subject] summary of the main changes

1. [feat] something
2. [fixs] other thing
3. [tool] fix CI
```

1. feat: 新增服务逻辑
2. fixs: 问题修复
3. docs: 文档、注释增改
4. perm: perform，服务逻辑补全、提升、优化
5. refa: refactoring
6. test: 单元测试新增、删改、修复
7. tool: 开发、构建（CICD）、部署（Docker、Mina）等业务无关工具的改动
8. depd: dependence，add, update, remove gem
9. conf: 配置改动
10. hack: （对于所有文件）暂时解决性的回退、新增、修改

## Design principles and patterns reference
