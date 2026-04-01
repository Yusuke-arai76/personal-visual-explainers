# HTML構造ガイド（お客様向け配布資料）

## 基本方針

- 構造・CDN・フッターは `.claude/skills/creating-visual-explainers/references/base.html` に従う
- **印刷・PDF配布を想定**したレイアウトにする（A4縦で崩れない）
- お客様が「読む・保存する・人に見せる」ことを前提にデザインする

## プレースホルダー

| プレースホルダー | 記入内容 |
|------------------|----------|
| `<!-- TITLE -->` | 制度名と「わかりやすく解説」など（例: 先進的窓リノベ事業ガイド） |
| `<!-- DESCRIPTION -->` | 「〇〇の補助金をお客様向けにわかりやすく解説した図解です」 |
| `<!-- CONTENT_START -->` 〜 `<!-- CONTENT_END -->` | 図解本体 |

## 配色（ADS Tailwind）

`base.html` に定義済みのものを使う:

```
text-ads-text（本文）/ text-ads-muted（補足）/ text-ads-dim（注釈）
bg-ads-surface（薄グレー背景）/ border-ads-border（枠線）
text-ads-accent / bg-ads-accent（青：強調・ボタン）
text-ads-positive（緑）/ text-ads-negative（赤）/ text-ads-warning（オレンジ）
```

## 推奨セクション順（本文）

1. **リードコピー**: 「誰向けか」「難しくない」を一言で
2. **まず3つだけ**: 骨格情報（対象・金額・流れ）
3. **わが家は対象？チェックリスト**: YES/NO で自己判断
4. **手続きの流れ（フロー図）**: ステップ番号付きで視覚化
5. **金額の計算例**: 具体的な数字で「得するイメージ」
6. **よくある質問（FAQ）**: 不安・疑問を先に解消
7. **出典・確認先**: 公式URL・「〇年〇月時点」
8. **クロージング（相談導線）**: 次のアクションを1行で

## フロー図（ステップ番号つき）

お客様は手続きの順番を知りたい。番号とアイコンで「今どの段階か」が見えるようにする。

```html
<div class="flex flex-col md:flex-row items-stretch md:items-center justify-center gap-3 my-8">
  <!-- ステップ1 -->
  <div class="rounded-xl border-2 border-ads-accent/40 bg-white px-4 py-4 text-center flex-1">
    <div class="w-8 h-8 rounded-full bg-ads-accent text-white flex items-center justify-center font-black text-sm mx-auto mb-2">1</div>
    <i data-lucide="file-text" class="w-5 h-5 text-ads-accent mx-auto mb-1"></i>
    <div class="text-sm font-bold text-ads-text">申し込み</div>
    <div class="text-xs text-ads-muted mt-1">工事前に手続き</div>
  </div>
  <i data-lucide="arrow-right" class="w-5 h-5 text-ads-dim hidden md:block flex-shrink-0"></i>
  <i data-lucide="arrow-down" class="w-5 h-5 text-ads-dim md:hidden mx-auto"></i>
  <!-- ステップ2 以降同じ形 -->
</div>
```

## チェックリスト（対象判定）

```html
<ul class="space-y-3">
  <li class="flex items-start gap-3">
    <div class="w-6 h-6 rounded border-2 border-green-400 flex-shrink-0 mt-0.5 bg-white"></div>
    <p class="text-ads-text">条件の説明（やさしい言葉で）</p>
  </li>
</ul>
```

## 計算例テーブル

```html
<div class="bg-white rounded-xl border border-ads-border p-4">
  <div class="space-y-2 text-sm">
    <div class="flex justify-between border-b border-ads-border pb-2">
      <span class="text-ads-muted">工事費（税込）</span>
      <span class="font-bold text-ads-text">150,000円</span>
    </div>
    <div class="flex justify-between text-green-700">
      <span>補助金（工事費の〇%）</span>
      <span class="font-bold">▲ XX,000円</span>
    </div>
    <div class="flex justify-between text-lg pt-2">
      <span class="font-bold text-ads-text">実質負担</span>
      <span class="font-black text-ads-accent">〇〇,000円</span>
    </div>
  </div>
</div>
```

## FAQ アコーディオン

```html
<details class="rounded-xl border border-ads-border bg-white p-4 cursor-pointer group">
  <summary class="font-bold text-ads-text list-none flex items-center justify-between">
    質問文
    <i data-lucide="chevron-down" class="w-4 h-4 text-ads-dim"></i>
  </summary>
  <p class="mt-3 text-sm text-ads-muted leading-relaxed">回答文</p>
</details>
```

## 出典ブロック

制度の信頼性を担保する。リンク付きで目立つ場所に置く。

```html
<section class="rounded-xl border border-ads-border bg-ads-surface p-4 mb-6">
  <div class="flex items-start gap-3">
    <i data-lucide="external-link" class="w-5 h-5 text-ads-accent flex-shrink-0 mt-0.5"></i>
    <div>
      <p class="text-sm font-bold text-ads-text mb-1">出典・最新情報の確認先</p>
      <p class="text-xs text-ads-muted mb-1">この説明書の情報は〇〇年〇月時点のものです。変更になる場合があります。</p>
      <a href="https://..." class="text-xs text-ads-accent underline break-all">公式サイト URL</a>
    </div>
  </div>
</section>
```

## 印刷対応の注意点

- `max-w-3xl` の中に収める（`base.html` デフォルト）
- `overflow-x-auto` のある横スクロールテーブルは**印刷で切れる**ので、テーブルはシンプルに
- 色は印刷されない場合も考慮して、**枠線・太字**でも区別がつくようにする
- `base.html` の PDF ボタンは自動で印刷ダイアログを開く
