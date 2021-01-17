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
 - ソース保管場所としてsrcフォルダ、実行ファイル保存場所としてdistフォルダを作成する。  
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
 - index.html  
 - main.ts  
 - index.tsx