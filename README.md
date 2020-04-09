# git-practice

[![Dependencies status](https://david-dm.org/skyzhao1223/git-practice.svg?style=flat-square)](https://david-dm.org/skyzhao1223/git-practice#info=dependencies)
[![Dev Dependencies status](https://img.shields.io/david/dev/skyzhao1223/git-practice.svg?style=flat-square)](https://david-dm.org/v#info=devDependencies)
[![MIT License](https://img.shields.io/npm/l/ghooks.svg?style=flat-square)](http://opensource.org/licenses/MIT)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg?style=flat-square)](http://commitizen.github.io/cz-cli/)

一个用来熟悉 git 操作的仓库。

## 常用命令

### 新建工作区

### 处理当前更改

### 检查历史和状态

### 增加、标记或微调提交历史

### 合作

## 生成 Change Log

conventionalChangelog 这一步有两种选择

```bash
# 不会覆盖以前的 Change log，只会在 CHANGELOG.md 的头部加上自从上次发布以来的变动
$ conventional-changelog -p angular -i CHANGELOG.md -s -p

# 生成所有发布的 Change log
$ conventional-changelog -p angular -i CHANGELOG.md -w -r 0
```
