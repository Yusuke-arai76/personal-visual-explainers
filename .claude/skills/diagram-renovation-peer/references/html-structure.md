# HTML構造ガイド（ADS 額縁 + リフォーム図解）

## 基本方針

- **単一のソースオブトゥルース**: ドキュメント構造・CDN・フッターは `.claude/skills/creating-visual-explainers/references/base.html` に従う
- 作業手順: `base.html` を `output/{スラッグ}.html` にコピーし、プレースホルダーのみ差し替える（`creating-visual-explainers` の Step 5 と同じ）
- **本文（`CONTENT` 内）**だけを、このガイドと [exemplar.md](exemplar.md) のパターンで組み立てる

## プレースホルダー

| プレースホルダー | 内容 |
|------------------|------|
| `<!-- TITLE -->` | 図解タイトル（検索・SNSで意味が通じる文） |
| `<!-- DESCRIPTION -->` | 1文サマリ（誰向けか含めると良い） |
| `<!-- CONTENT_START -->` 〜 `<!-- CONTENT_END -->` | 図解本体 |

## Tailwind 配色（ADS）

`base.html` で既に `tailwind.config` が定義済み。本文では主に以下を使う:

- テキスト: `text-ads-text`, `text-ads-muted`, `text-ads-dim`
- 背景: `bg-ads-bg`, `bg-ads-surface`, `border-ads-border`
- アクセント: `text-ads-accent`, `bg-blue-50`, `border-ads-accent`

## Lucide Icons

`base.html` 終盤で `lucide.createIcons()` が呼ばれる。本文では:

```html
<i data-lucide="home" class="w-5 h-5 text-ads-accent"></i>
```

### リフォーム・制度向けに使いやすいアイコン

| 用途 | アイコン名 |
|------|------------|
| 住まい | `home`, `door-open`, `layout-template` |
| お金・制度 | `landmark`, `banknote`, `percent`, `file-check` |
| カレンダー・期限 | `calendar`, `clock` |
| チェックリスト | `list-checks`, `check-circle` |
| 注意 | `triangle-alert`, `info` |
| フロー | `arrow-right`, `arrow-down`, `git-branch`（分岐の比喩） |

**絵文字は使わない。**

## 推奨セクション順（本文）

1. **リード**: 誰向けか・読了後にできるようになること（お客様説明）
2. **導入対話**（仲間 × 営業の解説役）→ [character-usage.md](character-usage.md)
3. **全体の地図**: 1図で「今日の話の位置」
4. **お客様説明で最初に言う3つ**
5. **詳細セクション**（カード + 小見出し + 箇条書き + 必要ならフロー）
6. **助成金・制度がある場合**: タイムライン（申請〜工事〜入金など）と**条件分岐**の図
7. **出典・要確認**（リンク付き）
8. **まとめ対話** + **お客様に渡す一言（またはチェックリスト）**

## フロー・タイムライン例

```html
<div class="flex flex-col md:flex-row items-stretch md:items-center justify-center gap-3 my-8">
  <div class="rounded-xl border border-ads-border bg-ads-surface px-4 py-3 text-center flex-1">
    <i data-lucide="file-text" class="w-6 h-6 text-ads-accent mx-auto mb-1"></i>
    <div class="text-sm font-bold text-ads-text">① 条件確認</div>
    <div class="text-xs text-ads-muted mt-1">対象・期限を一次情報で</div>
  </div>
  <i data-lucide="arrow-right" class="w-6 h-6 text-ads-dim hidden md:block flex-shrink-0"></i>
  <i data-lucide="arrow-down" class="w-6 h-6 text-ads-dim md:hidden mx-auto"></i>
  <div class="rounded-xl border border-ads-border bg-ads-surface px-4 py-3 text-center flex-1">
    <i data-lucide="hammer" class="w-6 h-6 text-ads-accent mx-auto mb-1"></i>
    <div class="text-sm font-bold text-ads-text">② 見積・契約</div>
    <div class="text-xs text-ads-muted mt-1">工事内容の確定</div>
  </div>
  <i data-lucide="arrow-right" class="w-6 h-6 text-ads-dim hidden md:block flex-shrink-0"></i>
  <i data-lucide="arrow-down" class="w-6 h-6 text-ads-dim md:hidden mx-auto"></i>
  <div class="rounded-xl border border-ads-border bg-ads-surface px-4 py-3 text-center flex-1">
    <i data-lucide="landmark" class="w-6 h-6 text-ads-accent mx-auto mb-1"></i>
    <div class="text-sm font-bold text-ads-text">③ 手続き</div>
    <div class="text-xs text-ads-muted mt-1">事前 / 事後は制度次第</div>
  </div>
</div>
```

## 条件分岐（シンプル）

```html
<div class="grid md:grid-cols-2 gap-4 my-8">
  <div class="rounded-xl border-2 border-green-200 bg-green-50/80 p-4">
    <div class="flex items-center gap-2 font-bold text-green-900 mb-2">
      <i data-lucide="check-circle" class="w-5 h-5"></i> たぶん対象
    </div>
    <ul class="text-sm text-ads-text space-y-1 list-disc list-inside">
      <li>条件Aを満たす</li>
      <li>期間内に申請</li>
    </ul>
  </div>
  <div class="rounded-xl border-2 border-amber-200 bg-amber-50/80 p-4">
    <div class="flex items-center gap-2 font-bold text-amber-900 mb-2">
      <i data-lucide="triangle-alert" class="w-5 h-5"></i> 要確認
    </div>
    <ul class="text-sm text-ads-text space-y-1 list-disc list-inside">
      <li>自治体・事業者で差がある</li>
      <li>性能・工事種別の定義を確認</li>
    </ul>
  </div>
</div>
```

## 印刷・PDF

`base.html` に印刷用スタイルと PDF ボタンあり。横に広すぎる表は `overflow-x-auto` で囲む。

## コードブロック

リフォーム図解では**コードが主役になることは少ない**。JSONや申請サイトの画面例を載せる場合は、**必ず前後に日本語で「何を見せているか」**を書く（diagram-maji の「このコードがやること」に相当）。
