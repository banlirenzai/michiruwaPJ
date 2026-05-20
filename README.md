# 記録ソフト UX モックアップ

児童発達支援・放課後等デイサービス向け 記録ソフトの UX 可視化用 静的モックアップです。

クライアント（ミチルワグループ FC本部 情報システム部）への提案書ドラフトに対応する5画面を、HTML + CSS のみで構築しています。

---

## 起動方法

ビルド・依存パッケージは不要です。以下のいずれかで開いてください。

```bash
# Mac
open michiruwa/mockups/index.html

# 任意のブラウザで index.html を直接開く
```

エントリポイントは [`mockups/index.html`](mockups/index.html) です。4画面へのリンクが並んでいます。

---

## 画面一覧

| # | 画面 | ファイル | 主な要件ID |
|---|---|---|---|
| 01 | 管理者ダッシュボード | [`mockups/01_dashboard.html`](mockups/01_dashboard.html) | D-08 / P-10 / P-11 / D-07 / FT-10 |
| 02 | 児童詳細・同一画面集約 | [`mockups/02_child_detail.html`](mockups/02_child_detail.html) | UI-03 / A-01 / P-02 / D-01 / P-11 |
| 03 | 個別支援計画作成（既存児童 v3 改訂） | [`mockups/03_support_plan.html`](mockups/03_support_plan.html) | P-01 / P-02 / P-05 / P-08 / P-12（将来） |
| 04 | アセスメント入力（再アセス・差分更新） | [`mockups/04_assessment.html`](mockups/04_assessment.html) | A-01 / A-02 / A-03 / A-07 / A-10 |
| 05 | **新規児童 入所時アセス＋計画作成 — 音声×AI 一気通貫** | [`mockups/05_new_intake.html`](mockups/05_new_intake.html) | A-01〜A-03 / P-01 / P-02 / P-05 / P-08 / D-09・D-12・P-12（将来） |

---

## 設計の前提

### 要件IDとの連動
画面上の各UI要素には RFI の **要件ID（A-01〜D-12, UI-01〜RP-06, SE-01〜OP-04, FT-01〜FT-10）** をバッジ表示しています。要件定義書（提案書）との対応関係が一目でわかります。

### 将来要件の明示
本提案で △ロードマップ 扱いの機能（**D-12 音声入力 / P-12 AI下書き作成**）は、紫グラデーションのリボン＋「2027年〜」バッジで明示しています。初期リリーススコープと将来スコープの境界が明確になっています。

### 確認待ち事項
クライアントへの未確定論点（質問15問）は、関連UI付近に「⚠ 確認待ち（質問#N）」マーカーで可視化しています。

---

## ディレクトリ構成

```
michiruwa/
├── README.md           # 本ファイル
└── mockups/
    ├── index.html              # エントリポイント（5画面ナビゲーション）
    ├── 01_dashboard.html
    ├── 02_child_detail.html
    ├── 03_support_plan.html    # 既存児童の計画 v3 改訂
    ├── 04_assessment.html      # 再アセス・差分更新
    ├── 05_new_intake.html      # 新規児童 入所時 音声×AI 一気通貫フロー
    └── style.css               # 共通スタイル
```

---

## 技術スタック

- **HTML5 + CSS3**（フレームワーク・ビルドツールなし）
- **JavaScript なし**（タブ切替は `<input type="radio">` + `~` セレクタによる Pure CSS 実装）
- **フォント**: Hiragino Sans / Noto Sans JP（OS標準）
- **アイコン**: Unicode 絵文字（外部依存なし）

ブラウザ要件: モダンブラウザ（Chrome / Safari / Edge / Firefox の最新版）。

---

## カラートークン

| 役割 | カラー |
|---|---|
| Primary (Navy) | `#0f2044` |
| Accent (Teal) | `#14b8a6` |
| Warm (Orange) | `#f97316` |
| Future feature (Purple gradient) | `#c084fc` → `#a78bfa` |
| Background | `#f5f7fa` |

詳細は [`mockups/style.css`](mockups/style.css) 冒頭の `:root` 変数定義を参照してください。

---

## 本モックの位置付け

- **静的モック**であり、機能実装は含まれていません（DB・API・認証なし）
- **インタラクションは表現していません**（タブ切替のみ動作）
- 提案書（要件定義）の **UX 部分を可視化するため** のものです
- 色彩設計・情報配置・要件IDとの連動を確認する用途を想定しています

実装フェーズでは、本モックを参考にしつつ、要件定義書・既存UIガイドラインに沿った設計・開発を進めてください。

---

## 関連ドキュメント

- 提案書（要件定義）ドラフト: 別途共有
- RFI v4 回答済みチェックリスト: 別途共有
- 業務調査メモ（法令要件・業界標準）: 別途共有
