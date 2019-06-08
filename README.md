# GitJournal: 基於 git 的期刊出版新模式

> 本論文投稿到 《Git 開源期刊》，正在審查中！

## 論文

* HTML 版 -- https://ccckmit.github.io/GitJournal/submit/paper.html
* PDF 版 -- https://ccckmit.github.io/GitJournal/submit/paper.html

## 建置方法

安裝相關軟體

要建置論文必須安裝 pandoc 與 xeLatex (在 windows 下您可以安裝 MikTex，裏面包含 xeLatex) ，請參考下列安裝指引：

* pandoc 安裝 -- https://pandoc.org/installing.html
    * Windows : choco install pandoc
    * iMAC : brew install pandoc pandoc-citeproc
    * Linux (Ubuntu) : sudo apt-get install pandoc
* xeLatex 安裝 -- 
    * Windows : 從 http://www.texts.io/support/0002/ 點選下載後安裝
    * iMAC: 從 http://www.texts.io/support/0001/ 點選下載後安裝
    * Linux (Ubuntu) : sudo apt-get install texlive-xetex

開始建置論文

```
$ ./build paper

$ pandoc --katex --template=../template/template.html --filter pandoc-citeproc --bibliography=example.bib -H ../template/header.html -s example.md -o example.html

$ pandoc --template=../template/template.tex --filter pandoc-citeproc --bibliography=example.bib --variable papersize=a4paper -s example.md -o example.tex

$ pandoc --template=../template/template.tex --filter pandoc-citeproc --bibliography=example.bib --variable papersize=a4paper -s example.md -o example.pdf --pdf-engine=xelatex -V CJKmainfont=MingLiU
```

