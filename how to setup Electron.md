## Node,npmをインストール（アップデート）  

 - LTS最新版Nodeをダウンロードし、インストール（アップデートも同じ方法）  
    [ダウンロード先](https://nodejs.org/ja/download/)  

 - バージョン確認方法
    ```
    node --version
    npm --version
    ```
 - インストールしたNodeに対応するnpmを確認  
    （npmはパッケージマネージャで勝手にインストールされる）  
    [NODEのサイト](https://nodejs.org/en/download/releases/)

## 作業環境作成
 - 作業用フォルダを作成しコマンドプロンプトでそこまで移動しておく  

 - npmの適用  
   規定値で作るために-yオプションを指定する  
   ```
   C:\Electron>npm init -y
   Wrote to C:\Electron\package.json:

   {
   "name": "Electron",
   "version": "1.0.0",
   "description": "",
   "main": "index.js",
   "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1"
   },
   "repository": {
      "type": "git",
      "url": "git+https://github.com/**********/Electron.git"
   },
   "keywords": [],
   "author": "",
   "license": "ISC",
   "bugs": {
      "url": "https://github.com/**********/Electron/issues"
   },
   "homepage": "https://github.com/**********/Electron#readme"
   }

   ```

## Electronインストール
 - コマンドプロンプトで作業用フォルダまで移動しておく  
    package.jsに記載するために-Dオプションを指定する  
    node_modulesフォルダが作られて、必要なものが全部インストールされる  
```
C:\Electron>npm i -D electron

> core-js@3.8.2 postinstall C:\Electron\node_modules\core-js
> node -e "try{require('./postinstall')}catch(e){}"

Thank you for using core-js ( https://github.com/zloirock/core-js ) for polyfilling JavaScript standard library!

The project needs your help! Please consider supporting of core-js on Open Collective or Patreon:
> https://opencollective.com/core-js
> https://www.patreon.com/zloirock

Also, the author of core-js ( https://github.com/zloirock ) is looking for a good job -)


> electron@11.2.0 postinstall C:\Electron\node_modules\electron
> node install.js

npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN Electron@1.0.0 No description

+ electron@11.2.0
added 89 packages from 99 contributors and audited 89 packages in 26.123s

6 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

```

