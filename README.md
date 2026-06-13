# Ryosuke Nakamoto — AI Research & Advisory

京都大学博士（情報学）・元 日立製作所中央研究所 主任研究員・現 株式会社ELYZA Researcher による、AI研究・技術顧問・研修・PoC/プロダクト開発の案内サイト（個人事業）。

ビルド不要の静的サイト（`index.html` 1枚）。フレームワークなし・CDNフォントのみ。GitHub Pages にそのまま載せられます。

## デプロイ手順（最短）

1. GitHub で新しいリポジトリを作成（公開 / Public）。
   - 独自ドメインを使わない場合、リポジトリ名を `ユーザー名.github.io` にすると `https://ユーザー名.github.io/` で公開できます。
2. このフォルダの中身（`index.html`, `.nojekyll`, `README.md`）をリポジトリ直下に push。

   ```bash
   git init
   git add .
   git commit -m "Add site"
   git branch -M main
   git remote add origin https://github.com/ユーザー名/リポジトリ名.git
   git push -u origin main
   ```

3. リポジトリの **Settings → Pages** を開く。
   - **Source** を「Deploy from a branch」に。
   - **Branch** を `main` / `/(root)` に設定して Save。
4. 1〜2分後、表示される URL で公開されます。

## 独自ドメイン（例: nakamoto-ai.com）

1. ドメインを取得（年2,000円程度）。
2. リポジトリ直下に `CNAME` というファイルを作り、中身にドメイン名のみ記載：

   ```
   nakamoto-ai.com
   ```

3. ドメイン側の DNS で、GitHub Pages 向けの A レコード（`185.199.108.153` ほか4つ）と、`www` の CNAME（`ユーザー名.github.io`）を設定。
4. Settings → Pages の Custom domain に同じドメインを入力し、「Enforce HTTPS」を有効化。

## 編集ポイント

`index.html` 内を直接編集できます。よく変えるのは以下：

- **問い合わせ先メール**: `s0527225@gmail.com`（HTML下部の Contact と、末尾 `<script>` 内 `EMAIL` 定数の2箇所）。
- **外部リンク**: Contact セクションの `researchmap` / `GitHub` / `LinkedIn` の `href`（現在は仮の `https://researchmap.jp/` など）を、ご自身のページURLに置き換えてください。
- **料金**: Services セクションの各 `price-row` / `price-inline`。
- **論文**: Publications セクションの `pubs` リスト。

## 構成

```
.
├── index.html   # サイト本体（HTML/CSS/JSすべて内包）
├── .nojekyll    # GitHubのJekyll処理を無効化（静的配信を確実に）
└── README.md
```
