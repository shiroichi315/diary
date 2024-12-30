+++
title = "「関数型ドメインモデリング」関数からサービス、ワークフローまで一貫した設計思想を得ることができる良書"
date = 2024-08-03
[taxonomies]
tags=["Read", "Input", "Software Archtecture"]

[extra]
meta = [
  {property = "og:title", content = "「関数型ドメインモデリング」関数からサービス、ワークフローまで一貫した設計思想を得ることができる良書"}
]
+++

「関数型ドメインモデリング ドメイン駆動設計とF#でソフトウェアの複雑さに立ち向かおう」の書籍を読んだ。

大前提、本書はソフトウェア設計に関する入門書である。「関数型」や「ドメイン駆動設計」の用語に怖気付く必要はない。

個人的な感想を殴り書きではあるがまとめる。

# 個人的に感じていたソフトウェア設計に関する形式知への課題
前提として本書を読む前までに自身が感じていた課題、それは設計をする規模に関係なく本来一貫して重要であるはずの設計思想が、異なる文脈へと散在していることである。

例えば、情報の隠蔽に関する話題は
- ドメイン集約のメソッド公開範囲
- マイクロサービスのインターフェースを小さく保つ話
- ワークフロー間のドメインイベントの話題

のように規模（または実装手段）の違いによる異なる文脈へ散在しているように感じる（本書でドメイン境界に触れるのは境界付けられたコンテキストでの話題がほとんどだが）

# 「関数」という一貫した設計思想
本書ではまず第2章の「ドメインの理解」でドメインエキスパートと一緒に記述するドメイン文書化の独自フォーマットを紹介している。このフォーマットはある境界付けられたコンテキストにおけるワークフローを記述するもので、インプットとアウトプット・関係する副作用を明示にする。いわば関数の設計文書のようになっている。

第3章の「関数型アーキテクチャ」の説明も同様、オニオンアーキテクチャを例にしあるサービスにおける処理の通り道を図に起こしながら、インプットとアウトプット・そしてドメインから分離すべき副作用について語られる。

第8章「関数の理解」ではサービスから低レベル処理へと規模が移る。関数同士を一つのレールのように繋げる関数合成について語られる。関数型プログラミングを学ぶ上で登竜門となることが多い「モナド」という単語の利用は避け、関数同士を合成したくなるモチベーション（Linuxのパイプ処理が例に出ている）を図を用いながらごく一般的な流れで説明がされる。

そして「8.4.2 関数からアプリケーション全体を構築する」が個人的に一番しっくりきた部分、関数合成を使った組み合わせによって低レベル処理→サービス→ワークフロー→アプリケーション、の順に同じ「関数」という設計思想で規模の違いを一つに取りまとめるような説明がされる。

続く第9章「実装:パイプラインの合成」以降は実装時の詳細について。例として関数型プログラミングの「部分適用」による依存性注入の説明、関数で取り扱う副作用を関数の型シグネチャ内で明示に扱い、副作用を分離するパターンが書かれている。第3章でオニオンアーキテクチャの例で語られたように副作用の分離を一貫する設計思想として扱う。

# まとめ
関数型プログラミングは業務でも使っていて個人的に推しているのだが、その理由を上手く説明できずに悩んでいた。そして導入として書いたソフトウェア設計に関する課題が関数型プログラミングのパターンによって解決できるかもしれないことを学んだ。

アプリケーション全体をワークフローの関数合成で表すような設計思想はとても素敵だと思っていて、より自律的なプロダクト開発ができるようになる第一歩だと思う。

ぜひ人におすすめしたい一冊になった。