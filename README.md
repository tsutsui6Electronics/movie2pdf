# kindle2img

このプログラムはkindleのデータをローカルに保存するために作成したプログラムです。

# kindleをキャプチャーしても...
kindleをキャプチャーした動画データは静止画の集合のように見えますが、実際は1枚1枚微妙にチャネルの値が変わっています。
したがって同じ見た目でも単純な画像処理では完全に重複なしで各コマを取得することはできません。


そのためこのプログラムは微妙な違いをOpenCVを用いた画像処理で取り除くことで、重複がない画像データに変換します。

# 注意
このプログラムは計算コストを考慮し、動画の各コマの画像領域を1部カットして処理を行います。
しかし現在、画像のカットする領域はマニュアルで修正する必要があります。
したがって、デフォルト値で生成画像の端が切れるようでしたら、ソースコードの以下の部分を適切な値に変更して調整してください。
```frame=frame[90:956,510:1460]```

# 使用方法

保存したい作品の全ページをOBSなどでキャプチャーしmp4形式に保存します。
そしてコマンドラインから以下の形式でプログラムを実行します。
引数には動画データと出力フォルダ名を与えます。
```python kindle2img.py キャプチャ動画 (出力フォルダ名)```


出力フォルダ内に各コマの画像が出力されます。
作成者は複数の動画を使って出力結果を確認していますが、動画の状況によっては重複コマが発生してしまうことも考えられます。

-------------------------------
作成者は当プログラムの利用に関して一切の責任を負いかねます。
