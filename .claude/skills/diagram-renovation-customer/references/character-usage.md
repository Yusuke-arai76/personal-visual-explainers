# 安心感の設計ガイド（お客様向け）

このスキルではキャラクターによる対話を**使わない**。お客様に配るドキュメントなので、キャラクターより「整理された情報」と「信頼感」を優先する。

代わりに以下の仕掛けで「読みやすさ」「安心感」「自己解決感」を作る。

---

## 1. リードコピー（冒頭）

最初の一文でお客様が「これは自分のための説明書だ」と感じられるかを決める。

### 書き方

```html
<div class="text-center mb-10">
  <div class="inline-flex items-center gap-2 bg-ads-accent/10 text-ads-accent-light px-4 py-1.5 rounded-full text-sm font-medium mb-5">
    <i data-lucide="home" class="w-4 h-4"></i>
    窓のリフォームをお考えの方へ
  </div>
  <h1 class="text-2xl md:text-4xl font-black text-slate-900 tracking-tight mb-4">
    国の補助金を使って<br class="md:hidden"><span class="text-ads-accent-light">お得に窓を替える方法</span>
  </h1>
  <p class="text-ads-muted max-w-xl mx-auto leading-relaxed">
    難しい申請書類は担当者がサポートします。<br>
    まずはこの3ページを読んで、制度のイメージをつかんでください。
  </p>
</div>
```

### ポイント

- 「誰向けか」を最初の一行に入れる
- 「難しくない」「一人じゃない」という安心を伝える
- 専門用語はリードコピーに一切入れない

---

## 2. 「まず3つだけ覚えてください」ブロック

お客様は情報過多になるとすぐ読むのをやめる。最初に「骨格3点」を見せて、後から肉付けする構成にする。

```html
<section class="mb-10">
  <h2 class="text-xl font-bold text-ads-text mb-4 flex items-center gap-2">
    <i data-lucide="lightbulb" class="w-6 h-6 text-ads-accent"></i>
    まず3つだけ覚えてください
  </h2>
  <div class="grid md:grid-cols-3 gap-4">
    <div class="rounded-xl border border-ads-border bg-white p-4 text-center">
      <div class="w-10 h-10 rounded-full bg-blue-100 flex items-center justify-center mx-auto mb-3">
        <span class="text-ads-accent font-black text-lg">1</span>
      </div>
      <div class="font-bold text-ads-text mb-1">対象になる工事</div>
      <p class="text-sm text-ads-muted">断熱性能の高い窓への交換。種類によって金額が変わります</p>
    </div>
    <!-- 2, 3 も同じ形 -->
  </div>
</section>
```

---

## 3. チェックリスト「わが家は対象？」

お客様が一番知りたいのは「自分の家が対象かどうか」。YES/NO チェックリストにすると自己判断できる。

```html
<section class="rounded-2xl border border-green-200 bg-green-50/60 p-5 mb-8">
  <h2 class="font-bold text-ads-text mb-4 flex items-center gap-2">
    <i data-lucide="list-checks" class="w-5 h-5 text-green-600"></i>
    わが家は対象？ 確認リスト
  </h2>
  <ul class="space-y-3">
    <li class="flex items-start gap-3">
      <div class="w-6 h-6 rounded border-2 border-green-400 flex-shrink-0 mt-0.5"></div>
      <p class="text-ads-text">日本国内の住宅（持ち家・賃貸どちらも対象の場合あり）</p>
    </li>
    <li class="flex items-start gap-3">
      <div class="w-6 h-6 rounded border-2 border-green-400 flex-shrink-0 mt-0.5"></div>
      <p class="text-ads-text">対象の断熱窓に交換する工事</p>
    </li>
    <!-- 続く -->
  </ul>
  <p class="text-xs text-ads-dim mt-4">すべてにチェックが入れば対象の可能性があります。詳しくは担当者までご相談ください。</p>
</section>
```

---

## 4. 「〇〇万円の節約イメージ」具体例ブロック

「いくら戻るか」が一番関心の高い情報。具体的な数字（仮の例でもOK）を見せると信頼度が上がる。

```html
<section class="rounded-2xl border border-ads-border bg-ads-surface p-5 mb-8">
  <h2 class="font-bold text-ads-text mb-4 flex items-center gap-2">
    <i data-lucide="calculator" class="w-5 h-5 text-ads-accent"></i>
    いくら戻る？ 計算例
  </h2>
  <div class="bg-white rounded-xl border border-ads-border p-4">
    <p class="text-sm text-ads-muted mb-3">例：6畳の部屋の窓1か所を内窓に交換した場合（仮）</p>
    <div class="space-y-2 text-sm">
      <div class="flex justify-between">
        <span class="text-ads-muted">工事費（税込）</span>
        <span class="font-bold text-ads-text">150,000円</span>
      </div>
      <div class="flex justify-between text-green-700">
        <span>補助金（例：工事費の〇〇%）</span>
        <span class="font-bold">▲ XX,000円</span>
      </div>
      <div class="border-t border-ads-border pt-2 flex justify-between text-lg">
        <span class="font-bold text-ads-text">実質負担</span>
        <span class="font-black text-ads-accent">〇〇,000円</span>
      </div>
    </div>
    <p class="text-xs text-ads-dim mt-3">※ 金額は目安です。制度の予算・条件・工事内容によって異なります。実際の見積はご相談ください。</p>
  </div>
</section>
```

---

## 5. 不安を先に解消する「よくある質問」

お客様の不安（怪しい・難しい・損するかも）を FAQ 形式で先に解消する。

```html
<section class="mb-8">
  <h2 class="text-lg font-bold text-ads-text mb-4 flex items-center gap-2">
    <i data-lucide="help-circle" class="w-5 h-5 text-ads-accent"></i>
    よくあるご質問
  </h2>
  <div class="space-y-3">
    <details class="rounded-xl border border-ads-border bg-white p-4 cursor-pointer">
      <summary class="font-bold text-ads-text">本当に国の制度ですか？詐欺ではないですか？</summary>
      <p class="mt-3 text-sm text-ads-muted">
        はい、〇〇省が実施する公式の事業です。詳細は公式サイト（リンク）でご確認いただけます。
      </p>
    </details>
    <details class="rounded-xl border border-ads-border bg-white p-4 cursor-pointer">
      <summary class="font-bold text-ads-text">手続きは自分でやらないといけませんか？</summary>
      <p class="mt-3 text-sm text-ads-muted">
        書類の多くは担当者がサポートします。お客様にご用意いただくものは〇〇だけです。
      </p>
    </details>
  </div>
</section>
```

---

## 6. クロージング（読後のアクション）

読み終わったお客様が「次に何をするか」を1行で示す。

```html
<section class="rounded-2xl bg-gradient-to-br from-ads-accent/10 to-blue-50 border border-ads-accent/20 p-6 text-center mb-8">
  <i data-lucide="phone-call" class="w-8 h-8 text-ads-accent mx-auto mb-3"></i>
  <h2 class="text-xl font-bold text-ads-text mb-2">まずは無料相談から</h2>
  <p class="text-ads-muted text-sm">「補助金の使える工事か確認したい」だけでもOKです。担当者がお答えします。</p>
</section>
```

---

## 配置ルール

1. **安心要素は前半に**: チェックリスト・FAQ は「金額説明」より前に置く
2. **数字は大きく**: 金額・割合はひと目でわかるサイズで表示
3. **注釈はこまめに**: 断定は避け「〇年〇月時点」「目安です」を必ず添える
4. **相談導線は最後に**: 読み終わったお客様が迷わず次の行動に進めるよう締める
