# amica-notes

amica（Wire Jewelry）の「お取り扱いとご注意（Care Guide）」ページ。
Care Guide カードの QR コードからリンクされる。

- ページ本体: `care/index.html`（公開 URL の `/care/`）
- ルートの `index.html` は `/care/` への転送のみ（将来トップページを作る場合はここを差し替える）
- ホスティング: GitHub Pages（main ブランチ / root）

## 本文の差し替え

`care/index.html` の次の 2 つのコメントの間を書き換える。

```
<!-- ===================== 本文 ここから（差し替え範囲） ===================== -->
...
<!-- ===================== 本文 ここまで ===================== -->
```

- 「最終更新日」の日付も更新する
- 目次（`<ul class="toc">`）の項目と各 `<section id="...">` の id を対応させる
- イラストは `assets/illust-*.png`（線画・透過 PNG）

push すると 1〜2 分で反映される。URL は変わらないので、カードの QR はそのまま使える。

## 絶対にやらないこと（印刷済みの QR が読めなくなる）

- このリポジトリを削除する / 名前を変える / private にする
- `care/` のパスを変える
- 独自ドメインの更新を止める（自動更新をオンにしておく）

## 独自ドメインの設定

1. ドメインの DNS に GitHub Pages を設定
   - ルートドメイン（例 `example.com`）: A レコード 4 つ
     `185.199.108.153` / `185.199.109.153` / `185.199.110.153` / `185.199.111.153`
   - `www`: CNAME → `bluefire7777.github.io`
2. リポジトリの Settings → Pages → Custom domain にドメインを入力 → Enforce HTTPS をオン
3. `care/index.html` の `og:url` / `og:image` を新ドメインに書き換える
4. QR は `https://<ドメイン>/care/` で作り直す
