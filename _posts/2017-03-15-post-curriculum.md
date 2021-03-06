---
title:  "ゲノム解析入門カリキュラム"
categories:
  - general
tags:
  - education
author: Shiraishi
---


現代のゲノム解析研究を遂行するためには、もちろんある程度情報解析の能力を身につけていることが必須になりつつあり、
とはいえ、それを完全に独学で習得することは結構難しいです。
自分たちの研究室は、かなり長くゲノム解析に従事してきていて、またいろいろな付き合いもあることから、
特に医学系の研究者から、「若い学生さんやポスドクを短期間預かり、ゲノム解析の技術を教えて欲しい！」
とお願いされることが結構頻繁にあります。
日々の仕事でとても忙しいこともあるのだが、もちろんそういった情報技術を備えた人が増えてもらうことは大切なので、
受け入れを承諾した方には、その人がきちんとしたスキルを身につけることができるように対応することにしています。
また、自分たちの研究室でも、これまでゲノム解析をしたことがないという人が新しく入ってきた時に、できるだけ最短で効率よく技術を教えることは大切です。


実際に教える際に、「何を教えよう・・？」とその都度考えるのは大変なので、
事前に大体カリキュラムは決めていて、それに従って教えるようにしています（またはスタッフの誰かにお願いする）。
読者の役に立つことがあるかもしれないことと、備忘録的な意味も含め、今回はそのカリキュラムを紹介します。

## Genomon開発グループによるゲノム解析入門カリキュラム

1. [スパコン](https://supcom.hgc.jp/japanese/)にログイン～コマンド上で、editorを編集して、簡単なスクリプト処理プログラムを書く
  - スパコンにログイン（putty?のインストール、vi or emacsに親しむ、linuxに親しむ）
  - pythonで簡単なテキスト処理プログラムを書く（UCSCのrefGeneでcoding遺伝子だけを抽出するなど簡単なテキスト処理）
  - HGCスパコンの使い方の講習会資料を読む
  - 簡単なプログラム(pythonのテキスト処理）で良いので、スパコンで動かす
  - githubに登録して、上の処理をuploadする（以下、開発するスクリプトは全てgithubに登録）
  
2. alignmentをしてみる
  - fastqのフォーマットを理解（[こちらのページ](https://en.wikipedia.org/wiki/FASTQ_format)を読んでもらう）
  - bwaでアラインメントをしてみる（小さいデータを作る, headコマンドなどの使い方）
  - samtoolsでbam変換、sort, duplicate, index処理を順にやってもらう
  - 2, 3の処理をスパコンで実装（シェルスクリプトを書いて、クラスターにジョブを投げる）
  - fastqをsplitして、アラインメント、sort、マージ、indexの順のプログラムをスパコンで実装（簡単なアラインメントパイプラインの作成）
   
3. mutation callの原理
  - samtools mpileupを実行して、フォーマットを理解
  - SNPを抽出する簡易的なプログラムを書いてもらう
  - 見つけた変異をIGVなどで実際に見て見る（false positiveがどのようにして生じるかも理解する）
  - regionを分割して、スパコンで実行するプロシージャーを作成

4. コピー数の計算
  - それぞれのexonごとに、張り付いたリード数をカウント（主にbedtoolsを使う）
  - tumorとnormalで比率を取る
  - tumor / normalのdepthをRなどでプロットして、コピー数が変化しているところを調べる


これはほとんどプログラムを書いたことのない人（でもプログラムを独学で書けるようになりそうな人）が大体１ヶ月で終える目標のカリキュラムです。
もちろんその方の最終目標やレベルにより多少変わりますが、基本は以下のカリキュラムを使います。
グループ内での研修メニューの策定などの際に参考にしていただければ幸いです。
