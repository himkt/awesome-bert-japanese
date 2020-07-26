# awesome-bert-japanese


|      | モデル           | 文 -> 単語     | 単語 -> サブワード           | サブワード分割のための語彙構築アルゴリズム     |
| ---: | :--------------- | :------------- | :--------------------------- | :--------------------------------------------- |
| 0    | 多言語 BERT      | Whitespace     | WordPiece                    | BPE?                                           |
| 1    | Kikuta           | --             | Sentencepiece (文から直接)   | Sentencepiece                                  |
| 2    | ストックマーク   | MeCab          | --                           | --                                             |
| 3    | 京都大学         | Juman++        | WordPiece                    | BPE                                            |
| 4    | 東北大学 (a)     | MeCab          | WordPiece                    | BPE                                            |
| 5    | 東北大学 (b)     | MeCab          | WordPiece                    | Character                                      |
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
