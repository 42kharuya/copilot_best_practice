# 🤖 GitHub Copilot の全体像ガイド

このファイルは、GitHub Copilot 関連機能の**全体像と使い分けの概要**だけをまとめる場所です。

各機能の詳細な使い方は `.github/about/` に集約します。

## 3つのレイヤー

このリポジトリは、Copilot 関連ファイルを次の 3 層で整理します。

| レイヤー | 役割 | 主な配置先 |
| :--- | :--- | :--- |
| **Core** | どのプロジェクトでも変わりにくい共通原則 | `AGENTS.md`, `.github/copilot-instructions.md` |
| **Blueprints** | プロジェクトごとにコピーして差し込む雛形 | `.github/blueprints/` |
| **Optional Packs** | 必要な人だけ追加導入する具体例や拡張 | `.github/optional-packs/` |

## 機能ごとの見方

| 種類 | 主な配置先 | 役割 |
| :--- | :--- | :--- |
| **共通原則** | `AGENTS.md` | 安全性、変更方針、検証姿勢などの土台 |
| **全体ルール** | `.github/copilot-instructions.md` | リポジトリ全体で守らせたい応答・提案ルール |
| **局所ルール** | `各ディレクトリ/AGENTS.md`、`.github/instructions/` | 特定領域だけで必要な補足ルール |
| **カスタムエージェント** | `.github/agents/` | 特定用途に特化した役割定義 |
| **skills** | `.github/skills/` | エージェントに実行させる具体的手順 |
| **workflows** | `.github/workflows/` | クラウド側で動く環境構築や実行準備 |

## 使い分けの基本

- まず **Core** をそのまま使う
- 次に必要な雛形を `.github/blueprints/` からコピーして調整する
- プロジェクト固有情報の差し込み設計は `.github/blueprints/project-context/` から始める
- 強い前提を持つ具体例は `.github/optional-packs/` から追加する

## 詳細説明

- `AGENTS.md` の説明: `.github/about/ABOUT_ROOT_AGENTS.md`
- `.github/copilot-instructions.md` の説明: `.github/about/ABOUT_COPILOT_INSTRUCTIONS.md`
- agents の説明: `.github/about/ABOUT_AGENTS.md`
- instructions の説明: `.github/about/ABOUT_INSTRUCTIONS.md`
- skills の説明: `.github/about/ABOUT_SKILLS.md`
- workflows の説明: `.github/about/ABOUT_WORKFLOWS.md`
