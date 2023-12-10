# Git 常用指令彙整

以下是我個人常用的 Git 指令，主要用於提升效能和簡化操作。

## 查詢 Commit Log

使用以下指令迅速查看每個 Commit 的第一行資訊：

```bash
$ git log --oneline
```

## 本地分支推送至遠端

將本地 Commit 推送至遠端的方法：

```bash
$ git push origin HEAD
```

## 回到上一個版本

使用以下指令回到上一個版本：

```bash
$ git reset --hard ORIG_HEAD
```

## 分支更新與衝突解決

為了確保新的 Master 資料進入分支，使用以下流程進行分支更新與解決衝突：

```bash
$ git fetch origin -p
$ git rebase origin/master
$ git rebase --continue
```

## 強制推送至遠端

確保資料最新後，可使用以下指令強制推送至遠端：

```bash
$ git push origin HEAD -f
```

## 查詢有衝突的檔案

```bash
$ git status
$ git ls-files -u
$ git diff
```

## 合併 Commit

若有多次測試 Commit，但不想刪除原先 Commit，可使用以下流程合併或修改 Commit：

1. 查看 Commit 版本：

```bash
$ git log --oneline
```

2. 指定要合併的 Commit 位置，搭配 ^ 指定合併到當前版本，不搭配 ^ 則合併到前一個：

```bash
$ git rebase -i dbf6195^
```

3. 顯示出要合併的版本號，使用編輯模式 ( :i ) 將 pick 改成 s 代表合併到 `dbf6185` 版本：

```bash
pick dbf6195 [Update] Update the test framework
s 5c2f971 modify test case name
s 4a5b5cb modify file name and force tags
s f15e46c modify keyword file name
s 599952d modify wait link function
```

4. 儲存後執行 `git push origin HEAD -f` 推送至遠端。

## 刪除分支

```bash
git branch -D XXX
```

> ⚠️ 在執行 Git 操作時，可能會遇到以下問題 ⚠️

### Unmerged Issue

```bash
error: path 'tests/auth/getAllOrders.test.js' is unmerged
```

解決方法：

```bash
git reset tests/auth/getAllOrders.test.js
git checkout tests/auth/getAllOrders.test.js
```

### Bad Object Issue

```bash
fatal: bad object refs/heads/QA-1234 2
```

解決方法：

```bash
git update-ref -d refs/heads/QA-1234\ 2
```

希望這份整理的指令對你有所幫助！

### [回首頁](../README.md)

#### 關於我的連結
- GitHub: https://github.com/MarkwwLiu
- Facebook: https://www.facebook.com/TestMrMark
- Linkedin: https://www.linkedin.com/in/%E7%B4%8B%E7%91%8B-%E5%8A%89-03356584/
- CakeResume: https://www.cakeresume.com/me/ak790718

##### link: https://github.com/MarkwwLiu/git_teaching/blob/main/frequently_used/frequently_used.md
