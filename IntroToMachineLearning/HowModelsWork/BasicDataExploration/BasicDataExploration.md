### Pandas を使ってデータに慣れよう

機械学習プロジェクトの最初のステップは、
データに慣れる（理解する）こと です。

そのために Pandas ライブラリを使います。
Pandas はデータサイエンティストがデータを探索・操作するために使う主要ツールです。

多くの人は、コードで pandas を pd という短縮名で使います。
こう書きます：

```python
import pandas as pd
```

### Pandas の中心：DataFrame

Pandas の最重要構造は DataFrame（データフレーム） です。
DataFrame は、表（テーブル）形式のデータを扱う構造で、Excel のシートや SQL のテーブルに似ています。

Pandas には、この形式のデータを扱うための強力なメソッドが揃っています。

### 例：メルボルンの住宅価格データ

ここでは例として、オーストラリア・メルボルンの住宅価格データを使います。
実際の演習では、アイオワ州の住宅価格のデータセットを扱うことになります。

メルボルンのデータは、以下のファイルパスにあります：

```python
../input/melbourne-housing-snapshot/melb_data.csv
```

以下のコマンドでデータを読み込み、概観できます：

```python
# save filepath to variable for easier access
melbourne_file_path = '../input/melbourne-housing-snapshot/melb_data.csv'
# read the data and store data in DataFrame titled melbourne_data
melbourne_data = pd.read_csv(melbourne_file_path)
# print a summary of the data in Melbourne data
melbourne_data.describe()

```

### Interpreting Data Description（データ記述の読み方）

表示された結果は、元データセットの各列について 8 つの統計値 を示しています。

- count（件数）

最初の「count」は、
欠損値でない（＝値が入っている）行の数 です。

欠損値は、さまざまな理由で発生します。
たとえば、寝室が 1 つしかない家では「2 番目の寝室の面積」は計測されません。

- mean（平均）

2 つ目は 平均値（mean）。

- std（標準偏差）

std は 標準偏差。
値がどのくらい散らばっているかを表します。

### min, 25%, 50%, 75%, max の意味

列の値を「小さい順に並べた」と想像してください。

- min：最も小さい値

- 25%：下から 25%の位置（25 パーセンタイル）

- 50%：中央値（50 パーセンタイル）

- 75%：上位 25%地点（75 パーセンタイル）

max：最大値
