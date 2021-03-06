---
title:  "template"
categories: 
  - Jekyll
  - 未分類
tags:
  - update
  - サンプル
author: Okada
---

## はじめに

ここでは、投稿の方法を解説します。

このサイトはgithubで管理していますので、新規投稿はgithubのリポジトリにファイルを追加することになります。

ウェブブラウザからgithubのリポジトリに直接追加してもいいですし、`git clone` してから add -> push もできます。

<!-- htmlのコメントが使えます -->
<!-- この行↓を入れると目次を表示します -->
{% include toc %}

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

```ruby
Shiraishi:                            # <- ここがauthor名になります。
  name        : "Yuichi Shiraishi"    # <- サイトにはここが表示されます。
  (省略)
Chiba:
  name        : "Ken-ichi Chiba"
  (省略)

Okada:
  name        : "Ai Okada"
  (省略)
```

authorに設定できるソーシャルプロファイル

```ruby
  name             : "Team Genomon"
  uri              : "/"
  email            : "genomon.devel@gmail.com"
  bio              : "The Zen of Cancer Genome Analysis"
  avatar           : "/assets/images/genomon31_c.png"
  location         : "Tokyo, JP"
  bitbucket        :
  codepen          :
  dribbble         :
  flickr           :
  facebook         :
  foursquare       :
  github           : "Genomon-Project"
  google_plus      :
  keybase          :
  instagram        :
  lastfm           :
  linkedin         :
  pinterest        :
  soundcloud       :
  stackoverflow    :
  steam            :
  tumblr           :
  twitter          :
  vine             :
  weibo            :
  xing             :
  youtube          :
```

## マークダウンフォーマット

マークダウン(*.md) の記述方法は以下を参照してください。

[基本的な書き方](https://help.github.com/articles/basic-writing-and-formatting-syntax/)

絵文字も使えます。:laughing:

[絵文字チートシート](http://www.webpagefx.com/tools/emoji-cheat-sheet/)

:heavy_exclamation_mark: `# ` (<H1>) は yamlヘッダの `title` が等価になりますので、`## ` (<H2>) 以降を使用します。

## 画像

画像はマークダウンもしくは `<a>` タグを使用してリンクを貼ります。

画像ファイルは投稿のテキストファイルとは別にリポジトリ直下の `/images/` ディレクトリに追加してください。

画像ファイルの名前は任意ですが、投稿ファイル名と揃えておいた方が重複がなくていいかもしれません。

**HTML:**

<img src="{{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-2.PNG" alt="">

**Kramdown:**

![alt]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-2.PNG)

### キャプション

{% capture fig_img %}
![alt]({{ "/images/2016-01-13-post-template-2.PNG" | absolute_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>fig1. キャプションの例</figcaption>
</figure>

---

**上付きにする場合**

{% capture fig_img %}
![alt]({{ "/images/2016-01-13-post-template-2.PNG" | absolute_url }})
{% endcapture %}

<figure>
  <figcaption>fig2. 上付きキャプション</figcaption>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
</figure>

---

**センタリングする場合**

{% capture fig_img %}
![alt]({{ "/images/2016-01-13-post-template-2.PNG" | absolute_url }})
{% endcapture %}

<figure style="display: block; text-align:center;">
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>fig3. センタリング</figcaption>
</figure>


### 画像の位置

画像の表示位置も設定できます。

**1. デフォルト**

![image-center]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-3.png)

---

**2. センタリング**

:one: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

![image-center]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-3.png){: .align-center}

:two: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

---

**3. 左寄せ**

:interrobang: [注意] 右寄せと左寄せを設定した場合、文章の回り込みが発生します。

:one: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

![image-left]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-3.png){: .align-left}

:two: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

---

**4. 右寄せ**

:one: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。

![image-left]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-3.png){: .align-right}

:two: これは表示確認用のテキストです。ブラウザで画像との位置関係を確認してください。


---

**[参考] グリッド表示**

[https://mmistakes.github.io/minimal-mistakes/post%20formats/post-gallery/](https://mmistakes.github.io/minimal-mistakes/post%20formats/post-gallery/)

### 画像からのリンク

[![duckduckgo.com]({{ site.url }}{{ site.baseurl }}/images/2016-01-13-post-template-DDG_Full_Vertical.1x.png)](https://duckduckgo.com/)

### Genomon画像

Genomonくんの画像はリポジトリの `/assets/images/` ディレクトリにあります。

このように使用します。

![alt]({{ site.url }}{{ site.baseurl }}/assets/images/genomon21.png)

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

## テーブル

```markdown
| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:| <- この行で右寄せ、センタリング、左寄せを指定する
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
```

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |


## メモ

**memo** 文章の最後に `{: .notice}` をつけます。
{: .notice}

いろいろ種類があります。

| Notice Type | Class              |
| ----------- | -----              |
| Default     | `.notice`          |
| Primary     | `.notice--primary` |
| Info        | `.notice--info`    |
| Warning     | `.notice--warning` |
| Success     | `.notice--success` |
| Danger      | `.notice--danger`  |

**example** `{: .notice}` class
{: .notice}

**example** `{: .notice--primary}` class
{: .notice--primary}

**example** `{: .notice--info}` class
{: .notice--info}

**example** `{: .notice--warning}` class
{: .notice--warning}

**example** `{: .notice--success}` class
{: .notice--success}

**example** `{: .notice--danger}` class
{: .notice--danger}

---

{% capture notice-text %}
`<div>` タグに `.notice` クラスをつけてもよいです。

 - list item1
 - list item2
{% endcapture %}

<div class="notice--info">
  <h4>Notice Headline:</h4>
  {{ notice-text | markdownify }}
</div>


## Minimal Mistakesへのリンク

このサイトは jekyll のテーマ [Minimal Mistakes](https://mademistakes.com/work/minimal-mistakes-jekyll-theme/) を使用しています。

このテーマのドキュメントは[ここ](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/) です。

