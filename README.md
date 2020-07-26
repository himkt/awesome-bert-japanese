# awesome-bert-japanese

日本語の学習済み BERT は文から単語への分かち書き，単語からサブワードへの分割の処理にいくつかの選択肢が存在します．
また，単語をサブワードに分割する際に利用する語彙についても構築方法に数種類のバリエーションがあります．
本リポジトリでは，公開されている学習済み BERT モデルについて，
分かち書き・サブワード分割・語彙構築アルゴリズムそれぞれどのアルゴリズムが採用されているかを表にまとめています．


## モデル


|      | モデル           | 文 -> 単語     | 単語 -> サブワード           | サブワード分割のための語彙構築アルゴリズム     |
| ---: | :--------------- | :------------- | :--------------------------- | :--------------------------------------------- |
| 0    | 多言語 BERT      | Whitespace     | WordPiece                    | BPE?                                           |
| 1    | Kikuta           | --             | Sentencepiece (文から直接)   | Sentencepiece                                  |
| 2    | ストックマーク   | MeCab          | --                           | --                                             |
| 3    | 京都大学         | Juman++        | WordPiece                    | BPE                                            |
| 4    | 東北大学 (a)     | MeCab          | WordPiece                    | Sentencepiece (model_type=bpe)                 |
| 5    | 東北大学 (b)     | MeCab          | Character                    | Sentencepiece (model_type=character)           |
| 6    | ホットリンク     | --             | Sentencepiece (文から直接)   | Sentencepiece                                  |
| 7    | NICT (a)         | MeCab          | WordPiece?                   | BPE                                            |
| 8    | NICT (b)         | MeCab          | WordPiece?                   | Character                                      |
| 9    | 東京大学         | MeCab          | WordPiece                    | BPE                                            |



## リンク

- 多言語 BERT: https://github.com/google-research/bert/blob/master/multilingual.md
- Kikuta: https://yoheikikuta.github.io/bert-japanese/
- ストックマーク: https://qiita.com/mkt3/items/3c1278339ff1bcc0187f
- ホットリンク: https://www.hottolink.co.jp/blog/20190311_101674/
- 京都大学: https://www.anlp.jp/proceedings/annual_meeting/2019/pdf_dir/F2-4.pdf
- 東北大学: https://github.com/cl-tohoku/bert-japanese
- NICT: https://alaginrc.nict.go.jp/nict-bert/index.html
- 東京大学: https://ai-health.m.u-tokyo.ac.jp/uth-ber
