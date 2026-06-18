# UGS DISC診断ツール

公開URL: **https://ugs-disc.github.io/**

PC・スマホのブラウザで開ける単一HTMLの診断ツール。強制選択24問 →
D/I/S/C集計 → 2文字タイプ（例：DC）判定 → 結果レポート → PDF保存。

## ファイル
- `index.html` … 診断ツール本体（これ1つで完結）

## 更新のしかた（3ステップ）
1. `index.html` を編集（設問・配点・デザインなど）
2. 下記を実行してpush
   ```
   cd /Users/koba/Desktop/UGS/ugs-disc
   git add index.html
   git commit -m "更新内容を書く"
   git push
   ```
3. **1〜2分で公開URLに自動反映**。ブラウザは強制リロード（⌘+Shift+R）で確認

## ローカル原本
`/Users/koba/Desktop/UGS/disc_tool/disc_診断.html` が同一内容の作業用コピー。
※今後はこの `index.html` を「正」として編集すると二重管理にならない。

## 採点ロジック
- 各問：最も適している＝該当タイプ +1 ／ 最も遠い＝ −1
- D/I/S/C合計 → 1位＝主タイプ、2位＝副タイプ → 2文字で表示

## PDF出力
- jsPDF + html2canvas（CDN読込）でファイルとして保存
- オフライン時は自動で印刷ダイアログにフォールバック

## ホスティング
- GitHub Pages（このリポジトリ・public）。`main` ブランチの直下を配信
- 公開停止したい場合：リポジトリ Settings → Pages を無効化、またはリポジトリをprivate化
