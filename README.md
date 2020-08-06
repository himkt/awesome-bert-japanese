# awesome-bert-japanese

日本語の学習済み BERT は文から単語への分かち書き，単語からサブワードへの分割の処理にいくつかの選択肢が存在します．
また，単語をサブワードに分割する際に利用する語彙についても構築方法に数種類のバリエーションがあります．

本リポジトリでは，公開されている学習済み BERT モデルについて，
分かち書き・サブワード分割・語彙構築アルゴリズムそれぞれどのアルゴリズムが採用されているかを表にまとめています．

A list of pre-trained BERT models for Japanese.
Japanese is a complicated language; which doesn't have any word boundaries and has many kind of characters.
Therefore, it requires word segmentation before tokenizing word into subwords.
I summarize pretrained BERT models for Japanese by `word segmentation algorithm`, `subword tokenization algorithm`, and `algorithm for constructing vocabulary used in subword tokenization`.


## Model


| Model                      | Sentence -> Words                                                                                                                                    | Word -> Subword                           | Algorithm for constructing vocabulary used in subword tokenization     |
| :------------------------- | :----------------                                                                                                                                    | :---------------------------------------- | :--------------------------------------------------------------------- |
| Google (Multilingual BERT) | Whitespace                                                                                                                                           | WordPiece                                 | BPE?                                                                   |
| Kikuta                     | --                                                                                                                                                   | Sentencepiece (without word segmentation) | Sentencepiece (model_type=unigram)                                     |
| Hotto Link Inc.            | --                                                                                                                                                   | Sentencepiece (without word segmentation) | Sentencepiece (model_type=unigram)                                     |
| Kyoto University           | Juman++                                                                                                                                              | WordPiece                                 | subword-nmt (BPE)                                                      |
| Stockmark Inc.             | MeCab (mecab-ipadic-neologd)                                                                                                                         | --                                        | --                                                                     |
| Tohoku University (a)      | MeCab (mecab-ipadic)                                                                                                                                 | WordPiece                                 | Sentencepiece (model_type=bpe)                                         |
| Tohoku University (b)      | MeCab (mecab-ipadic)                                                                                                                                 | Character                                 | Sentencepiece (model_type=character)                                   |
| NICT (a)                   | MeCab (mecab-jumandic)                                                                                                                               | WordPiece                                 | subword-nmt (BPE)                                                      |
| NICT (b)                   | MeCab (mecab-jumandic)                                                                                                                               | ---                                       | ---                                                                    |
| akirakubo (a)              | MeCab (unidic-cwj) for Wikipedia and Aozora bunko written in `新仮名` + MeCab (unidic_qkana) for Aozora bunko written in `旧仮名`                    | WordPiece                                 | subword-nmt (BPE)                                                      |
| akirakubo (b)              | SudachiPy (SudachiDict_core + A mode) for Wikipedia and Aozora bunko written in `新仮名` + MeCab (unidic_qkana) for Aozora bunko written in `旧仮名` | WordPiece                                 | subword-nmt (BPE)                                                      |
| The University of Tokyo    | MeCab (mecab-ipadic-neologd + user dic (J-MeDic)                                                                                                     | WordPiece                                 | ? (BPE)                                                                |
| Laboro.AI Inc.             | --                                                                                                                                                   | Sentencepiece (without word segmentation) | Sentencepiece (model_type=unigram)                                     |
| Bandai Namco Research Inc. | MeCab (mecab-ipadic)                                                                                                                                 | WordPiece                                 | Sentencepiece (model_type=bpe)                                         |

* NICT: National Institute of Information and Communications Technology
* `without word segmentation`: 文を単語に分割せず直接サブワードへ分割する
* For models by Tohoku University, MeCab+mecab-ipadic-neologd is used for sentence segmentation (thanks [@ikuyamada](https://github.com/ikuyamada) san!)
* For models by akirakubo, documents in Aozora bunko are classified into two categories. It is based on types of kana spelling. (thanks [@kkadowa](https://github.com/kkadowa) san and [@akirakubo](https://github.com/akirakubo) san!
  * See also: https://github.com/akirakubo/bert-japanese-aozora/issues/1#issuecomment-667495267
* For DistilBERT (by Bandai Namco Resean Inc.), the same word segmentation and algorithm for constructing vocabulary are used both for teacher/studen models.


## Reference

- Google (Multilingual BERT) (2018/11): https://github.com/google-research/bert/blob/master/multilingual.md
- Kikuta (2019/01): https://yoheikikuta.github.io/bert-japanese/
- Hotto Link Inc. (2019/03): https://www.hottolink.co.jp/blog/20190311_101674/
- Kyoto University (2019/03): [http://nlp.ist.i.kyoto-u.ac.jp/bert](http://nlp.ist.i.kyoto-u.ac.jp/index.php?BERT%E6%97%A5%E6%9C%AC%E8%AA%9EPretrained%E3%83%A2%E3%83%87%E3%83%AB)
- Stockmark Inc. (2019/04): https://qiita.com/mkt3/items/3c1278339ff1bcc0187f
- Tohoku University (2019/12): https://github.com/cl-tohoku/bert-japanese
- NICT (2020/03): https://alaginrc.nict.go.jp/nict-bert/index.html
- akirakubo (2020/03): https://github.com/akirakubo/bert-japanese-aozora
- The University of Tokyo (2020/03): https://ai-health.m.u-tokyo.ac.jp/uth-ber
- Laboro.AI Inc. (2020/04): https://laboro.ai/column/laboro-bert/
- Bandai Namco Research Inc. (2020/04): https://github.com/BandaiNamcoResearchInc/DistilBERT-base-jp
