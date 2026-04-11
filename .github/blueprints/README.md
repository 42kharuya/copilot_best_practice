# `.github/blueprints/` について

このディレクトリは、プロジェクトごとに差し替えるための Blueprint をまとめる場所です。

ここには、次のような「そのまま本体には置かず、必要に応じてコピー・調整して使うもの」を置きます。

- `.github/agents/` に配置するカスタムエージェントの雛形
- `.github/instructions/` に配置する instructions の雛形
- `.github/skills/` に配置する skills の雛形
- `.github/workflows/` に配置する workflow の雛形
- プロジェクト固有情報の差し込み設計に使う記入ガイド

## 使い方

1. 必要な Blueprint を選ぶ
2. 実際の配置先へコピーする
3. プロジェクト固有の内容に書き換える

プロジェクト固有情報の差し込み設計から始めたい場合は、`project-context/` 配下を入口にしてください。

- `project-context/README.md`
- `project-context/project-context-checklist.md`
- `project-context/directory.AGENTS.md.example`
- `project-context/project-area.instructions.md.example`

## 置き方の方針

- **Core** には、どのプロジェクトでも変わりにくい共通原則だけを置く
- **Blueprints** には、差し込み用の雛形や記入例を置く
- **Optional Packs** には、特定用途向けの強い具体例や拡張を置く
