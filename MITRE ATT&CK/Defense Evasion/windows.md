## ファイル削除
```powershell
del <ファイル名>
Remove-Item <ファイル名>
```

## フォルダ削除
```powershell
rd /s /q <フォルダ名> # サブフォルダ含め(s)、確認メッセージ非表示(q)
Remove-Item <フォルダ名> -Recurse -Force # サブフォルダ、隠しファイルなども含める
```
