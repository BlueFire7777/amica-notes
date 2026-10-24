# amica-notes

amica（wire accessories）名刺裏面の QR コードからリンクされる「ご注意事項」ページ。

- 公開 URL: https://bluefire7777.github.io/amica-notes/
- ホスティング: GitHub Pages（main ブランチ / root）

## 注意書きの差し替え

`index.html` の次の 2 つのコメントの間だけを書き換える。

```
<!-- ===================== 注意書き ここから（差し替え範囲） ===================== -->
...
<!-- ===================== 注意書き ここまで ===================== -->
```

- 見出しごとに `<section>`、項目ごとに `<li>`（番号は自動）
- 「最終更新日」の日付を更新する
- 正式版にしたら「このページは現在準備中です」の `<p class="notice">` を削除する

push すると 1〜2 分で公開ページに反映される。URL は変わらないので、名刺の QR はそのまま使える。

## 絶対にやらないこと（名刺の QR が読めなくなる）

- このリポジトリを削除する / 名前を変える / private にする
- GitHub のユーザー名（BlueFire7777）を変える

## 独自ドメインへの引っ越し

1. 先方がドメインを取得し、DNS に `CNAME → bluefire7777.github.io` を設定
2. このリポジトリの Settings → Pages → Custom domain にドメインを入力し、Enforce HTTPS をオン
3. 旧 URL（bluefire7777.github.io/amica-notes/）は新ドメインへ自動転送されるので、印刷済みの QR はそのまま使える
4. `index.html` の `og:url` / `og:image` を新ドメインに書き換える

別のサーバーや先方の GitHub アカウントへ移す場合も、このリポジトリは削除せず、
`index.html` を新 URL への転送ページに置き換えて残すこと。
