# 模範パターン（お客様向け補助金説明書）

`creating-visual-explainers/references/model-answer.html` が**デザインの模範**。ここでは本スキル固有の「成功構造」とミニ例をまとめる。

## 成功する図解の構造

```
1. タイトル・説明（base.html プレースホルダー）
2. リードコピー
   └─ 「誰向けか」「難しくない」「一人じゃない」を一文で
3. まず3つだけ（骨格情報カード×3）
   └─ ① 対象になる工事  ② いくら戻るか  ③ 何をすればいいか
4. わが家は対象？チェックリスト
   └─ YES/NO 形式で自己判断できる
5. 手続きの流れ（番号付きフロー図）
   └─ 申し込み → 承認待ち → 工事 → 完了報告 → 入金
6. 金額の計算例（具体数値）
   └─ 工事費 → 補助額 → 実質負担の3行
7. よくある質問（アコーディオン）
   └─ 「怪しくない？」「手続きは難しい？」を先に潰す
8. 出典・確認先（公式URL・日付）
9. クロージング（相談導線）
```

---

## 「まず3つだけ」の例（カード形式）

```html
<section class="mb-10">
  <h2 class="text-xl font-bold text-ads-text mb-4 flex items-center gap-2">
    <i data-lucide="lightbulb" class="w-6 h-6 text-ads-accent"></i>
    まず3つだけ覚えてください
  </h2>
  <div class="grid md:grid-cols-3 gap-4">
    <div class="rounded-xl border border-ads-border bg-white p-5 text-center">
      <div class="w-10 h-10 rounded-full bg-blue-100 flex items-center justify-center mx-auto mb-3">
        <span class="text-ads-accent font-black text-lg">1</span>
      </div>
      <i data-lucide="home" class="w-6 h-6 text-ads-accent mx-auto mb-2"></i>
      <div class="font-bold text-ads-text mb-1">対象の工事</div>
      <p class="text-sm text-ads-muted">断熱性能の高い窓への交換。種類によって受け取れる金額が変わります</p>
    </div>
    <div class="rounded-xl border border-ads-border bg-white p-5 text-center">
      <div class="w-10 h-10 rounded-full bg-blue-100 flex items-center justify-center mx-auto mb-3">
        <span class="text-ads-accent font-black text-lg">2</span>
      </div>
      <i data-lucide="banknote" class="w-6 h-6 text-ads-accent mx-auto mb-2"></i>
      <div class="font-bold text-ads-text mb-1">工事費の一部が戻る</div>
      <p class="text-sm text-ads-muted">国が費用を肩代わりしてくれます。最大〇〇万円まで（〇年〇月時点）</p>
    </div>
    <div class="rounded-xl border border-ads-border bg-white p-5 text-center">
      <div class="w-10 h-10 rounded-full bg-blue-100 flex items-center justify-center mx-auto mb-3">
        <span class="text-ads-accent font-black text-lg">3</span>
      </div>
      <i data-lucide="clipboard-list" class="w-6 h-6 text-ads-accent mx-auto mb-2"></i>
      <div class="font-bold text-ads-text mb-1">手続きはサポート付き</div>
      <p class="text-sm text-ads-muted">難しい申請書類は担当者が一緒に進めます。ご自身でやることは最小限です</p>
    </div>
  </div>
</section>
```

---

## diagram-peer（仲間向け）との対応表

前回作った `diagram-renovation-peer` との違いを整理しておく。

| 観点 | diagram-renovation-peer（仲間向け） | diagram-renovation-customer（お客様向け） |
|------|--------------------------------------|------------------------------------------|
| 読者 | ADSスクールの仲間。業界未経験 | 一般のお客様。補助金の知識ゼロ |
| ゴール | 自分がお客様に説明できるようになる | 読んだ人が自分で理解・納得できる |
| トーン | 仲間内の解説 + 「営業で使える言い回し」 | お客様への丁寧な説明書 |
| 対話 | 仲間 × 営業の解説役 | **対話なし**。整理された情報 + FAQ |
| 金額 | 大まかな制度の枠組み | **具体数値の計算例**（必須） |
| 印刷 | 参考資料 | **A4印刷・PDF配布を想定**（必須） |
| 安心感 | 出典URLを添える | **「怪しくない」FAQ + 公式URL**（必須） |
| 相談導線 | なし | **クロージング必須**（担当への連絡先へ誘導） |

---

## 品質チェックリスト（作成後）

### 内容

- [ ] 行政語・業界語がすべてお客様語に変換されている
- [ ] 「わが家は対象か」チェックリストがある
- [ ] 具体的な金額（計算例）が入っている
- [ ] 手続きの流れがステップ番号付きフローで示されている
- [ ] FAQ に「怪しくない？」「難しい？」の回答がある
- [ ] 公式URL と情報の日付が明記されている
- [ ] 最後に「次にすべきこと」が一文で書かれている

### デザイン・実用性

- [ ] Lucide のみ（絵文字なし）
- [ ] ADS 配色（`base.html` に沿う）
- [ ] A4 印刷・PDF で崩れない
- [ ] スマホで縦読みしやすい

### 営業コンプライアンス

- [ ] 断定的な表現（「必ず」「誰でも」）がない
- [ ] 金額・期限の変動について「〇月時点」「要確認」を添えている
