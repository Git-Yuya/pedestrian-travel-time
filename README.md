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

## 実装
- 言語：
  <img src="https://img.shields.io/badge/-Python-3776AB.svg?logo=python&style=plastic">
- 統合開発環境：
  <img src="https://img.shields.io/badge/-Colab-F9AB00.svg?logo=google%20colab&style=plastic">

## 各ファイルの説明
- system.ipynb：出発地から目的地までの歩行者移動時間を算出
- network.json：歩道ネットワーク情報を格納したファイル
- network.png：歩道ネットワーク画像
