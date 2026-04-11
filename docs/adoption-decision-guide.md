# 導入判断ガイド

このガイドは、GitHub Copilot 関連ファイルを**どこまで導入すべきか**を判断するためのものです。

重要なのは、最初から全部入れることではなく、**自分の状況に合う導入レベルを選ぶこと**です。

## まず結論

- 出力ブレを抑えたいだけなら **最小導入**
- プロジェクト固有情報まで安全に渡したいなら **標準導入**
- クラウド実行や専用役割まで整えたいなら **拡張導入**

## 判断フロー

次の順に判断してください。

### 1. まず確認すること

- 個人利用か、チーム利用か
- 単一構成か、複数ディレクトリで役割が分かれる構成か
- 出力ブレだけ抑えたいのか、レビューや運用まで整えたいのか
- Cloud Agent まで使うかどうか

### 2. レベルを選ぶ基準

#### 最小導入が向いているケース

- 個人で使う
- まずは回答のブレを減らしたい
- ディレクトリごとの細かいルールはまだ不要
- Cloud Agent は使わない

#### 標準導入が向いているケース

- チームで使う、または将来チーム利用を想定している
- プロジェクト固有情報を安全に差し込みたい
- ディレクトリごとに役割やルールが違う
- レビュー観点や実装方針を揃えたい

#### 拡張導入が向いているケース

- Cloud Agent を使いたい
- 定型作業を agents / skills に分けたい
- ワークフローや自動実行まで整えたい
- 強い前提を持つ具体例も併用したい

## 導入レベル別ガイド

### レベル1: 最小導入

**目的:** まず AI の出力ブレを減らす

**導入するもの:**

- [AGENTS.md](../AGENTS.md)
- [.github/copilot-instructions.md](../.github/copilot-instructions.md)

**この段階で十分なケース:**

- まだルールが少ない
- 個人で試している
- プロジェクト構造が単純

**無理に入れなくてよいもの:**

- `各ディレクトリ/AGENTS.md`
- `.github/instructions/`
- `.github/agents/`
- `.github/skills/`
- `.github/workflows/`

### レベル2: 標準導入

**目的:** プロジェクト固有情報を差し込み、実装判断を安定させる

**追加で導入するもの:**

- [.github/blueprints/project-context/project-context-checklist.md](../.github/blueprints/project-context/project-context-checklist.md)
- [.github/blueprints/project-context/directory.AGENTS.md.example](../.github/blueprints/project-context/directory.AGENTS.md.example)
- [.github/blueprints/project-context/project-area.instructions.md.example](../.github/blueprints/project-context/project-area.instructions.md.example)
- 必要に応じた `各ディレクトリ/AGENTS.md`
- 必要に応じた `.github/instructions/*.instructions.md`

**この段階が向いているケース:**

- フロントエンドとバックエンドでルールが違う
- 主要ディレクトリごとに責務が分かれている
- チームで共通の変更判断を持ちたい

**判断の目安:**

- ディレクトリ固有の構造や注意点がある → `各ディレクトリ/AGENTS.md`
- パス単位で継続適用したい実装ルールがある → `.github/instructions/*.instructions.md`

### レベル3: 拡張導入

**目的:** 専用役割、定型作業、自動実行まで整える

**追加で導入するもの:**

- `.github/agents/`
- `.github/skills/`
- `.github/workflows/`
- 必要に応じて `.github/optional-packs/`

**この段階が向いているケース:**

- コードレビューや調査役を分けたい
- lint / テスト / 整形などの定型作業を整理したい
- Cloud Agent に作業させたい
- 強い具体例を本体から分離したまま導入したい

## 各レベルで必要なファイル

| 導入レベル | 必須 | 任意 |
| :--- | :--- | :--- |
| 最小導入 | `AGENTS.md`, `.github/copilot-instructions.md` | なし |
| 標準導入 | 最小導入 + `各ディレクトリ/AGENTS.md` または `.github/instructions/*.instructions.md` | Blueprint 由来の補助資料 |
| 拡張導入 | 標準導入 + `.github/agents/`, `.github/skills/`, `.github/workflows/` | `.github/optional-packs/` |

## 過剰導入を避ける指針

次の状態なら、導入しすぎの可能性があります。

- まだ困りごとが明確でないのに agents / skills / workflows まで入れている
- ディレクトリごとの差がないのに instructions を増やしている
- 一時的な事情を Core に書いている
- チームで運用しないのに複雑な構成を先に作っている

迷ったときは、**1段階下の導入レベルから始める**のが安全です。

## おすすめの進め方

1. まず Core だけ入れる
2. 実際に困った場面を確認する
3. 差し込みが必要な場所だけ標準導入へ進める
4. 自動化や専用役割が必要になったら拡張導入へ進める

## 関連リンク

- [README.md](../README.md)
- [.github/COPILOT_USAGE.md](../.github/COPILOT_USAGE.md)
- [.github/about/README.md](../.github/about/README.md)
- [.github/blueprints/project-context/README.md](../.github/blueprints/project-context/README.md)
