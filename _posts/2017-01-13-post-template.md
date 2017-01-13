---
title:  "template"
categories: 
  - Jekyll
tags:
  - update
author: Okada
---

<!-- htmlのコメントが使えます -->
<!-- この行↓を入れると目次を表示します -->
{% include toc %}

## はじめに

ここでは、投稿の方法を解説します。

このサイトはgithubで管理していますので、新規投稿はgithubのリポジトリにファイルを追加することになります。

ウェブブラウザからgithubのリポジトリに直接追加してもいいですし、`git clone` してから、まとめて add -> push もできます。

## 基本

 - `_posts` ディレクトリの直下に投稿ごとにファイルを追加します。
 - ファイル名は `YYYY-MM-DD-NAME.md` とします。
 - 投稿はマークダウン形式で記述します。
 - エンコードは `Unicode (UTF-8)` にしてください。（日本語だと文字化けするので）

![post image]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-1.PNG)

## ヘッダ

以下のヘッダを編集して使用してください。

```ruby
---
title:  "template"
categories: 
  - Jekyll
tags:
  - update
---

```

### category / tag

複数ある場合はこのようにも書けます。

```YAML:
---
title:  "template"
categories: 
  - Jekyll
  - Post Formats
tags:
  - update
  - standard
---
```

### author

このファイルで管理しています。
適宜、編集してください。

_data/authors.yml

```YAML
Shiraishi:    # <- ここがauthor名になります。
  name        : "Yuichi Shiraishi"
  (省略)
Chiba:
  name        : "Ken-ichi Chiba"
  (省略)

Okada:
  name        : "Ai Okada"
  (省略)
```

## マークダウンフォーマット

マークダウン(*.md) の記述方法は以下を参照してください。

マークダウン(*.md) の[基本的な書き方](https://help.github.com/articles/basic-writing-and-formatting-syntax/)

絵文字も使えます。:laughing:

ただし、`# ` (<H1>) は yamlヘッダの `title` が等価になりますので、`## ` (<H2>) 以降を使用します。

## 画像

画像はマークダウンもしくは `<a>` タグを使用してリンクを貼ります。

画像ファイルは投稿のテキストファイルとは別にリポジトリ直下の `/images/` ディレクトリに追加してください。

画像ファイルの名前は任意ですが、投稿ファイル名と揃えておいた方が重複がなくていいかもしれません。

**HTML:**

```html
<img src="{{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-2.PNG" alt="">
```

**or Kramdown:**

```markdown
![alt]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-2.PNG)
```

![alt]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-2.PNG)

### 画像サイズ

↑の方法で書くと、テキストの枠内になるように画像サイズを自動で調整します。

オリジナルサイズで表示したい場合は、 `.full` クラスを追加します。

**HTML:**

```html
<img src="{{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-2.PNG" alt="" class="full">
```

**or Kramdown:**

```markdown
![alt]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-2.PNG)
{: .full}
```

![alt]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-2.PNG)
{: .full}

### 画像の位置

画像の表示位置も設定できます。

**センタリング** (デフォルト)

:one: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

:two: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。
![image-center]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-DDG_Full_Vertical.1x.png){: .align-center} :three: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。
:four: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

:five: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。
---

**左寄せ**

:one: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

:two: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。
![image-left]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-DDG_Full_Vertical.1x.png){: .align-left} :three: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。
:four: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

:five: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

---

**右寄せ**

:one: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

:two: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。
![image-left]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-DDG_Full_Vertical.1x.png){: .align-right} :three: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。
:four: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

:five: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

### 画像からのリンク

[![duckduckgo.com]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-DDG_Full_Vertical.1x.png)](https://duckduckgo.com/)

### Genomon画像

Genomonくんの画像はリポジトリの `/assets/images/` ディレクトリにあります。

このように使用します。

![alt]({{ site.url }}{{ site.baseurl }}/assets/images/genomon21.png)
{: .small}

## コードブロック

コードブロックのハイライトで言語指定ができます。

以下で定義されているものが使えるようです。

[https://github.com/github/linguist/blob/master/lib/linguist/languages.yml](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)

**shellの場合**

```shell
python --version
```

**pythonの場合**

```python
import sys
print sys.version
```

## Minimal Mistakesへのリンク

このサイトは jekyll のテーマ [Minimal Mistakes](https://mademistakes.com/work/minimal-mistakes-jekyll-theme/) を使用しています。

このテーマのドキュメントは[ここ](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/) です。

