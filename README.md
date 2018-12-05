# CrsSPY document 開発

## ドキュメント開発に必要な準備
ドキュメントとなるhtml生成にはpython製のsphinxを用いている。  
sphinx本体と使用しているhtmlテーマが必要。下記二つを`pip`などでインストールする。  
- sphinx
- sphinx_rtd_theme

## ドキュメント作成チュートリアル
### git clone
gitでソースファイルを取ってくる  
`$ git clone https://github.com/Tomoki-YAMASHITA/dev_CrySPY_doc.git`

`dev_CrySPY_doc`というディレクトリができて、その中に`Makefile`, `README.md`という二つのファイルと`source`というディレクトリがcloneされる。Makefileは編集する必要なし。基本的にはsourceの中の`conf.py`とrstファイルを編集する。

### conf.py
`conf.py`にはいろいろな設定が書いてあるが、基本的には変更しなくて良い。~~`version`と`release`のところは本当はドキュメントのバージョンを書くところなのかもしれないが、ここに書いたものがトップページに反映されて表示されるので、最終更新日を書くようにしている。よく忘れるが、ドキュメントを更新した時はここの日付を更新する。~~  
`version`と`release`にはCrySPYのバージョンを入れておく。最終更新日はフッターに自動的に表示されるようにした。

### rstファイル
rstファイルの書き方はググったら色々出てくるので調べながら書く。rstファイルの名前はウェブサイトのコンテンツの名前に対応している。

### make
ソースの編集が終わったら、`Makefile`があるディレクトリで下記コマンドを実行

```
make html
```

makeに成功すると`build`ディレクトリができる。buildディレクトリは`.gitignore`に登録してあって、git管理下には置いていない。`build/html/index.html`をブラウザで開けばページを確認できるはず。


### git push
問題なければ`git push`してレポジトリを更新。このレポジトリはドキュメントの開発用のレポジトリなので、権限が与えられている人は特に許可などいらないのでどんどんpushしてOK。



## CrySPYレポジトリのドキュメントについて
CrySPYのドキュメントはCrySPY本体のレポジトリの`CrySPY/docs/`ディレクトリに、make後の`build/html/`の中身をただコピーしている。注意点としては`.nojekyll`というドットファイルが必要なので、間違って消さないこと。本体のレポジトリはpullリクエストを受けて承認する形にしている。

