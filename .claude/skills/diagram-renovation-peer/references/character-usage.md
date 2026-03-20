# 対話キャラクター利用ガイド（画像なし）

このスキルでは **本気AIのキャラクター画像は使わない**。`creating-visual-explainers` の `base.html` に合わせ、**Lucide アイコン＋吹き出し**で登場人物を表す。

## 役割定義

| 役 | 読者像 | 役割 |
|----|--------|------|
| **仲間（読者代弁）** | ADS受講生。リフォーム・行政手続きは素人 | 素朴な疑問・不安・言い換え要求を出す |
| **営業の解説役** | 作者と同じく、窓・ドアリフォームの営業視点が強い | 現場で使う言い方、お客様への順序、注意点を短く示す |

## ビジュアル（推奨）

- **仲間**: `graduation-cap` または `user` を円形背景（例: `bg-ads-surface`）に配置
- **解説役**: `briefcase` または `message-circle` を円形背景（例: `bg-blue-50`）に配置

吹き出しの色分けは diagram-maji に倣い、**読者側＝暖色寄り**、**解説側＝寒色寄り**とすると一覧で区別しやすい。

## 対話パターン例

### 導入（「何の話か」を業界外語で聞く）

```html
<div class="flex items-start gap-3 mb-6">
  <div class="w-11 h-11 rounded-full bg-amber-50 border border-amber-200 flex items-center justify-center flex-shrink-0">
    <i data-lucide="graduation-cap" class="w-5 h-5 text-amber-700"></i>
  </div>
  <div class="flex-1 rounded-2xl border-2 border-amber-200 bg-gradient-to-br from-amber-50 to-yellow-50 px-4 py-3">
    <p class="text-sm font-bold text-amber-900 mb-1">仲間</p>
    <p class="text-ads-text">「補助金」と「助成金」、同じような気もするんですが、営業の現場ではどう切り分けて話しますか？</p>
  </div>
</div>

<div class="flex items-start gap-3 mb-6">
  <div class="w-11 h-11 rounded-full bg-blue-50 border border-blue-200 flex items-center justify-center flex-shrink-0">
    <i data-lucide="briefcase" class="w-5 h-5 text-blue-700"></i>
  </div>
  <div class="flex-1 rounded-2xl border-2 border-blue-200 bg-gradient-to-br from-sky-50 to-blue-50 px-4 py-3">
    <p class="text-sm font-bold text-blue-900 mb-1">営業の解説役</p>
    <p class="text-ads-text">お客様にはまず<strong>「誰が払うお金か」</strong>で話すと誤解が減ります。今日の図解では、行政の制度は〇〇、お客様負担は△△、という流れで整理しますね。</p>
  </div>
</div>
```

### 中盤（条件・期限でつまずく）

```html
<div class="flex items-start gap-3 mb-6">
  <div class="w-11 h-11 rounded-full bg-amber-50 border border-amber-200 flex items-center justify-center flex-shrink-0">
    <i data-lucide="graduation-cap" class="w-5 h-5 text-amber-700"></i>
  </div>
  <div class="flex-1 rounded-2xl border-2 border-amber-200 bg-gradient-to-br from-amber-50 to-yellow-50 px-4 py-3">
    <p class="text-sm font-bold text-amber-900 mb-1">仲間</p>
    <p class="text-ads-text">「対象工事」って書いてあるけど、窓だけ替えた場合も入りますか？</p>
  </div>
</div>
```

### まとめ（お客様説明用の一文）

```html
<div class="flex items-start gap-3 mb-6">
  <div class="w-11 h-11 rounded-full bg-blue-50 border border-blue-200 flex items-center justify-center flex-shrink-0">
    <i data-lucide="briefcase" class="w-5 h-5 text-blue-700"></i>
  </div>
  <div class="flex-1 rounded-2xl border-2 border-blue-200 bg-gradient-to-br from-sky-50 to-blue-50 px-4 py-3">
    <p class="text-sm font-bold text-blue-900 mb-1">営業の解説役</p>
    <p class="text-ads-text">お客様には最後にこう締めます。「今日お伝えしたのは<strong>3つだけ</strong>覚えてください」と言って、図の番号に沿って読み上げられるようにしておきましょう。</p>
  </div>
</div>
```

## セリフの書き方

### 仲間

- 丁寧語。知ったかぶりしない。**具体的な場面**（見積もり、電話、展示場）を入れると良い
- 「公式サイトにはこう書いてあるけど、現場だとどう？」が強い

### 営業の解説役

- 断定は**出典付きの範囲**で。微妙なときは「会社の方針で」「自治体によって」と明示
- **お客様にそのまま使える短い言い回し**を1つ以上入れる

## 配置ルール

1. 対話は**上から順**（左右固定しない）
2. アイコンサイズは `w-11 h-11` 前後で統一
3. セクションが長いときは、**対話を挟んで呼吸**を作る
