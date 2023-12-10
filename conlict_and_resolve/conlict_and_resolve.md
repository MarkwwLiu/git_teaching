# 如何製造與解決 Git 衝突流程

## 如何製造衝突？

1. 建立兩個分支 (mark_1, mark_2)
2. 切換到 `mark_2 branch` 並新增 a.txt 檔案

```bash
$ git fetch origin -p
$ git rebase origin/main
$ git add .
$ git status
$ git commit -m 'mark_2 update a.txt'
$ git push origin HEAD
```

3. 切換到 `mark_1 branch` 並再次新增 a.txt 檔案

```bash
$ git fetch origin -p
$ git rebase origin/main
$ git add .
$ git status
$ git commit -m 'mark_1 update a.txt'
$ git push origin HEAD
```

4. 在 GitHub 合併其中一個分支，將引發衝突

## 如何解決衝突？

1. 對可能引發衝突的分支進行遠端庫拉取

```bash
$ git fetch origin -p
$ git rebase origin/main
```

2. 若要放棄解決衝突，輸入以下指令即可中斷 rebase 流程

```bash
$ git rebase --abort
```

3. 若要解決衝突，修改檔案內容後執行以下指令

```bash
$ git add .
$ git status
$ git rebase --continue
```

4. 輸入資訊後回到終端機

```bash
$ git pull
```

5. 拉取臨時分支內容到自己的分支，再次修改內容

```bash
$ git add .
$ git status
$ git commit -m 'update merge'
$ git push origin HEAD
```

6. 在 GitHub 合併後，切換回 `main branch` 並拉取最新程式碼

```bash
$ git checkout main
$ git pull 
```

### 解決衝突時，若誤切換到不屬於自己的分支

執行以下指令確保衝突已解決後再繼續

```bash
$ git rebase --continue
```

### [回首頁](../README.md)

#### 關於我的連結
- GitHub: https://github.com/MarkwwLiu
- Facebook: https://www.facebook.com/TestMrMark
- Linkedin: https://www.linkedin.com/in/%E7%B4%8B%E7%91%8B-%E5%8A%89-03356584/
- CakeResume: https://www.cakeresume.com/me/ak790718

##### link: https://github.com/MarkwwLiu/git_teaching/blob/main/conlict_and_resolve/conlict_and_resolve.md
