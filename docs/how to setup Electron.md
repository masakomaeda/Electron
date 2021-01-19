## Node,npmを開発マシンにインストール（アップデート）  

 - LTS最新版Nodeをダウンロードし、インストール（アップデートも同じ方法）  
    [ダウンロード先](https://nodejs.org/ja/download/)  

 - バージョン確認方法
    ```
    node --version
    npm --version
    ```
 - インストールしたNodeに対応するnpmか念のため確認  
    （npmはパッケージマネージャで勝手にインストールされる）  
    [NODEのサイト](https://nodejs.org/en/download/releases/)

## 作業環境作成
 - 作業用フォルダを作成しコマンドプロンプトでそこまで移動しておく  
 - srcフォルダ(TypeScript置き場)、publicフォルダ(htmlやcssファイル置き場)、dist（ビルドファイル置き場）フォルダを作成する。  
 - npmの適用 (規定値で作るために-yオプションを指定する)  
   ```
   npm init -y
   ```
 - package.jsonが作成されるので必要箇所を修正する。

    ```
    "main": "src/main.js",　　←ここ

    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "start": "electron ."　←ここ
    },
    ```

## Electronoを含む必要なパッケージをインストールする  
 - readmeファイルを参照のこと


## TypeScript のコンパイル・オプション定義ファイルの作成
 - tsconfig.jsonの自動作成
   ```
   npx tsc --init
   ```
 - 一部コメントを解除したり、フォルダ名を構成通り記述する

## eslintの設定ファイルの作成
 - .eslintrc.jsonの自動作成
   ```
   npx eslint --init
   ```
 - 一部ルールを追加する(参考サイトを参照のこと)  
   注意) 参考サイトはyaml形式だか私はjsonを採用したよ

## webpack設定ファイルの作成
 - ひな形を作ってくれないので自分でファイルを作る「webpack.config.js」  

## コーディング
 - public/index.html  
 - src/main.ts  
 - src/index.tsx

## コンパイル
 - tsconfig.json の設定に従って TypeScript から JavaScript への変換が行われ、dist/main.js と dist/main.js.map が生成されます。
  ```
  # メインプロセスのコンパイル
  $ npx tsc
  ``` 
 - バンドルファイルが生成される
  ```
  # レンダープロセスのコンパイル
  $ npx webpack
  ``` 

 - electron実行してみる
  ```
  npx electron ./dist/main.js
  ```

## コンパイル（npm scriptsで）
```
 "scripts": {
    "start": "electron ./dist/main.js",
    "build:main": "tsc",
    "build:render": "webpack"
  }
```
