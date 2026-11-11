# GPS のずれの見積もり（試作）

国土交通省の 3D 都市モデル PLATEAU の建物の形と衛星の軌道から、ビルの多い街でスマホの GPS（衛星測位）の位置がずれやすい場所と時刻を前もって見積もる Web アプリの試作です。計算は全部あなたの閲覧器の中で行います。押した点の座標を送る先はありません（地図と建物の区画は、表示している範囲の分を公開の配信から取ります）。

- 開く: https://driedsandwich.github.io/plateau-gnss-sky-risk/
- 見積もりです。実測ではありません（建物は箱の形・反射の波〈マルチパス〉・木・大気は数えていない）。
- 画面は、推奨の見本（空を隠す建物）で仮に組んだ試作です。見た目はまだ変わります。

## 使い方

1. 地図を 1 回押します（押しても料金はかかりません）。
2. 押した点で見える衛星の数、位置のずれやすさ（HDOP）、空の見え方の円い図が出ます。
3. 周りの格子の色と「ずれにくい」候補の点も出ます。時刻を変えると変わります。

## 出典とデータ

- 出典：国土交通省 PLATEAU（3D 都市モデル・建築物 LOD1）を加工して作成。利用条件は PLATEAU サイトポリシー（公共データ利用規約 第1.0版・CC BY 4.0 と互換）。
- 地図：地理院タイル（淡色地図・標高タイル）。ジオイド高は国土地理院のジオイド高計算による値を同梱。
- 衛星の軌道：CelesTrak の GP データ（2026-11-09 に取った写しを同梱・選んだ時は新しく取る）。
- 閲覧器が直に取りに行く先：api.plateau.reearth.io・assets.cms.plateau.reearth.io・api.plateauview.mlit.go.jp・cyberjapandata.gsi.go.jp・celestrak.org（選んだ時だけ）。

## AI から使う

AI やエージェント向けの説明は [llms.txt](llms.txt) にあります。

## ライセンス

- このアプリ：MIT（[LICENSE](LICENSE)）。
- 同梱の外の部品：CesiumJS（Apache-2.0）・draco3d（Apache-2.0）・satellite.js（MIT）・字体 Noto Sans JP（SIL Open Font License 1.1）。許諾の文は [THIRD_PARTY_NOTICES](THIRD_PARTY_NOTICES/) にあります。
