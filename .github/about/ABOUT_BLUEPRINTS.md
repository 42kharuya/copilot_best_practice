# `.github/blueprints/` とは

`.github/blueprints/` は、**そのまま有効化するファイル置き場ではなく、コピーして調整する雛形置き場**です。

## 役割

- Core に入れない可変情報の差し込み口を用意する
- 初見ユーザーが「どこから書き始めればよいか」を迷いにくくする
- 実運用ファイルとサンプルファイルを分離する

## 使い分け

- 普遍原則は `AGENTS.md` / `.github/copilot-instructions.md`
- 実際に有効化する agents / instructions / skills / workflows は各本番ディレクトリ
- コピーして調整する雛形は `.github/blueprints/`

## プロジェクト固有情報を差し込むときの入口

まずは次のセットから始めるのが安全です。

- `.github/blueprints/project-context/README.md`
- `.github/blueprints/project-context/project-context-checklist.md`
- `.github/blueprints/project-context/directory.AGENTS.md.example`
- `.github/blueprints/project-context/project-area.instructions.md.example`

## 使うときの注意

- 雛形はそのまま置かず、必要な場所へコピーしてから調整する
- Core に戻すべき内容まで Blueprint 側へ増やしすぎない
- 特定スタック依存の強い具体例は Optional Packs 側も検討する
