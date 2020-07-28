# awesome-bert-japanese

日本語の学習済み BERT は文から単語への分かち書き，単語からサブワードへの分割の処理にいくつかの選択肢が存在します．
また，単語をサブワードに分割する際に利用する語彙についても構築方法に数種類のバリエーションがあります．

本リポジトリでは，公開されている学習済み BERT モデルについて，
分かち書き・サブワード分割・語彙構築アルゴリズムそれぞれどのアルゴリズムが採用されているかを表にまとめています．

A list of pre-trained BERT models for Japanese.
Japanese is a complicated language; which doesn't have any word boundaries and has many kind of characters.


## Adding Your Model

表に学習済みの BERT モデルを追加したい場合は Issue/PR よりお願いします．

If you are interested in adding new pretrained BERT model for Japanese, please feel free to open issue/PR.


## Model


| モデル           | 文 -> 単語     | 単語 -> サブワード           | サブワード分割のための語彙構築アルゴリズム     |
| :--------------- | :------------- | :--------------------------- | :--------------------------------------------- |
| 多言語 BERT      | Whitespace     | WordPiece                    | BPE?                                           |
| Kikuta           | --             | Sentencepiece (文から直接)   | Sentencepiece (model_type=unigram)             |
| ホットリンク     | --             | Sentencepiece (文から直接)   | Sentencepiece (model_type=unigram)             |
| 京都大学         | Juman++        | WordPiece                    | subword-nmt (BPE)                             |
| ストックマーク   | MeCab          | --                           | --                                             |
| 東北大学 (a)     | MeCab          | WordPiece                    | Sentencepiece (model_type=bpe)                 |
| 東北大学 (b)     | MeCab          | Character                    | Sentncepiece (model_type=character)           |
| NICT (a)         | MeCab          | WordPiece                    | subword-nmt (BPE)                                            |
| NICT (b)         | MeCab          | ---                          | ---                                            |
| 東京大学         | MeCab          | WordPiece                    | ? (BPE)                                            |



## Reference

- 多言語 BERT (2018/11): https://github.com/google-research/bert/blob/master/multilingual.md
- Kikuta (2019/01): https://yoheikikuta.github.io/bert-japanese/
- ホットリンク (2019/03): https://www.hottolink.co.jp/blog/20190311_101674/
- 京都大学 (2019/03): http://nlp.ist.i.kyoto-u.ac.jp/index.php?BERT%E6%97%A5%E6%9C%AC%E8%AA%9EPretrained%E3%83%A2%E3%83%87%E3%83%AB
- ストックマーク (2019/04): https://qiita.com/mkt3/items/3c1278339ff1bcc0187f
- 東北大学 (2019/12): https://github.com/cl-tohoku/bert-japanese
- NICT (2020/03): https://alaginrc.nict.go.jp/nict-bert/index.html
- 東京大学 (2020/03): https://ai-health.m.u-tokyo.ac.jp/uth-ber
