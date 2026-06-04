# 不動産ツール — Claude Code 作業指針

## サイト概要

- URL: https://fudosan-tools.com
- 静的HTMLサイト（サーバーサイド処理なし・ブラウザ完結型ツール群）
- 収益: Google AdSense（Publisher ID: ca-pub-6769343629657319）
- テーマ: 不動産売買・賃貸に特化

## 現在のツール

| ツール | パス |
|--------|------|
| 平米・坪変換 | `/tools/tsubo-calc/` |
| ㎡単価・坪単価計算 | `/tools/tanka-calc/` |
| 固定資産税・都市計画税 日割り計算 | `/tools/property-tax-calc/` |

## shared ファイル

- `shared/common.css` — 共通スタイル（navy配色: `--clr-primary: #1B5490`）
- `shared/common.js` — ヘッダー・フッター注入、`window.FudosanTools` 公開
- `shared/tool.css` — ツールページ専用スタイル

## 設計方針

- `window.ZeroTools` は使わない。必ず `window.FudosanTools` を使用
- ブランド名は「不動産ツール」（「0-TOOLs」は使用しない）
- 関連ツールリンクは3ツール内のみに限定

## SEO・品質チェック

- `<meta name="robots" content="noindex">` を入れない
- canonical URL は `https://fudosan-tools.com/...` を使用
- OG tags / JSON-LD の URL も `fudosan-tools.com` に統一
- 0-tools.com / G-S6LH1TXVP8（0-tools GA4）は使用しない

## Git 運用ルール

- **`git push` は必ずユーザーに確認してから実行する**（確認なしのプッシュ禁止）
- ブランチへのマージ・main への反映も事前に許可を得る

## セキュリティ

- `innerHTML` にユーザー入力を展開する場合は必ず `esc()` でエスケープ
- `onclick` 属性にユーザー値を直接展開しない
