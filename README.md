# Pythonによる実験計画法 - Design_of_Experiment(DoE) with Python in Jupyter Notebook
今回は、下記をPython + Jupyter notebookで実装しました。
- 2水準系の直交表を用いた実験計画の作成
- 上記実験結果の解析


# 使用言語とライブラリ - Dependency
<!-- 使用言語とバージョン、必要なライブラリとそのバージョンを書く
Pythonならrequirements.txtを用意するのも良い -->
- Python  :  3.6.5
- pandas  :  0.23.0
- openpyxl  :  2.5.3
- matplotlib :  2.2.2
- scipy :  1.1.0

# 準備 - Setup
<!-- セットアップ方法を書く。用意するハードウェアとソフトウェアをセットアップするためのコマンドを記載する -->
上記Python関連とJupyter Notebookの環境が必要です。  
それらを一括でインストールするにはAnacondaが便利です。  
[Anacondaの説明やインストール方法(参考リンク)](https://knowledge.sakura.ad.jp/17235/ "Anaconda参考リンク")

# 使用方法 - Usage
<!-- 使い方。なるべく具体的に書く。サンプルも書く -->
## Automatic assignment to 2-level orthogonal table + creation of experiment plan
<!-- このソフトはどんなもので、何ができるのかを書く
合わせて、簡単なデモ（使用例）などスクリーンショットやGIFアニメで表示 -->
- create_expt_plan_2_levels.ipynb
- 2水準直交表への因子と交互作用の割付(わりつけ)を行います。
- 割付後の表を実験計画としてEXCELに出力します。 

●パラメータの例
美味しいカレーに影響を与えるパラメータを調べたいとします。
- 煮込み時間：20 / 60 min
- 小麦粉割合：5 / 10 %
- カレー粉種類：横須賀海軍 / バーモント  

これを下記のように入力します。  

```python3
# 因子の名前
factor_symbols_all = ["時間", "小麦", "カレー粉"]

# 各因子の水準
factors = [
    [20,60],
    [5,10],
    ["海軍","BMT"]
]

# 見たい交互作用を因子の番号(o～)で指定。
interactions = [
#     [0, 1],    # AxB
#     [1, 2]     # BxC
]
```
実行すると、下記のような実験計画表とEXCELが出力されます。  
![実験計画]('sample-table.png')


## Analysis the result 2-level orthogonal table
<!-- このソフトはどんなもので、何ができるのかを書く
合わせて、簡単なデモ（使用例）などスクリーンショットやGIFアニメで表示 -->
- analysis_expt_result_2_levels.ipynb
- 前回作成した2水準系直交表を用いた実験後の結果データを用いて、  
因子と交互作用の効果を可視化・分析・推定します。 

# ライセンス - License
<!-- This software is released under the MIT License, see LICENSE. -->

Released under the [MIT license](https://opensource.org/licenses/mit-license.php "MIT Lisense")

# 著者 - Authors
<!-- 作者を明示する。特に、他者が作成したコードを利用する場合は、そのコードのライセンスに従った上で、リポジトリのそれぞれのコードのオリジナルの作者が誰か分かるように明示する（私はそれが良いと思い自主的にしています）。 -->
Copyright (c) 2019 Shintaro Yawata

# 参考 - References
参考にした情報源（サイト・論文）などの情報、リンク

http://jasst.jp/archives/jasst05w/pdf/S4-1.pdf  
https://www.slideshare.net/hajimemizuyama/par-49440366
