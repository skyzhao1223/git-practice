# git-practice

[![Dependencies status](https://david-dm.org/skyzhao1223/git-practice.svg?style=flat-square)](https://david-dm.org/skyzhao1223/git-practice#info=dependencies)
[![Dev Dependencies status](https://img.shields.io/david/dev/skyzhao1223/git-practice.svg?style=flat-square)](https://david-dm.org/v#info=devDependencies)
[![MIT License](https://img.shields.io/npm/l/ghooks.svg?style=flat-square)](http://opensource.org/licenses/MIT)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg?style=flat-square)](http://commitizen.github.io/cz-cli/)

一个用来熟悉 git 操作的仓库。

## 常用命令

> git --help 中罗列的常用命令

- 新建工作区

- 处理当前更改

- 检查历史和状态

- 增加、标记或微调提交历史

- 合作

## 提交规范

### 1. 内容检查 - [commitlint](https://commitlint.js.org/#/guides-local-setup?id=install-commitlint)

安装 commitlint 和 config-conventional 通用规则配置

```bash
npm install --save-dev @commitlint/{cli,config-conventional}
```

配置规则

```json
// package.json
{
  "commitlint": {
    "extends": [
      "@commitlint/config-conventional"
    ]
  },
}
```

### 2. 自动检查 - [husky](https://github.com/typicode/husky)

> 与 husky 功能相近的还有 ghooks 和 pre-commit。

安装 husky

```bash
npm install --save-dev husky
```

将 commitlint 配置到 commi-msg 钩子上

```json
// package.json
{
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }
  }
}
```

### 3. 格式化提交 - [commitizen](https://github.com/commitizen/cz-cli)

安装

```bash
# 安装 commitizen
npm install commitizen -g

# 使用 cz-conventional-changelog 初始化项目
commitizen init cz-conventional-changelog --save-dev --save-exact
```

添加执行脚本和配置项

```json
// package.json
{
  "scripts": {
    "commit": "git-cz"
  },
  "config": {
    "commitizen": {
      "path": "cz-conventional-changelog"
    }
  }
}
```

使用脚本进行提交

```bash
npm run commit
```

## 多人协作

- 分支保护

- Webhook

## 生成 Change Log

conventionalChangelog 这一步有两种选择

```bash
# 不会覆盖以前的 Change log，只会在 CHANGELOG.md 的头部加上自从上次发布以来的变动
$ conventional-changelog -p angular -i CHANGELOG.md -s -p

# 生成所有发布的 Change log
$ conventional-changelog -p angular -i CHANGELOG.md -w -r 0
```
