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

![post image](/images/2016-01-13-post-template-1.PNG)

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

```ruby
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

```
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

マークダウン(*.md) の(基本的な書き方)[https://help.github.com/articles/basic-writing-and-formatting-syntax/]

絵文字も使えます。:laughing:

ただし、ヘッダ `# ` (<H1>) は `title` が等価になりますので、`## ` (<H2>) 以降を使用します。

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

↑の方法で書くと、テキストの枠内に自動で調整されてしまいます。

それでは困るという場合は、 `.full` クラスを追加します。

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


### Genomon画像

Genomonくんの画像はリポジトリの `/assets/images/` ディレクトリにあります。

このように使用します。

![alt]({{ site.url }}{{ site.baseurl }}/assets/images/genomon21.png)

## コードブロック

コードブロックのハイライトで言語指定ができます。

以下で定義されているものが使えるようです。

https://github.com/github/linguist/blob/master/lib/linguist/languages.yml

**shellの場合**

<pre>
```shell
python --version
```
</pre>


```shell
python --version
```

**pythonの場合**

<pre>
```python
import sys
print sys.version
```
</pre>

```python
import sys
print sys.version
```

