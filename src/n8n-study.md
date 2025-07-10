---
marp: true
theme: default
paginate: true
lang: "ja"
footer: "©2025 n8n Study"
style: |
  /* Rosé Pine カラーパレット */
  :root {
    --rp-base: #191724;
    --rp-surface: #1f1d2e;
    --rp-overlay: #26233a;
    --rp-muted: #6e6a86;
    --rp-subtle: #908caa;
    --rp-text: #e0def4;
    --rp-love: #eb6f92;
    --rp-gold: #f6c177;
    --rp-rose: #ebbcba;
    --rp-pine: #31748f;
    --rp-foam: #9ccfd8;
    --rp-iris: #c4a7e7;
    --rp-highlight-low: #21202e;
    --rp-highlight-med: #403d52;
    --rp-highlight-high: #524f67;
  }

  /* プレゼンテーション全体のスタイル */
  section {
    font-family: "Noto Sans JP", "Hiragino Kaku Gothic ProN", "Hiragino Sans", Meiryo, sans-serif;
    background: linear-gradient(135deg, var(--rp-base) 0%, var(--rp-surface) 100%);
    color: var(--rp-text);
    font-size: 24px;
    line-height: 1.5;
    justify-content: flex-start;
    align-items: flex-start;
    padding: 40px;
    margin: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }

  /* 見出しのスタイル */
  h1 {
    color: var(--rp-iris);
    font-size: 40px;
    margin-top: 0;
    margin-bottom: 1em;
    text-shadow: 0 2px 4px rgba(0,0,0,0.3);
  }

  h2 {
    color: var(--rp-foam);
    font-size: 32px;
    margin-bottom: 0.8em;
    text-shadow: 0 1px 2px rgba(0,0,0,0.3);
  }

  h3 {
    color: var(--rp-gold);
    font-size: 28px;
    margin-bottom: 0.6em;
  }

  /* リストのスタイル */
  ul, ol {
    font-size: 22px;
    margin-left: 1em;
    line-height: 1.6;
    color: var(--rp-text);
  }

  /* ネストされたリストのスタイル */
  ul ul, ul ol, ol ul, ol ol {
    font-size: 20px;
    margin-top: 0.3em;
    margin-bottom: 0.3em;
    color: var(--rp-subtle);
  }

  /* リストアイテムの間隔 */
  li {
    margin-bottom: 0.5em;
  }

  /* テキストのスタイル */
  p {
    font-size: 24px;
    margin-bottom: 1em;
    color: var(--rp-text);
  }

  /* コードブロックのスタイル */
  pre {
    background-color: var(--rp-highlight-low);
    border: 1px solid var(--rp-highlight-med);
    border-radius: 8px;
    padding: 1em;
    color: var(--rp-text);
  }

  /* ヘッダーとフッターのスタイル */
  header, footer {
    color: var(--rp-muted);
    font-size: 0.8em;
  }

  /* 画像のスタイル */
  section img {
    max-width: 80%;
    height: auto;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.3);
  }

  /* テーブルのスタイル */
  table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0;
    margin: 1.5em 0;
    background-color: var(--rp-base);
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
    border: 1px solid var(--rp-highlight-med);
  }

  th, td {
    padding: 1em;
    border-bottom: 1px solid var(--rp-highlight-med);
    color: var(--rp-text);
    font-size: 18px;
    text-align: left;
    vertical-align: middle;
    background-color: var(--rp-base);
  }

  th {
    background-color: var(--rp-overlay);
    color: var(--rp-iris);
    font-weight: bold;
    font-size: 20px;
  }

  tr:last-child td {
    border-bottom: none;
  }

  /* テーブル内の強調テキスト */
  table strong {
    color: var(--rp-gold);
    font-weight: bold;
  }

  /* テーブルヘッダーのアニメーション効果 */
  /*
  th::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 3px;
    background: linear-gradient(90deg, var(--rp-rose) 0%, var(--rp-gold) 100%);
  }
  */

  /* タイトルページのスタイル */
  section.title-slide {
    background: linear-gradient(135deg, var(--rp-base) 0%, var(--rp-surface) 50%, var(--rp-overlay) 100%);
    color: var(--rp-text);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    padding: 40px;
    position: relative;
    overflow: hidden;
  }

  section.title-slide::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: radial-gradient(circle at 30% 20%, var(--rp-iris) 0%, transparent 50%),
                radial-gradient(circle at 70% 80%, var(--rp-pine) 0%, transparent 50%);
    opacity: 0.1;
    z-index: 0;
  }

  section.title-slide > * {
    position: relative;
    z-index: 1;
  }

  section.title-slide h1 {
    color: var(--rp-iris);
    font-size: 5em;
    margin-bottom: 0.2em;
    line-height: 1.2;
    text-shadow: 0 4px 8px rgba(0,0,0,0.5);
  }

  section.title-slide h2 {
    color: var(--rp-foam);
    font-size: 2em;
    margin-bottom: 2em;
    font-weight: normal;
    text-shadow: 0 2px 4px rgba(0,0,0,0.3);
  }

  section.title-slide footer {
    color: var(--rp-muted);
    font-size: 1.2em;
    position: absolute;
    bottom: 40px;
    left: 40px;
  }

  /* フレックスコンテナのスタイル */
  .flex-container {
    display: flex;
    justify-content: flex-start;
    align-items: flex-start;
    gap: 20px;
  }

  /* ハイライトボックスのスタイル */
  .highlight-box {
    background: linear-gradient(135deg, var(--rp-highlight-low) 0%, var(--rp-overlay) 100%);
    border-left: 4px solid var(--rp-iris);
    padding: 1.5em;
    border-radius: 8px;
    margin: 1em 0;
    box-shadow: 0 4px 12px rgba(0,0,0,0.2);
  }

  /* コードハイライト */
  .code-example {
    background: linear-gradient(135deg, var(--rp-base) 0%, var(--rp-highlight-low) 100%);
    color: var(--rp-text);
    padding: 1.5em;
    border-radius: 8px;
    font-family: 'JetBrains Mono', 'Fira Code', 'Courier New', monospace;
    font-size: 18px;
    border: 1px solid var(--rp-highlight-med);
    box-shadow: 0 4px 12px rgba(0,0,0,0.3);
  }

  /* カードスタイル */
  .card {
    background: linear-gradient(135deg, var(--rp-overlay) 0%, var(--rp-highlight-low) 100%);
    border-radius: 12px;
    padding: 1.5em;
    margin: 1em 0;
    border: 1px solid var(--rp-highlight-med);
    box-shadow: 0 6px 20px rgba(0,0,0,0.3);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .card:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(0,0,0,0.4);
  }

  /* グラデーションテキスト */
  .gradient-text {
    background: linear-gradient(135deg, var(--rp-iris) 0%, var(--rp-foam) 50%, var(--rp-gold) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-weight: bold;
  }

  /* アニメーション要素 */
  .animated {
    animation: fadeInUp 0.6s ease-out;
  }

  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  /* スライド番号 */
  section::after {
    color: var(--rp-muted);
    font-size: 0.8em;
  }

  /* リンクスタイル */
  a {
    color: var(--rp-foam);
    text-decoration: none;
    border-bottom: 1px solid var(--rp-foam);
    transition: color 0.3s ease;
  }

  a:hover {
    color: var(--rp-iris);
  }

  /* 強調テキスト */
  strong {
    color: var(--rp-gold);
  }

  /* 引用スタイル */
  blockquote {
    border-left: 4px solid var(--rp-rose);
    padding-left: 1em;
    margin: 1em 0;
    font-style: italic;
    color: var(--rp-subtle);
  }

  /* リストマーカー */
  ul li::marker {
    color: var(--rp-iris);
  }

  ol li::marker {
    color: var(--rp-foam);
  }
math: mathjax
mermaid: true
---

<!-- Mermaidを読み込み -->
<script type="module">
import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@11.4.1/dist/mermaid.esm.min.mjs';
mermaid.initialize({ startOnLoad: true });
</script>

<!-- タイトルスライド -->

# <span>n8n</span>

## AI ワークフロー自動化プラットフォーム

<!-- _class: title-slide -->

---

# 目次

## 基礎編

<div class="card animated">
  <ol>
    <li><strong>n8n とは何か</strong> - 基本概念と特徴</li>
    <li><strong>n8n の特徴と強み</strong> - 他のツールとの違い</li>
    <li><strong>n8n のアーキテクチャ概要</strong> - システム構成</li>
    <li><strong>n8n の主な利用シーン</strong> - 実用例</li>
    <li><strong>ワークフローの基本構造</strong> - ノードとコネクション</li>
    <li><strong>コアノードと統合例</strong> - 主要機能</li>
    <li><strong>実際のワークフロー作成デモ</strong> - 実践例</li>
  </ol>
</div>

---

# 目次

## 応用編

<div class="card animated">
  <ol>
    <li><strong>n8n の拡張性</strong> - カスタムノード・API 連携</li>
    <li><strong>セキュリティと運用</strong> - 本格運用に向けて</li>
    <li><strong>n8n の導入方法</strong> - Cloud/Self-host/Docker</li>
    <li><strong>パフォーマンス最適化</strong> - 高速化とスケーリング</li>
    <li><strong>トラブルシューティング</strong> - よくある問題と解決策</li>
    <li><strong>ベストプラクティス</strong> - 設計と運用の指針</li>
    <li><strong>企業導入事例</strong> - 実際の活用例</li>
    <li><strong>コミュニティと学習リソース</strong> - 学習支援</li>
    <li><strong>今後の展望とまとめ</strong> - 発展性</li>
  </ol>
</div>

---

# n8n 企業情報

<div class="card animated">
 🏢 企業概要

- **企業名**: n8n.io GmbH
- **設立**: 2019 年
- **創業者**: Jan Oberhauser
- **本社**: ドイツ・ベルリン
- **従業員数**: 100 名以上（2024 年時点）
</div>

<div class="highlight-box">
> **ミッション:** プライバシー重視のワークフロー自動化で、誰もが簡単にシステムを統合できる世界を創造する
</div>

---

# 創業ストーリー

<div class="card animated">
 🚀 創業の背景

- **2019 年** - Jan Oberhauser が n8n を開発開始
- **オープンソース** - コミュニティ主導の開発
- **Fair-code** - 新しいライセンスモデルの確立

**💡 創業者のビジョン**

- プライバシー重視の自動化ツール
- 開発者フレンドリーな設計
- コミュニティ主導の成長
</div>

---

<div class="card animated">
 📈 成長軌跡

- **2019 年** - GitHub でオープンソース公開
- **2020 年** - 初回資金調達
- **2021 年** - n8n Cloud サービス開始
- **2022 年** - 企業向け機能強化
- **2023 年** - グローバル展開加速
- **2024 年** - AI 機能統合強化
</div>

---

# ビジネスモデル

#### ☁️ n8n Cloud

- SaaS 型サービス
- 月額・年額サブスクリプション
- 自動スケーリング
- 24/7 サポート

#### 🏢 エンタープライズ

- 企業向けソリューション
- オンプレミス導入
- カスタマイズ開発
- 専用サポート
- SLA 保証

---

#### 🤝 パートナー

- エコシステム構築
- システムインテグレーター
- コンサルティング
- トレーニング
- カスタム開発

> **特徴:** Fair-code ライセンスにより、個人・小規模利用は無料、商用利用は有料という柔軟なモデル

---

# 市場ポジション

### 📊 市場シェアと競合

- **Zapier**: 市場リーダー、最も普及している
- **Dify**: 自己ホスト可能、ワークフロー、AI エージェント
- **n8n**: 自己ホスト可能、ワークフロー、AI エージェント
- **Microsoft Power Automate**: エンタープライズ、Microsoft 統合

### 🎯 n8n の差別化要因

- **自己ホスト可能** - オンプレミス展開
- **Fair-code ライセンス** - 柔軟な利用モデル
- **開発者フレンドリー** - カスタマイズ性
- **豊富な接続先設定** - Slack / Gmail / Calender /などなど

---

# 資金調達と投資家

### 💰 資金調達履歴

- **2020 年** - シリーズ A: $12M
- **2021 年** - シリーズ B: $50M
- **2023 年** - シリーズ C: $100M+
- **総調達額** - $200M 以上

### 🎯 投資家

- **Sequoia Capital** - リード投資家
- **Bessemer Venture Partners** - 主要投資家
- **FirstMark Capital** - 早期投資家
- **GitHub** - 戦略的投資家

---

### 📈 企業価値

- **バリュエーション** - $1B+（ユニコーン）
- **成長率** - 年間 300%+
- **顧客数** - 10,000+企業
- **従業員数** - 100 名+（急成長中）

### 🌍 グローバル展開

- **北米市場での急成長** - AI エージェントともに急成長
- **ヨーロッパでの基盤強化** - ヨーロッパ発の SaaS サービスとして
- **アジア太平洋地域への展開** - 日本語化などへの取り組み強化

---

# 1. n8n とは何か

<div class="card animated">
<div style="display: flex; justify-content: space-between; align-items: center;">
  <div style="width: 55%;">
    <h3><span class="gradient-text">n8n（n-eight-n）とは</span></h3>
    <ul>
      <li><strong>Fair-code</strong>ライセンスのワークフロー自動化ツール</li>
      <li>APIを持つアプリケーション間の接続とデータ操作</li>
      <li>AI機能とビジネスプロセス自動化の組み合わせ</li>
      <li>コードを書かずに複雑なワークフローを構築可能</li>
    </ul>
    
  </div>
  <div style="width: 45%;">
    <img src="https://n8niostorageaccount.blob.core.windows.net/n8nio-strapi-blobs-prod/assets/Home_ITO_Ps_5a5aac3fda.webp" alt="n8n" style="width: 100%; margin: 0 auto;">
  </div>
</div>
</div>

---

# n8n の基本概念

<div style="display: flex; justify-content: space-around; margin: 2em 0;">
  <div class="card animated" style="width: 30%; text-align: center; padding: 1em;">
    <h3>🔗 統合</h3>
    <p style="font-size: 18px;">APIを持つアプリケーション間の接続</p>
  </div>
  <div class="card animated" style="width: 30%; text-align: center; padding: 1em;">
    <h3>⚙️ 自動化</h3>
    <p style="font-size: 18px;">ビジネスプロセスの自動実行</p>
  </div>
  <div class="card animated" style="width: 30%; text-align: center; padding: 1em;">
    <h3>🤖 AI機能</h3>
    <p style="font-size: 18px;">AIを活用した高度な処理</p>
  </div>
</div>

<div class="highlight-box">
  <strong>特徴:</strong> プライバシー重視（自己ホスト可能）、高度にカスタマイズ可能、直感的なUI
</div>

---

# 2. n8n の特徴と強み

<div style="display: grid; grid-template-columns: 1fr 1fr; grid-template-rows: 1fr 1fr; gap: 10px; height: 46vh;">
  <div class="card animated" style="padding: 0.6em;">
    <h3 style="font-size: 1em; margin-bottom: 0.3em;">🔒 プライバシー重視</h3>
    <ul style="font-size: 0.9em; line-height: 1.1;">
      <li>Fair-codeライセンス</li>
      <li>自己ホスト可能</li>
      <li>データの完全制御</li>
    </ul>
  </div>
  <div class="card animated" style="padding: 0.6em;">
    <h3 style="font-size: 1em; margin-bottom: 0.3em;">🚀 豊富な統合</h3>
    <ul style="font-size: 0.9em; line-height: 1.1;">
      <li>400+のノード</li>
      <li>主要SaaSサービス対応</li>
      <li>Webhook/API対応</li>
    </ul>
  </div>
  <div class="card animated" style="padding: 0.6em;">
    <h3 style="font-size: 1em; margin-bottom: 0.3em;">🎨 高度なカスタマイズ</h3>
    <ul style="font-size: 0.9em; line-height: 1.1;">
      <li>カスタムノード開発</li>
      <li>TypeScript対応</li>
      <li>柔軟なデータ変換</li>
    </ul>
  </div>
  <div class="card animated" style="padding: 0.6em;">
    <h3 style="font-size: 1em; margin-bottom: 0.3em;">💡 直感的なUI</h3>
    <ul style="font-size: 0.9em; line-height: 1.1;">
      <li>ドラッグ&ドロップ</li>
      <li>リアルタイムプレビュー</li>
      <li>視覚的なワークフロー</li>
    </ul>
  </div>
</div>

---

# 他の自動化ツールとの比較

<div style="text-align: center; width: 100%; margin: 2em 0;">
  <table style="border-collapse: separate !important; border-spacing: 0 !important; background-color: var(--rp-base) !important; border-radius: 8px !important; overflow: hidden !important; box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3) !important; border: 1px solid var(--rp-highlight-med) !important; margin: 0 auto !important; display: table !important; width: auto !important;">
    <thead>
      <tr>
        <th style="padding: 1em; background-color: var(--rp-overlay); color: var(--rp-iris); font-weight: bold; font-size: 20px; text-align: left; border-bottom: 1px solid var(--rp-highlight-med);">特徴</th>
        <th style="padding: 1em; background-color: var(--rp-overlay); color: var(--rp-iris); font-weight: bold; font-size: 20px; text-align: left; border-bottom: 1px solid var(--rp-highlight-med);">n8n</th>
        <th style="padding: 1em; background-color: var(--rp-overlay); color: var(--rp-iris); font-weight: bold; font-size: 20px; text-align: left; border-bottom: 1px solid var(--rp-highlight-med);">Dify</th>
        <th style="padding: 1em; background-color: var(--rp-overlay); color: var(--rp-iris); font-weight: bold; font-size: 20px; text-align: left; border-bottom: 1px solid var(--rp-highlight-med);">Zapier</th>
        <th style="padding: 1em; background-color: var(--rp-overlay); color: var(--rp-iris); font-weight: bold; font-size: 20px; text-align: left; border-bottom: 1px solid var(--rp-highlight-med);">Make</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; font-weight: bold; background-color: var(--rp-base);">ライセンス</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">Fair-code</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">オープンソース</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">プロプライエタリ</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">プロプライエタリ</td>
      </tr>
      <tr>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; font-weight: bold; background-color: var(--rp-base);">ホスティング</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">自己ホスト可能</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">自己ホスト可能</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">クラウドのみ</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">クラウドのみ</td>
      </tr>
      <tr>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; font-weight: bold; background-color: var(--rp-base);">AI機能</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">豊富な統合</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">AI特化</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">基本的</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">基本的</td>
      </tr>
      <tr>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; font-weight: bold; background-color: var(--rp-base);">カスタマイズ</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">高度</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">高度</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">制限的</td>
        <td style="padding: 0.8em; border-bottom: 1px solid var(--rp-highlight-med); color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">中程度</td>
      </tr>
      <tr>
        <td style="padding: 0.8em; color: var(--rp-text); font-size: 18px; font-weight: bold; background-color: var(--rp-base);">コスト</td>
        <td style="padding: 0.8em; color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">低コスト</td>
        <td style="padding: 0.8em; color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">低コスト</td>
        <td style="padding: 0.8em; color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">高コスト</td>
        <td style="padding: 0.8em; color: var(--rp-text); font-size: 18px; background-color: var(--rp-base);">中コスト</td>
      </tr>
    </tbody>
  </table>
</div>

---

# 3. n8n のアーキテクチャ概要

<div class="card animated">
<div style="display: flex; justify-content: center; margin: 2em 0;">
  <img src="https://docs.n8n.io/assets/images/architecture-overview.png" alt="n8n Architecture" style="width: 90%; border-radius: 8px;">
</div>

<div style="margin-top: 1em;">
  <h3>主要コンポーネント</h3>
  <ul>
    <li><strong>Web UI</strong> - ワークフローエディタと管理画面</li>
    <li><strong>Execution Engine</strong> - ワークフローの実行エンジン</li>
    <li><strong>Database</strong> - ワークフローと実行履歴の保存</li>
    <li><strong>Queue System</strong> - 非同期処理の管理</li>
  </ul>
</div>
</div>

---

# n8n の技術スタック

<div style="display: flex; justify-content: space-around; margin: 2em 0;">
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>フロントエンド</h3>
    <p style="font-size: 18px;">Vue.js + TypeScript</p>
  </div>
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>バックエンド</h3>
    <p style="font-size: 18px;">Node.js + TypeScript</p>
  </div>
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>データベース</h3>
    <p style="font-size: 18px;">SQLite / PostgreSQL</p>
  </div>
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>デプロイ</h3>
    <p style="font-size: 18px;">Docker / npm</p>
  </div>
</div>

<div class="highlight-box">
  <strong>特徴:</strong> TypeScriptによる型安全性、モジュラー設計、拡張可能なアーキテクチャ
</div>

---

# 4. n8n の主な利用シーン

### 📧 メール自動化

- フォーム送信時の自動返信
- リード管理システム連携
- メール配信の自動化

### 📊 データ同期

- CRM とメール配信の同期
- 在庫管理システム連携
- 売上データの自動集計

### 🤖 AI・機械学習

- ChatGPT API 連携
- 画像認識・分析
- 自然言語処理

### 🛠️ 開発支援

- CI/CD パイプライン
- テスト自動化
- デプロイメント自動化

---

# 実用例：E コマース自動化

![E-commerce Automation](https://docs.n8n.io/assets/images/workflows/ecommerce-automation.png)

#### ワークフロー例

1. **注文受信** - Shopify Webhook
2. **在庫確認** - データベース照会
3. **メール通知** - 顧客・管理者へ
4. **配送手配** - 配送業者 API 連携
5. **在庫更新** - リアルタイム同期

---

# 5. ワークフローの基本構造

<div style="display: flex; justify-content: center; margin: 1em 0;">
  <img src="https://docs.n8n.io/assets/images/workflows/basic-workflow-structure.png" alt="Workflow Structure" style="width: 90%; border-radius: 8px;">
</div>

<div style="margin-top: 1em;">
  <h3>基本要素</h3>
  <ul>
    <li><strong>ノード（Node）</strong> - 個別の処理単位</li>
    <li><strong>コネクション（Connection）</strong> - ノード間のデータフロー</li>
    <li><strong>トリガー（Trigger）</strong> - ワークフロー開始点</li>
    <li><strong>アクション（Action）</strong> - 実行処理</li>
  </ul>
</div>

---

# ノードの種類

<div style="display: flex; flex-wrap: wrap; justify-content: space-around; margin: 1.5em 0; gap: 0.8em;">
  <div class="card animated" style="width: 28%; text-align: center; padding: 0.8em;">
    <h3 style="font-size: 18px; margin-bottom: 0.5em;">🔴 トリガーノード</h3>
    <p style="font-size: 14px; margin-bottom: 0.5em;">ワークフローの開始点</p>
    <ul style="text-align: left; font-size: 13px; margin: 0; padding-left: 1.2em;">
      <li>Webhook</li>
      <li>Cron / Schedule</li>
      <li>Manual Trigger</li>
    </ul>
  </div>
  <div class="card animated" style="width: 28%; text-align: center; padding: 0.8em;">
    <h3 style="font-size: 18px; margin-bottom: 0.5em;">🟢 Regular ノード</h3>
    <p style="font-size: 14px; margin-bottom: 0.5em;">メインの処理ノード</p>
    <ul style="text-align: left; font-size: 13px; margin: 0; padding-left: 1.2em;">
      <li>HTTP Request</li>
      <li>サービス連携（600+）</li>
      <li>データベース操作</li>
    </ul>
  </div>
  <div class="card animated" style="width: 28%; text-align: center; padding: 0.8em;">
    <h3 style="font-size: 18px; margin-bottom: 0.5em;">🟡 Core ノード</h3>
    <p style="font-size: 14px; margin-bottom: 0.5em;">基本的なデータ操作</p>
    <ul style="text-align: left; font-size: 13px; margin: 0; padding-left: 1.2em;">
      <li>Set / Edit Fields</li>
      <li>If / Switch</li>
      <li>Merge / Split</li>
    </ul>
  </div>
  <div class="card animated" style="width: 28%; text-align: center; padding: 0.8em;">
    <h3 style="font-size: 18px; margin-bottom: 0.5em;">🔵 Sub-workflow ノード</h3>
    <p style="font-size: 14px; margin-bottom: 0.5em;">ワークフロー管理</p>
    <ul style="text-align: left; font-size: 13px; margin: 0; padding-left: 1.2em;">
      <li>Execute Workflow</li>
      <li>Wait</li>
      <li>Stop and Error</li>
    </ul>
  </div>
  <div class="card animated" style="width: 28%; text-align: center; padding: 0.8em;">
    <h3 style="font-size: 18px; margin-bottom: 0.5em;">🟣 Community ノード</h3>
    <p style="font-size: 14px; margin-bottom: 0.5em;">コミュニティ制作</p>
    <ul style="text-align: left; font-size: 13px; margin: 0; padding-left: 1.2em;">
      <li>npm パッケージ</li>
      <li>カスタムノード</li>
      <li>サードパーティ拡張</li>
    </ul>
  </div>
</div>

---

# 6. コアノードと統合例

### 🔗 統合ノード

- **HTTP Request** - 任意の API 呼び出し
- **Webhook** - 外部からの呼び出し受信
- **REST API** - RESTful API 連携
- **GraphQL** - GraphQL API 連携

### 📊 データベース

- **PostgreSQL** - リレーショナル DB
- **MongoDB** - NoSQL DB
- **MySQL** - オープンソース DB

---

### 📧 コミュニケーション

- **Email** - SMTP 送信
- **Slack** - チーム連携
- **Discord** - ゲーミングコミュニティ

### 🤖 AI・機械学習

- **OpenAI** - ChatGPT API
- **Hugging Face** - 機械学習モデル
- **Google AI** - Gemini API

---

# 主要統合サービス

#### カテゴリ別統合

- **コミュニケーションツール** - Slack, Teams, Gmail
- **オンラインドライブ** - Google Drive, Box, AWS S3, Cloud Storage
- **E コマース** - Shopify, WooCommerce, Stripe
- **CRM** - Salesforce, HubSpot, Pipedrive
- **マーケティング** - Mailchimp, ConvertKit, ActiveCampaign
- **プロジェクト管理** - Trello, Asana, Monday.com

---

# 7. 実際のワークフロー作成デモ

<div style="margin-top: 1em;">
  <h3>メールサマリの通知 : Gmail summary</h3>
  <ol>
    <li><strong>マニュアルトリガー</strong> - 手動で実行</li>
    <li><strong>Gmail情報取得</strong> - 直近10件の受信メールを確認</li>
    <li><strong>テキストの成形</strong> - 後の工程で処理しやすい形に</li>
    <li><strong>AIエージェントで要約を作成</strong> - 全てのメールを確認し、重み付け</li>
    <li><strong>通知送信</strong> - チームへSlack通知</li>
  </ol>
</div>

---

<div style="margin-top: 1em;">
  <h3>Drag on Dropと少しのコードでワークフローを実現</h3>
</div>

<div style="display: flex; justify-content: center; margin: 2em 0;">
  <img src="..//src/images/GmailSummary.png" alt="Gmail Summary Workflow" style="width: 90%; border-radius: 8px; box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);">
</div>

---

# ワークフロー作成手順

<div style="display: flex; justify-content: space-around; margin-top: 2em;">
  <div class="card animated" style="width: 22%; text-align: center; padding: 1em;">
    <h3 style="color: var(--rp-iris); font-size: 24px; margin-bottom: 0.5em;">1. トリガー設定</h3>
    <p style="font-size: 18px; color: var(--rp-text);">ワークフローの開始点を定義</p>
  </div>
  <div class="card animated" style="width: 22%; text-align: center; padding: 1em;">
    <h3 style="color: var(--rp-foam); font-size: 24px; margin-bottom: 0.5em;">2. ノード追加</h3>
    <p style="font-size: 18px; color: var(--rp-text);">必要な処理ノードを配置</p>
  </div>
  <div class="card animated" style="width: 22%; text-align: center; padding: 1em;">
    <h3 style="color: var(--rp-gold); font-size: 24px; margin-bottom: 0.5em;">3. 接続設定</h3>
    <p style="font-size: 18px; color: var(--rp-text);">ノード間のデータフローを定義</p>
  </div>
  <div class="card animated" style="width: 22%; text-align: center; padding: 1em;">
    <h3 style="color: var(--rp-rose); font-size: 24px; margin-bottom: 0.5em;">4. テスト実行</h3>
    <p style="font-size: 18px; color: var(--rp-text);">動作確認とデバッグ</p>
  </div>
</div>

<div class="highlight-box">
  <strong>ポイント:</strong> 段階的に構築し、各ステップでテストを実行することが重要
</div>

---

# 8. n8n の拡張性

### 🔧 カスタムノード開発

- TypeScript/JavaScript で開発
- npm パッケージとして配布
- コミュニティへの貢献
- 企業固有の統合

### 📡 API 連携

- REST API 提供
- Webhook 受信
- 外部システム連携
- CI/CD 統合

---

### 🎨 UI カスタマイズ

- テーマカスタマイズ
- ブランディング対応
- 多言語対応
- アクセシビリティ

### 🔌 プラグインシステム

- 認証方式拡張
- データ形式変換
- 特殊処理追加

---

# 9. セキュリティと運用

<div style="display: flex; justify-content: space-between; align-items: flex-start;">
  <div style="width: 50%;">
    <h3>🔐 セキュリティ機能</h3>
    <ul>
      <li><strong>認証・認可</strong> - JWT, OAuth2対応</li>
      <li><strong>暗号化</strong> - 機密データの暗号化保存</li>
      <li><strong>アクセス制御</strong> - ロールベース権限管理</li>
      <li><strong>監査ログ</strong> - 操作履歴の記録</li>
    </ul>

    <h3>📊 監視・ログ</h3>
    <ul>
      <li>実行ログの詳細記録</li>
      <li>パフォーマンス監視</li>
      <li>エラー通知システム</li>
      <li>メトリクス収集</li>
    </ul>

  </div>

  <div style="width: 45%;">
    <h3>🔄 運用管理</h3>
    <ul>
      <li><strong>バックアップ</strong> - 自動バックアップ設定</li>
      <li><strong>スケーリング</strong> - 負荷分散対応</li>
      <li><strong>更新管理</strong> - セキュリティパッチ適用</li>
      <li><strong>障害対応</strong> - 自動復旧機能</li>
    </ul>

    <h3>📈 パフォーマンス</h3>
    <ul>
      <li>非同期処理</li>
      <li>キューシステム</li>
      <li>キャッシュ機能</li>
      <li>リソース最適化</li>
    </ul>

  </div>
</div>

---

# 10. n8n の導入方法

<div style="display: flex; justify-content: space-around; margin: 2em 0;">
  <div class="card animated" style="width: 30%; text-align: center; padding: 1em;">
    <h3 style="color: var(--rp-iris); font-size: 24px; margin-bottom: 0.5em;">☁️ n8n Cloud</h3>
    <p style="font-size: 18px; color: var(--rp-gold); font-weight: bold;">マネージドサービス</p>
    <ul style="text-align: left; font-size: 16px; color: var(--rp-text);">
      <li>簡単セットアップ</li>
      <li>自動スケーリング</li>
      <li>24/7サポート</li>
      <li>有料プラン</li>
    </ul>
  </div>
  <div class="card animated" style="width: 30%; text-align: center; padding: 1em;">
    <h3 style="color: var(--rp-foam); font-size: 24px; margin-bottom: 0.5em;">🐳 Docker</h3>
    <p style="font-size: 18px; color: var(--rp-gold); font-weight: bold;">推奨方法</p>
    <ul style="text-align: left; font-size: 16px; color: var(--rp-text);">
      <li>環境分離</li>
      <li>簡単デプロイ</li>
      <li>バージョン管理</li>
      <li>無料</li>
    </ul>
  </div>
  <div class="card animated" style="width: 30%; text-align: center; padding: 1em;">
    <h3 style="color: var(--rp-rose); font-size: 24px; margin-bottom: 0.5em;">📦 npm</h3>
    <p style="font-size: 18px; color: var(--rp-gold); font-weight: bold;">直接インストール</p>
    <ul style="text-align: left; font-size: 16px; color: var(--rp-text);">
      <li>完全制御</li>
      <li>カスタマイズ可能</li>
      <li>開発環境向け</li>
      <li>無料</li>
    </ul>
  </div>
</div>

---

# 11. パフォーマンス最適化

<div style="display: flex; justify-content: space-between; align-items: flex-start;">
  <div style="width: 50%;">
    <h3>🚀 実行最適化</h3>
    <ul>
      <li><strong>バッチ処理</strong> - 大量データの効率的処理</li>
      <li><strong>並列実行</strong> - 複数ノードの同時実行</li>
      <li><strong>キャッシュ活用</strong> - 重複処理の回避</li>
      <li><strong>リソース制限</strong> - メモリ・CPU使用量の制御</li>
    </ul>
    
    <h3>📊 監視・メトリクス</h3>
    <ul>
      <li>実行時間の測定</li>
      <li>エラー率の監視</li>
      <li>リソース使用量の追跡</li>
      <li>ボトルネックの特定</li>
    </ul>
  </div>
  
  <div style="width: 45%;">
    <h3>⚡ スケーリング戦略</h3>
    <ul>
      <li><strong>水平スケーリング</strong> - 複数インスタンス</li>
      <li><strong>垂直スケーリング</strong> - リソース増強</li>
      <li><strong>負荷分散</strong> - トラフィック分散</li>
      <li><strong>自動スケーリング</strong> - 需要に応じた調整</li>
    </ul>
    
    <h3>🔧 最適化テクニック</h3>
    <ul>
      <li>データベースクエリの最適化</li>
      <li>API呼び出しの効率化</li>
      <li>不要な処理の削除</li>
      <li>非同期処理の活用</li>
    </ul>
  </div>
</div>

---

# 12. トラブルシューティング

<div style="display: flex; justify-content: space-between; align-items: flex-start;">
  <div style="width: 50%;">
    <h3>🔍 よくある問題</h3>
    <ul>
      <li><strong>認証エラー</strong> - API認証情報の確認</li>
      <li><strong>タイムアウト</strong> - ネットワーク接続の確認</li>
      <li><strong>データ形式エラー</strong> - JSON/XML形式の検証</li>
      <li><strong>メモリ不足</strong> - リソース使用量の確認</li>
    </ul>
    
    <h3>🛠️ デバッグ手法</h3>
    <ul>
      <li>実行ログの詳細確認</li>
      <li>ノード単位でのテスト実行</li>
      <li>データフローの可視化</li>
      <li>エラーメッセージの解析</li>
    </ul>
  </div>
  
  <div style="width: 45%;">
    <h3>📋 診断チェックリスト</h3>
    <ul>
      <li><strong>接続確認</strong> - ネットワーク・API接続</li>
      <li><strong>認証確認</strong> - トークン・キーの有効性</li>
      <li><strong>権限確認</strong> - アクセス権限の確認</li>
      <li><strong>設定確認</strong> - 環境変数・設定値</li>
    </ul>
    
    <h3>🔧 解決策</h3>
    <ul>
      <li>再認証の実行</li>
      <li>タイムアウト値の調整</li>
      <li>データ形式の変換</li>
      <li>リソース制限の緩和</li>
    </ul>
  </div>
</div>

---

# 13. ベストプラクティス

### 設計原則

- **単一責任** - 1 つのノードに 1 つの機能
- **エラーハンドリング** - 例外処理の実装
- **ログ記録** - 実行履歴の保存
- **バージョン管理** - 変更履歴の追跡

#### 🔒 セキュリティ

- 機密情報の暗号化
- アクセス権限の最小化
- 定期的なセキュリティ監査
- セキュリティパッチの適用

### 運用管理

- **監視体制** - 24/7 監視の構築
- **バックアップ** - 定期的なデータバックアップ
- **障害対応** - インシデント対応手順
- **更新管理** - 定期的なアップデート

#### 🧑‍🤝‍🧑 チーム協働

- ドキュメント整備
- コードレビュー
- 知識共有
- 継続的改善

---

# 14. 企業導入事例

### 製造業での活用

- 在庫管理自動化 - リアルタイム在庫追跡
- 品質管理 - 検査データの自動収集
- サプライチェーン - 発注・配送の自動化
- 設備監視 - IoT センサーとの連携

#### 🏥 医療・ヘルスケア

- 患者データの自動同期
- 予約システムの連携
- 医療機器の監視
- コンプライアンス管理

### 金融・保険

- リスク管理 - リアルタイム監視
- コンプライアンス - 規制対応の自動化
- 顧客サービス - 問い合わせ対応
- 不正検知 - 異常検知システム

#### 🛒 小売・E コマース

- 在庫・価格の自動更新
- 顧客行動分析
- マーケティング自動化
- 配送・物流の最適化

---

# 導入効果の測定

<div class="card animated">
<div style="display: flex; justify-content: center; margin: 1em 0;">
  <div style="width: 90%; padding: 1.5em; border-radius: 8px;">
    <h3>📊 定量的効果</h3>
    <div style="display: flex; justify-content: space-around; margin: 2em 0;">
      <div class="card animated" style="width: 22%; text-align: center; padding: 1em;">
        <h4>時間短縮</h4>
        <p style="font-size: 18px; color: var(--rp-iris); font-weight: bold;">80%</p>
        <p style="font-size: 14px;">手作業の削減</p>
      </div>
      <div class="card animated" style="width: 22%; text-align: center; padding: 1em;">
        <h4>エラー削減</h4>
        <p style="font-size: 18px; color: var(--rp-iris); font-weight: bold;">95%</p>
        <p style="font-size: 14px;">人的ミスの削減</p>
      </div>
      <div class="card animated" style="width: 22%; text-align: center; padding: 1em;">
        <h4>コスト削減</h4>
        <p style="font-size: 18px; color: var(--rp-iris); font-weight: bold;">60%</p>
        <p style="font-size: 14px;">運用コストの削減</p>
      </div>
      <div class="card animated" style="width: 22%; text-align: center; padding: 1em;">
        <h4>ROI向上</h4>
        <p style="font-size: 18px; color: var(--rp-iris); font-weight: bold;">300%</p>
        <p style="font-size: 14px;">投資対効果</p>
      </div>
    </div>
  </div>
</div>

<div style="margin-top: 1em;">
  <h3>📈 定性的効果</h3>
  <ul>
    <li><strong>従業員満足度向上</strong> - 反復作業からの解放</li>
    <li><strong>意思決定の迅速化</strong> - リアルタイムデータ活用</li>
    <li><strong>顧客満足度向上</strong> - 迅速な対応</li>
    <li><strong>競争力強化</strong> - 効率化による差別化</li>
  </ul>
</div>

---

# 15. コミュニティと学習リソース

<div class="card animated">
### 🌐 公式リソース

- **ドキュメント** - 詳細な技術文書
- **チュートリアル** - ステップバイステップ
- **API リファレンス** - 開発者向け
- **サンプルワークフロー** - 実用例

### 🎓 学習コース

- **ビデオコース** - 初心者・上級者向け
- **テキストコース** - 実践的な学習
- **認定プログラム** - スキル証明

### 👥 コミュニティ

- **フォーラム** - 質問・回答
- **GitHub** - 開発・バグ報告
- **Discord** - リアルタイム交流
- **ブログ** - 最新情報

### 🛠️ 開発支援

- **カスタムノード** - コミュニティ開発
- **プラグイン** - 機能拡張
- **テーマ** - UI カスタマイズ
</div>

---

# 学習パス

<div class="card animated">
<div style="display: flex; justify-content: center; margin: 1em 0;">
  <img src="https://docs.n8n.io/assets/images/learning-path/learning-path-overview.png" alt="Learning Path" style="width: 90%; border-radius: 8px;">
</div>

<div style="margin-top: 1em;">
  <h3>推奨学習順序</h3>
  <ol>
    <li><strong>クイックスタート</strong> - 基本的なワークフロー作成</li>
    <li><strong>チュートリアル</strong> - 実践的な例を通じた学習</li>
    <li><strong>コース</strong> - 体系的な知識習得</li>
    <li><strong>コミュニティ参加</strong> - 実践と交流</li>
  </ol>
</div>
</div>

---

# 16. 今後の展望とまとめ

<div class="card animated">
<div style="display: flex; justify-content: space-around; margin: 2em 0;">
  <div style="width: 45%;">
    <h3 style="color: var(--rp-iris); margin-bottom: 1em;">🚀 技術発展</h3>
    <ul>
      <li>AI機能の強化</li>
      <li>リアルタイム処理</li>
      <li>エッジコンピューティング</li>
      <li>ブロックチェーン統合</li>
      <li>IoTデバイス連携</li>
    </ul>
  </div>

  <div style="width: 45%;">
    <h3 style="color: var(--rp-rose); margin-bottom: 1em;">📈 市場動向</h3>
    <ul>
      <li>自動化需要の増加</li>
      <li>ノーコード/ローコードの普及</li>
      <li>企業のDX推進</li>
      <li>クラウドネイティブ化</li>
      <li>セキュリティ強化</li>
    </ul>
  </div>
</div>
</div>

<div class="highlight-box">
  <strong>n8nの価値:</strong> プライバシー重視、高度なカスタマイズ、豊富な統合、活発なコミュニティ
</div>

---

# n8n の核心価値

<div class="card animated">
<div style="display: flex; justify-content: center; margin: 1em 0 2em 0;">
  <div style="width: 90%; padding: 1.5em; border-radius: 8px; box-shadow: 0 2px 6px rgba(0,0,0,0.1);">
    <ul style="list-style-type: none; padding-left: 0;">
      <li style="margin-bottom: 1em; display: flex; align-items: center;">
        <span style="background-color: var(--rp-iris); color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">1</span>
        <span><strong>Fair-codeライセンス</strong> - プライバシーと制御の両立</span>
      </li>
      <li style="margin-bottom: 1em; display: flex; align-items: center;">
        <span style="background-color: var(--rp-iris); color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">2</span>
        <span><strong>高度なカスタマイズ</strong> - 企業固有のニーズに対応</span>
      </li>
      <li style="margin-bottom: 1em; display: flex; align-items: center;">
        <span style="background-color: var(--rp-iris); color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">3</span>
        <span><strong>豊富な統合</strong> - 400+のノードで幅広い連携</span>
      </li>
      <li style="display: flex; align-items: center;">
        <span style="background-color: var(--rp-iris); color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">4</span>
        <span><strong>活発なコミュニティ</strong> - 継続的な発展と支援</span>
      </li>
    </ul>
  </div>
</div>

<div style="text-align: center; margin-top: 3em;">
  <p style="font-size: 28px; font-weight: bold; color: var(--rp-iris);">n8nでワークフロー自動化の未来を創造しよう</p>
</div>
</div>

---

<div class="card animated" style="display: flex; justify-content: center; align-items: center; height: 70vh;">
  <div style="text-align: center;">
    <h2 style="font-size: 36px; margin-bottom: 1em; color: var(--rp-iris);">Questions?</h2>
    <img src="https://cdn-icons-png.flaticon.com/512/6295/6295417.png" alt="Questions" style="width: 150px; margin: 0 auto;">
  </div>
</div>

/_ .card.animated の特別なスタイル _/
.card.animated {
animation: fadeInUpCard 0.8s cubic-bezier(0.23, 1, 0.32, 1) !important;
box-shadow: 0 10px 32px rgba(235, 111, 146, 0.18), 0 2px 8px rgba(49, 116, 143, 0.10) !important;
border: 2px solid var(--rp-iris) !important;
background: linear-gradient(135deg, var(--rp-overlay) 60%, var(--rp-highlight-low) 100%) !important;
}

@keyframes fadeInUpCard {
from {
opacity: 0;
transform: translateY(40px) scale(0.98);
filter: blur(4px);
}
to {
opacity: 1;
transform: translateY(0) scale(1);
filter: blur(0);
}
}
