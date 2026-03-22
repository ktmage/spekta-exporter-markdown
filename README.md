# @ktmage/spekta-exporter-markdown

Spekta の IR（中間表現）から Markdown ファイルを生成するエクスポータープラグイン。

## 機能

- IR の各ページを個別の Markdown ファイルとして出力
- セクションの階層構造を見出しレベル（h1-h4）にマッピング
- 画像ファイルを `images/` ディレクトリにコピーし、相対パスで参照
- Mermaid グラフ、手順リスト（steps）、関連ページリンク（see）、補足（why）に対応

## 設定例

`.spekta.yml` の `exporters` セクションにプラグインを追加する。

```yaml
exporters:
  - name: markdown
    outputDir: docs/markdown
```

`outputDir` を省略した場合、デフォルトは `markdown`。

## 出力形式

```
<outputDir>/
  <ページタイトル>.md
  images/
    <画像ファイル名>
```

各 `.md` ファイルはページタイトルをファイル名として使用する。画像を含むページがある場合のみ `images/` ディレクトリが作成される。
