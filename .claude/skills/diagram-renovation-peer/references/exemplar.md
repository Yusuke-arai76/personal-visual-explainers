# 模範パターン（リフォーム × ADS仲間向け）

`creating-visual-explainers/references/model-answer.html` が**デザインの模範**になる。ここでは **diagram-maji の「成功構造」**を、本スキルの文脈に置き換えたチェックリストとミニ例をまとめる。

## 成功する図解の構造

```
1. タイトル・説明（base.html のプレースホルダー）
2. リード（読者・ゴール宣言：お客様に説明できるまで）
3. 導入対話（仲間 × 営業の解説役）
4. 全体の地図（今日のテーマの位置づけ）
5. お客様説明で最初に言う3つ（必須 / 要確認 / 次に話す、などバッジ付きでも可）
6. 詳細セクション（カード + Lucide + 箇条書き）
   - 助成金・制度なら：タイムライン + 条件分岐図を必ず検討
7. 出典・要確認（一次情報URL）
8. まとめ対話
9. お客様説明用クロージング（1分スクリプト or チェックリスト）
```

---

## 「お客様説明で最初に言う3つ」の例

```html
<section class="mb-10">
  <div class="flex items-center gap-3 mb-4">
    <div class="w-10 h-10 rounded-xl bg-blue-50 flex items-center justify-center">
      <i data-lucide="star" class="w-5 h-5 text-ads-accent"></i>
    </div>
    <h2 class="text-xl font-bold text-ads-text">お客様説明で最初に言う3つ</h2>
  </div>
  <div class="space-y-3">
    <div class="rounded-xl border-l-4 border-ads-accent bg-ads-surface p-4 border border-ads-border">
      <div class="flex items-center gap-2 mb-1">
        <span class="text-sm font-bold text-ads-accent">1</span>
        <span class="font-bold text-ads-text">制度の「対象」は窓の種類だけで決まらない</span>
      </div>
      <p class="text-sm text-ads-muted">性能・工事内容・申請タイミングがセット。一次情報のチェックリストを見せながら話す。</p>
    </div>
    <div class="rounded-xl border-l-4 border-blue-300 bg-ads-surface p-4 border border-ads-border">
      <div class="flex items-center gap-2 mb-1">
        <span class="text-sm font-bold text-blue-600">2</span>
        <span class="font-bold text-ads-text">いつまでに何をするか（カレンダーで共有）</span>
      </div>
      <p class="text-sm text-ads-muted">「申請が先 / 工事が先」は制度で逆転するので、図の番号で追う。</p>
    </div>
    <div class="rounded-xl border-l-4 border-slate-300 bg-ads-surface p-4 border border-ads-border">
      <div class="flex items-center gap-2 mb-1">
        <span class="text-sm font-bold text-slate-600">3</span>
        <span class="font-bold text-ads-text">確定は担当窓口・公式のお知らせ</span>
      </div>
      <p class="text-sm text-ads-muted">図解は理解のため。金額・枠・締切は都度確認と断る。</p>
    </div>
  </div>
</section>
```

---

## 助成金パートで強い「制度の地図」

文章の羅列をやめ、**役者（誰が）**と**順番（いつ）**を図にする。

- **役者**: 国 / 都道府県 / 市区町村 / 事業者 / お客様 — 制度に合わせて省略可
- **順番**: 相談 → 見積 → 申請承認 → 契約 → 工事 → 報告・入金 など
- **分岐**: 「対象外になりやすい条件」を別色ボックスにまとめる

---

## 品質チェックリスト（作成後）

### 内容

- [ ] 専門語・行政語に用語解説（初出）
- [ ] たとえが3つ以上
- [ ] 導入・中間・まとめに対話
- [ ] 「お客様説明で最初に言う3つ」または同等の絞り込み
- [ ] 読者が**1分で第三者に説明できる**締め（スクリプト or チェックリスト）
- [ ] 制度・数値・期限に**出典**（ない場合は「要確認」と明記）

### デザイン・技術

- [ ] Lucide のみ（絵文字なし）
- [ ] `base.html` の ADS トーンに沿う
- [ ] スマホで縦読みしやすい（横スクロールは表だけに留める）

### 営業実務

- [ ] 誤解されやすい点（対象外・上乗せ条件）を**明示**
- [ ] 断定的な約束（必ずもらえる、必ず間に合う等）を避けている

---

## diagram-maji との対応表

| diagram-maji | 本スキル（diagram-renovation-peer） |
|--------------|-------------------------------------|
| マジくん・マスター | 仲間（ADS）・営業の解説役（アイコン吹き出し） |
| 本気AIブランドカラー | ADS 配色（`base.html`） |
| 技術用語辞書 | 建具・工事・行政語辞書＋お客様向け言い換え |
| コード前の日本語解説 | フォーム・条文・数値の「何を見せているか」 |
| surge デプロイ | `creating-visual-explainers/scripts/deploy-diagram.sh` |
