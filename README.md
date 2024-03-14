# 歩行者移動時間算出システム
　信号の制御情報を考慮し、出発地から目的地までの歩行者移動時間を算出する。

## 歩道ネットワーク
<img width="315" alt="歩道ネットワーク" src="https://github.com/Git-Yuya/pedestrian-travel-time/assets/84259422/e82e2c94-ae32-47d4-8380-0c90310a28e3">

## network.jsonファイル
　歩道ネットワークの歩道リンク情報や信号の制御情報が格納されている。
 - id：各リンクの識別番号
 - type："crosswalk"が横断歩道、"sidewalk"が歩道
 - cycle：信号の周期 [s]
 - green_duration：緑信号の継続時間 [s]
 - offset：0時（ある基準の時刻）から一番最初に緑信号に変化するまでの時間 [s]

## 動作例
　歩道ネットワークに示す出発地（左上）から目的地（右下）までのシミュレーションの動作例を示す。条件は以下の通りである。
- 出発時間：0時（ある基準の時刻）から10秒後
- 歩行速度：1.2 m/s
- 経路：[1, 3, 9, 8, 26, 41, 45, 44, 48, 59, 81, 89, 109, 112]。この経路は、ID=1を通り、ID=5を通り、・・・、ID=112を通ることを表している。 <br>
この条件の下でシミュレーションを行った結果、以下に示す出力が得られる。この結果より、出発地から目的地までの移動時間は1048.3秒かかると算出される。
```
Crosswalk 1
Arrival time: 10.0
Waiting time: 15.0
Time to start crossing: 25.0
Walking time: 12.5

Sidewalk 5
Arrival time: 37.5
Walking time: 83.33333333333334

Crosswalk 9
Arrival time: 120.83333333333334
Waiting time: 0.0
Time to start crossing: 120.83333333333334
Walking time: 15.0

Crosswalk 8
Arrival time: 135.83333333333334
Waiting time: 9.166666666666657
Time to start crossing: 145
Walking time: 13.333333333333334

Sidewalk 26
Arrival time: 158.33333333333334
Walking time: 83.33333333333334

Sidewalk 41
Arrival time: 241.66666666666669
Walking time: 250.0

Crosswalk 45
Arrival time: 491.6666666666667
Waiting time: 18.333333333333314
Time to start crossing: 510
Walking time: 18.333333333333336

Crosswalk 44
Arrival time: 528.3333333333334
Waiting time: 41.66666666666663
Time to start crossing: 570
Walking time: 16.666666666666668

Sidewalk 48
Arrival time: 586.6666666666666
Walking time: 166.66666666666669

Sidewalk 59
Arrival time: 753.3333333333333
Walking time: 125.0

Crosswalk 81
Arrival time: 878.3333333333333
Waiting time: 0.0
Time to start crossing: 878.3333333333333
Walking time: 16.666666666666668

Sidewalk 89
Arrival time: 894.9999999999999
Walking time: 125.0

Crosswalk 109
Arrival time: 1019.9999999999999
Waiting time: 0.0
Time to start crossing: 1019.9999999999999
Walking time: 20.0

Crosswalk 112
Arrival time: 1040.0
Waiting time: 5.0
Time to start crossing: 1045.0
Walking time: 13.333333333333334

Start time at starting point (ID 1): 10.0
Arrival time at destination (ID 112): 1058.3333333333333
Travel time: 1048.3333333333333
```

## 実装
- 言語：
  <img src="https://img.shields.io/badge/-Python-3776AB.svg?logo=python&style=plastic">
- 統合開発環境：
  <img src="https://img.shields.io/badge/-Colab-F9AB00.svg?logo=google%20colab&style=plastic">

## 各ファイルの説明
- system.ipynb：出発地から目的地までの歩行者移動時間を算出
- network.json：歩道ネットワーク情報を格納したファイル
- network.png：歩道ネットワーク画像
