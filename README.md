# Typst Math Notes Template

Typst 用の数学講義ノート・レポート作成テンプレートです。
シンプルで見やすいデザイン、定理環境、自動番号付け、日本語対応（CJK spacer 含む）を特徴としています。

## ✨ 特徴

- **自動ナンバリング**: 章ごとにリセットされる数式・定理番号 (例: Theorem 1.2.3, Equation 1.2.4)
- **相互参照**: 定理番号や数式番号へのリンク (`@label`)
- **目に優しい配色**: パステルカラーを用いた定理・定義ブロック
- **日本語対応**: 原ノ味明朝/ヒラギノ明朝 + CJK Spacer（日本語と英数字の間の自動スペース）
- **ディレクトリ構成**: 章ごとにファイルを分割して管理しやすい構成

## 🚀 使い方

### 1. このテンプレートを使用する

GitHub 右上の **"Use this template"** ボタンをクリックし、新しいリポジトリを作成してください。

### 2. 環境構築

以下のいずれかの方法で Typst 環境を用意します。

- **VS Code (推奨):** 拡張機能 [Tinymist](https://marketplace.visualstudio.com/items?itemName=myriad-dreamin.tinymist) をインストール。
- **CLI:** [Typst 公式](https://github.com/typst/typst)の手順に従いインストール。

### 3. 執筆ガイド

`chapters/` フォルダ内に `.typ` ファイルを作成し、`main.typ` で `#include` します。

#### 定理・定義の書き方

`lib.typ` をインポートすることで、以下の環境が使えます。

```typst
#import "../lib.typ": *

// タイトルあり、ラベルあり
#theorem(title: "平均値の定理", lab: <mean_value>)[
  関数 $f(x)$ が...
]

// 参照する
定理@mean_value より、...
```


利用可能な環境:

- `#theorem` (定理)
- `#proposition` (命題)
- `#lemma` (補題)
- `#corollary` (系)
- `#definition` (定義)
- `#proof` (証明)

#### 数式の書き方

ブロック数式（前後にスペース）にすると自動で番号が付きます。

```typst
$e^(i pi) = -1$ <euler>

式@euler は有名である。
```

### ⚠️ VS Code でのエラー回避

各章のファイルを開いている際に「参照エラー」等が出る場合は、Tinymist の設定で **Pin Main File** を行ってください。

1.  VS Code 下部のステータスバーにある `detached` などをクリック
2.  `main.typ` を選択

## 📄 ライセンス

This project is licensed under the MIT License.
