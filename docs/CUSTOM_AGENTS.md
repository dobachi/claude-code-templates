# カスタムエージェントの使用方法

## knowledge-work カテゴリ

以下のカスタムエージェントが利用可能です：

| エージェント | 説明 |
|-------------|------|
| `knowledge-work/researcher` | 正確性重視の情報調査 |
| `knowledge-work/project-manager` | R&Dプロジェクト管理 |
| `knowledge-work/whitepaper-writer` | 意思決定者向け技術文書 |
| `knowledge-work/paper-analyst` | 論文の深い分析・批評 |

## インストール方法

環境変数でカスタムリポジトリを指定して実行：

```bash
CCT_REPO_OWNER=dobachi \
CCT_REPO_NAME=claude-code-templates \
CCT_REPO_BRANCH=custom \
CCT_COMPONENTS_PATH=cli-tool/components \
npx github:dobachi/claude-code-templates#custom --agent knowledge-work/researcher --yes
```

## エイリアス設定（推奨）

`.bashrc` または `.zshrc` に追加：

```bash
# カスタムCCTエイリアス
alias cct-custom='CCT_REPO_OWNER=dobachi CCT_REPO_NAME=claude-code-templates CCT_REPO_BRANCH=custom CCT_COMPONENTS_PATH=cli-tool/components npx github:dobachi/claude-code-templates#custom'
```

使用例：
```bash
cct-custom --agent knowledge-work/researcher --yes
cct-custom --agent knowledge-work/project-manager --yes
```

## 複数エージェントの同時インストール

```bash
cct-custom \
  --agent knowledge-work/researcher \
  --agent knowledge-work/project-manager \
  --agent knowledge-work/whitepaper-writer \
  --agent knowledge-work/paper-analyst \
  --yes
```

## 環境変数一覧

| 変数名 | 説明 | デフォルト値 |
|--------|------|-------------|
| `CCT_REPO_OWNER` | リポジトリオーナー | `davila7` |
| `CCT_REPO_NAME` | リポジトリ名 | `claude-code-templates` |
| `CCT_REPO_BRANCH` | ブランチ名 | `main` |
| `CCT_COMPONENTS_PATH` | コンポーネントパス | `cli-tool/components` |
