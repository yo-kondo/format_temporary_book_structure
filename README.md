# FmtTmpBookStruct
`temp_Memo_Book`のディレクトリ構成を修正します。  
ローカルにクローンしたリポジトリの修正を行います。  

## 仕様
* ディレクトリ構成の変更（9999の数字が同一のものをまとめます）
    ```
    repository
    │  9999_本のタイトル.md
    │
    └─9999
            001.jpg
            002.jpg
            003.png
            004.png
    ```
    上記の構成を、以下の構成に変更します。
    ```
    repository
    │
    └─md
        ├─読んだ年（2016,2017など）
        │  ├─ISBN（ない場合はASIN）
        │  │      本のタイトル.md
        │  │      画像.jpg
        │  │
        │  └─ISBN
        │          本のタイトル.md
        │          画像.jpg
        │
        └─読んだ年
            └─ISBN
                    本のタイトル.md
                    画像.jpg
    ```
* 読んだ年、ISBNは本のタイトル.md内の情報を取得します。  
Markdownの中身は以下のようになっています。
    ```
    |||
    |---|---|
    |表紙       |![](001.jpg)|
    |著者       |著者名|
    |出版社      |出版社名|
    |ISBN-10   |9999999999|
    |ISBN-13   |999-9999999999|
    |発売日      |yyyy/MM/dd|
    |Amazon     |Amazonのリンク|
    |読了日      |2016/01/01|
    ```
    この中のISBN-13、読了日をディレクトリ名に使用します。  

## 設定ファイル
jsonを使用します。  
設定ファイルは実行ファイルと同じディレクトリに、config.jsonという名前で配置してください。  

記述例  
RepositoryPath : リポジトリのディレクトリパス
```json
{
  "RepositoryPath" : "C:\\repo"
}
```
