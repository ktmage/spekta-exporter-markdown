# @ktmage/spekta-exporter-markdown

Spekta の Markdown Exporter プラグイン。IR から Markdown 形式の仕様書を生成する。

## インストール

> npm パッケージは未公開です。現在は [Spekta モノレポ](https://github.com/ktmage/spekta) のサブモジュールとして利用できます。

npm 公開後は以下でインストールできるようになる予定です。

```bash
npm install @ktmage/spekta-exporter-markdown
```

## 機能

- IR の各ページを個別の Markdown ファイルとして出力
- セクションの階層構造を見出しレベル（h1-h4）にマッピング
- 画像ファイルを `images/` ディレクトリにコピーし、相対パスで参照
- Mermaid グラフ、手順リスト（steps）、関連ページリンク（see）、補足（why）に対応

## 設定例

`.spekta.yml` の `exporter` セクションにプラグインを追加する。

```yaml
exporter:
  "@ktmage/spekta-exporter-markdown":
    name: "My Project"
```

`outputDir` を省略した場合、デフォルトは `markdown`。

## 対応ノード

| ノード | 説明 |
|--------|------|
| `section` | セクション（見出しレベルにマッピング） |
| `summary` | セクションの要約 |
| `why` | 補足説明 |
| `see` | 関連ページリンク |
| `steps` / `step` | 手順リスト |
| `image` | 画像（`images/` にコピー） |
| `graph` | Mermaid グラフ |
| `text` | テキストブロック |
| `code` | コードブロック |
| `callout` | コールアウト（note / warning / tip） |
| `list` / `item` | リスト |

## 出力形式

```
<outputDir>/
  <ページタイトル>.md
  images/
    <画像ファイル名>
```

各 `.md` ファイルはページタイトルをファイル名として使用する。画像を含むページがある場合のみ `images/` ディレクトリが作成される。

## ライセンス

[MIT](LICENSE)
