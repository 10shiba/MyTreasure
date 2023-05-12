# Aneurysm 3D detection model

できるようになりたいこと

二次元医療画像から自動で3次元特徴量抽出及び自動3Dモデル作成ソフトウエア開発

### DICOMデータから3次元にするためのサイトやモデル．データセット

- 無料DICOM to STLサイト：
1. [https://www.embodi3d.com/democratiz3d/
2.](https://www.embodi3d.com/democratiz3d/) [https://medevel.com/invesalius-3d-dicom/](https://medevel.com/invesalius-3d-dicom/)
3. Youtube :[https://www.youtube.com/watch?v=JvTnLf8-x7U](https://www.youtube.com/watch?v=JvTnLf8-x7U)
- DICOMを含む医療画像を集めたサイトStudierfenster : [https://link.springer.com/article/10.1007/s10278-021-00574-8](https://link.springer.com/article/10.1007/s10278-021-00574-8)
この中に複数の実験解析が含まれている．
搭載機能；一般的医療スコア計算，医療画像のスライス毎の構造の主導アウトライン，医療画像データへのランドマークの手動配置，医療データのVRによる可視化，医療データの顔面再構築と登録のためのAR．CNNの頭蓋骨インプラントの設計，GANによる大動脈瘤解離の塗りつぶし，CTA画像の大動脈ランドマーク検出のためのCNN
該当サイト：[http://studierfenster.icg.tugraz.at](http://studierfenster.icg.tugraz.at/)

### 3次元を用いた自動化技術

- 3次元計測できるアプリケーションが既に搭載
- CANON : [ttps://jp.medical.canon/products/healthcareIT/advanced_visualization/neurology](https://jp.medical.canon/products/healthcareIT/advanced_visualization/neurology)
搭載機能：CT/XA脳動脈瘤の形態計測の自動化．4D脳血流解析
- EIRL : [https://www.pmda.go.jp/PmdaSearch/kikiDetail/ResultDataSetPDF/171955_30100BZX00142000_A_00_04](https://www.pmda.go.jp/PmdaSearch/kikiDetail/ResultDataSetPDF/171955_30100BZX00142000_A_00_04)
機能：脳動脈瘤の候補点を提示し，CNNモデルを使用して脳動脈瘤の類似度を計測．検査結果を出力とする．
- 自動動脈瘤検出システム：[https://pubs.rsna.org/doi/full/10.1148/radiol.2018180901](https://pubs.rsna.org/doi/full/10.1148/radiol.2018180901)
モデルはResNetを用いたモデル．ただし，入力情報が画像なのか連続した画像なのかがわからない．ResNetを用いたモデルだからおそらく2Dだと思うが．．．3Dモデルから自動検出できる方が良いのでは？評価の方法が今ひとつわからない．
- おそらく3D自動動脈瘤検出システム：h[ttps://www.ncbi.nlm.nih.gov/pmc/articles/PMC7048599/](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7048599/)

### IDEA

- おそらく2Dから3Dにすることは簡単．オンラインでも実装できるし，高速に3Dモデル化はできるはずである．一方，自分が欲しい情報だけに限定する場合に時間がかかる．またCFDの数値を取得するのに時間がかかる．
- 現状考えているのは脳動脈瘤の自動検出器と繋がっている血管検出器，過去のデータを元に保管する生成AI及びCFD解析に必要なデータ作成のALL 自動化アルゴリズムの生成．