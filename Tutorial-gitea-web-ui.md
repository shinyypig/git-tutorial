# Gitea Web 使用教程

网站上主要的操作有发起 `Pull Request` 和 `Issue` 等，这些不做过多介绍，本文主要如何进行交叉引用。

## commit message 引用

在提交的 commit message 中写上对应 issue 的标号，比如

```
Fix #2
```

即可引用序号为 `#2` 的 issue。

<div align=center>
    <img width=30% style=margin:2% src="assets/2023-11-03-10-56-36.png">
</div>

## 在 issue 中引用 commit 或代码

复制 commit 的 SHA 粘贴到 issue 中即可：

<div align=center>
    <img width=50% style=margin:2% src="assets/2023-11-03-10-58-58.png">
</div>

<div align=center>
    <img width=50% style=margin:2% src="assets/2023-11-03-10-59-15.png">
</div>

<div align=center>
    <img width=50% style=margin:2% src="assets/2023-11-03-10-59-23.png">
</div>

引用代码，首先需要打开对应文件，点击`permalink`，然后复制`url`即可

<div align=center>
    <img width=50% style=margin:2% src="assets/2023-11-03-11-02-01.png">
</div>

<div align=center>
    <img width=50% style=margin:2% src="assets/2023-11-03-11-02-25.png">
</div>

<div align=center>
    <img width=50% style=margin:2% src="assets/2023-11-03-11-02-33.png">
</div>

引用代码特定行，首先需要打开对应文件，想要引用的行的行号，此时会出现三个点，点击`Copy Permalink`即可：

<div align=center>
    <img width=50% style=margin:2% src="assets/2023-11-03-11-03-27.png">
</div>

<div align=center>
    <img width=50% style=margin:2% src="assets/2023-11-03-11-04-31.png">
</div>

<div align=center>
    <img width=50% style=margin:2% src="assets/2023-11-03-11-04-39.png">
</div>
