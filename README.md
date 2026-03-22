# @ktmage/spekta-exporter-markdown

Spekta Markdown Exporter plugin. Generates Markdown documentation from IR.

Spekta の Markdown Exporter プラグイン。IR から Markdown 形式の仕様書を生成する。

## Table of Contents / 目次

- [English](#english)
- [日本語](#japanese)

<a id="english"></a>
## English

> [!CAUTION]
> **Disclaimer:**
> This project is experimental. It is provided "as-is" without warranty of any kind. APIs and output format may change without notice. Use at your own risk.

### Features

- Outputs each IR page as an individual Markdown file
- Maps section hierarchy to heading levels (h1-h4)
- Copies image files to `images/` with relative path references
- Supports all IR node types: text, code, callout, list, steps, graph, see, why, image

### Installation

> npm package is not yet published. Currently available as a submodule of the [Spekta monorepo](https://github.com/ktmage/spekta).

After npm publication:

```bash
npm install @ktmage/spekta-exporter-markdown
```

### Configuration

```yaml
exporter:
  "@ktmage/spekta-exporter-markdown":
    name: "My Project"
```

Default output directory is `markdown`.

### Supported Nodes

| Node | Markdown Output |
|------|-----------------|
| `section` | Heading (`##`, `###`, `####`) |
| `summary` | Paragraph |
| `why` | Blockquote (`> **Why**: ...`) |
| `see` | Link (`Related: [title](title.md)`) |
| `steps` / `step` | Ordered list |
| `image` | Image (`![alt](images/file.png)`) |
| `graph` | Fenced code block (` ```mermaid `) |
| `text` | Paragraph |
| `code` | Fenced code block (` ```lang `) |
| `callout` | Blockquote (`> **Note/Warning/Tip**: ...`) |
| `list` / `item` | Unordered list |

### Output Structure

```
<outputDir>/
  <page title>.md
  images/
    <image files>
```

### License

[MIT](LICENSE)

---

<a id="japanese"></a>
## 日本語

> [!CAUTION]
> **免責事項：**
> 本プロジェクトは実験的な取り組みです。いかなる保証もなく「現状のまま」提供されます。API や出力形式は予告なく変更される可能性があります。ご利用は自己責任でお願いいたします。

### 機能

- IR の各ページを個別の Markdown ファイルとして出力
- セクションの階層構造を見出しレベル（h1-h4）にマッピング
- 画像ファイルを `images/` ディレクトリにコピーし、相対パスで参照
- 全 IR ノードタイプに対応: text, code, callout, list, steps, graph, see, why, image

### インストール

> npm パッケージは未公開です。現在は [Spekta モノレポ](https://github.com/ktmage/spekta) のサブモジュールとして利用できます。

npm 公開後は以下でインストールできるようになる予定です。

```bash
npm install @ktmage/spekta-exporter-markdown
```

### 設定例

```yaml
exporter:
  "@ktmage/spekta-exporter-markdown":
    name: "My Project"
```

デフォルトの出力ディレクトリは `markdown`。

### 対応ノード

| ノード | Markdown 出力 |
|--------|---------------|
| `section` | 見出し（`##`, `###`, `####`） |
| `summary` | 段落 |
| `why` | 引用（`> **なぜ**: ...`） |
| `see` | リンク（`関連: [title](title.md)`） |
| `steps` / `step` | 番号付きリスト |
| `image` | 画像（`![alt](images/file.png)`） |
| `graph` | コードブロック（` ```mermaid `） |
| `text` | 段落 |
| `code` | コードブロック（` ```lang `） |
| `callout` | 引用（`> **Note/Warning/Tip**: ...`） |
| `list` / `item` | 箇条書きリスト |

### 出力形式

```
<outputDir>/
  <ページタイトル>.md
  images/
    <画像ファイル名>
```

### ライセンス

[MIT](LICENSE)
