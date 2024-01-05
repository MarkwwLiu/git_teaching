# 解決 Git 中文亂碼的方法

在 Git 和終端機中，如果遇到中文亂碼的問題，可以按照以下步驟進行設定：

## Git 中文亂碼解決方法

```bash
$ git config --global i18n.commitencoding utf-8
$ git config --global i18n.logoutputencoding utf-8
$ export LESSCHARSET=utf-8
```

## 終端機中文亂碼解決方法

在環境變數中加入以下設定：

```bash
$ export LC_ALL=en_US.UTF-8
$ export LANG=en_US.UTF-8
```

這樣設定後，應該能夠解決 Git 和終端機顯示中文亂碼的問題。確保在使用 Git 和終端機時，字符編碼都設定為 UTF-8，有助於正確顯示中文字符。

### [回首頁](../README.md)

#### 關於我的連結
- GitHub: https://github.com/MarkwwLiu
- Linkedin: https://www.linkedin.com/in/%E7%B4%8B%E7%91%8B-%E5%8A%89-03356584/
- CakeResume: https://www.cakeresume.com/me/ak790718

##### link: https://github.com/MarkwwLiu/git_teaching/blob/main/git_chinese/git_chinese.md
