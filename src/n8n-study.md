---
marp: true
theme: default
paginate: true
lang: "ja"
header: "n8n - ワークフロー自動化プラットフォーム"
footer: "©2025 n8n Study"
style: |
  /* プレゼンテーション全体のスタイル */
  section {
    font-family: "Noto Sans JP", "Hiragino Kaku Gothic ProN", "Hiragino Sans", Meiryo, sans-serif;
    background-color: white;
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
    color: #2563EB;
    font-size: 40px;
    margin-top: 0;
    margin-bottom: 1em;
  }

  h2 {
    color: #2563EB;
    font-size: 32px;
    margin-bottom: 0.8em;
  }

  /* リストのスタイル */
  ul, ol {
    font-size: 22px;
    margin-left: 1em;
    line-height: 1.6;
  }

  /* ネストされたリストのスタイル */
  ul ul, ul ol, ol ul, ol ol {
    font-size: 20px;
    margin-top: 0.3em;
    margin-bottom: 0.3em;
  }

  /* リストアイテムの間隔 */
  li {
    margin-bottom: 0.5em;
  }

  /* テキストのスタイル */
  p {
    font-size: 24px;
    margin-bottom: 1em;
  }

  /* コードブロックのスタイル */
  pre {
    background-color: #f8f9fa;
    border-radius: 4px;
    padding: 1em;
  }

  /* ヘッダーとフッターのスタイル */
  header, footer {
    color: #666;
    font-size: 0.8em;
  }

  /* 画像のスタイル */
  section img {
    max-width: 80%;
    height: auto;
  }

  /* テーブルのスタイル */
  table {
    width: 100%;
    border-collapse: collapse;
    margin: 1em 0;
  }

  th, td {
    padding: 0.6em;
    border: 1px solid #ddd;
  }

  th {
    background-color: #f0f0f0;
  }

  /* タイトルページのスタイル */
  section.title-slide {
    background: linear-gradient(135deg, #4169e1 0%, #00bfff 100%);
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    padding: 40px;
  }

  section.title-slide h1 {
    color: white;
    font-size: 5em;
    margin-bottom: 0.2em;
    line-height: 1.2;
  }

  section.title-slide h2 {
    color: white;
    font-size: 2em;
    margin-bottom: 2em;
    font-weight: normal;
  }

  section.title-slide footer {
    color: white;
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
    background-color: #f0f7ff;
    border-left: 4px solid #2563EB;
    padding: 1em;
    border-radius: 4px;
    margin: 1em 0;
  }

  /* コードハイライト */
  .code-example {
    background-color: #272822;
    color: #f8f8f2;
    padding: 1em;
    border-radius: 4px;
    font-family: 'Courier New', monospace;
    font-size: 18px;
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

# n8n

## ワークフロー自動化プラットフォーム

<!-- _class: title-slide -->

---

# 目次

## 基礎編

1. **n8n とは何か** - 基本概念と特徴
2. **n8n の特徴と強み** - 他のツールとの違い
3. **n8n のアーキテクチャ概要** - システム構成
4. **n8n の主な利用シーン** - 実用例
5. **ワークフローの基本構造** - ノードとコネクション
6. **コアノードと統合例** - 主要機能
7. **実際のワークフロー作成デモ** - 実践例

---

# 目次

## 応用編

8. **n8n の拡張性** - カスタムノード・API 連携
9. **セキュリティと運用** - 本格運用に向けて
10. **n8n の導入方法** - Cloud/Self-host/Docker
11. **パフォーマンス最適化** - 高速化とスケーリング
12. **トラブルシューティング** - よくある問題と解決策
13. **ベストプラクティス** - 設計と運用の指針
14. **企業導入事例** - 実際の活用例
15. **コミュニティと学習リソース** - 学習支援
16. **今後の展望とまとめ** - 発展性

---

# 1. n8n とは何か

<div style="display: flex; justify-content: space-between; align-items: center;">
  <div style="width: 55%;">
    <h3>n8n（n-eight-n）とは</h3>
    <ul>
      <li><strong>Fair-code</strong>ライセンスのワークフロー自動化ツール</li>
      <li>APIを持つアプリケーション間の接続とデータ操作</li>
      <li>AI機能とビジネスプロセス自動化の組み合わせ</li>
      <li>コードを書かずに複雑なワークフローを構築可能</li>
    </ul>
    
    <div class="highlight-box">
      <strong>核心理念:</strong> プライバシー重視、高度にカスタマイズ可能、便利な統合環境
    </div>
  </div>
  <div style="width: 40%;">
    <img src="https://n8n.io/images/n8n-logo.svg" alt="n8n Logo" style="width: 100%; margin: 0 auto;">
  </div>
</div>

---

# n8n の基本概念

<div style="display: flex; justify-content: space-around; margin: 2em 0;">
  <div style="width: 30%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>🔗 統合</h3>
    <p style="font-size: 18px;">APIを持つアプリケーション間の接続</p>
  </div>
  <div style="width: 30%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>⚙️ 自動化</h3>
    <p style="font-size: 18px;">ビジネスプロセスの自動実行</p>
  </div>
  <div style="width: 30%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>🤖 AI機能</h3>
    <p style="font-size: 18px;">AIを活用した高度な処理</p>
  </div>
</div>

<div style="margin-top: 2em; padding: 1em; background-color: #f8f9fa; border-radius: 8px;">
  <strong>特徴:</strong> プライバシー重視（自己ホスト可能）、高度にカスタマイズ可能、直感的なUI
</div>

---

# 2. n8n の特徴と強み

<div style="display: flex; justify-content: space-between; align-items: flex-start;">
  <div style="width: 50%;">
    <h3>🔒 プライバシー重視</h3>
    <ul>
      <li>Fair-codeライセンス</li>
      <li>自己ホスト可能</li>
      <li>データの完全制御</li>
      <li>オープンソースベース</li>
    </ul>
    
    <h3>🎨 高度なカスタマイズ</h3>
    <ul>
      <li>カスタムノード開発</li>
      <li>JavaScript/TypeScript対応</li>
      <li>柔軟なデータ変換</li>
    </ul>
  </div>
  
  <div style="width: 45%;">
    <h3>🚀 豊富な統合</h3>
    <ul>
      <li>400+のノード</li>
      <li>主要SaaSサービス対応</li>
      <li>Webhook/API対応</li>
      <li>データベース連携</li>
    </ul>
    
    <h3>💡 直感的なUI</h3>
    <ul>
      <li>ドラッグ&ドロップ</li>
      <li>リアルタイムプレビュー</li>
      <li>視覚的なワークフロー</li>
    </ul>
  </div>
</div>

---

# 他の自動化ツールとの比較

<div style="overflow-x: auto; margin: 1.5em 0;">
  <table style="width: 100%; border-collapse: collapse; border: 1px solid #ddd;">
    <thead>
      <tr style="background-color: #f0f7ff;">
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">特徴</th>
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">n8n</th>
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">Zapier</th>
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">Make</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="padding: 12px; border: 1px solid #ddd; font-weight: bold;">ライセンス</td>
        <td style="padding: 12px; border: 1px solid #ddd;">Fair-code</td>
        <td style="padding: 12px; border: 1px solid #ddd;">プロプライエタリ</td>
        <td style="padding: 12px; border: 1px solid #ddd;">プロプライエタリ</td>
      </tr>
      <tr style="background-color: #f8f9fa;">
        <td style="padding: 12px; border: 1px solid #ddd; font-weight: bold;">ホスティング</td>
        <td style="padding: 12px; border: 1px solid #ddd;">自己ホスト可能</td>
        <td style="padding: 12px; border: 1px solid #ddd;">クラウドのみ</td>
        <td style="padding: 12px; border: 1px solid #ddd;">クラウドのみ</td>
      </tr>
      <tr>
        <td style="padding: 12px; border: 1px solid #ddd; font-weight: bold;">カスタマイズ</td>
        <td style="padding: 12px; border: 1px solid #ddd;">高度</td>
        <td style="padding: 12px; border: 1px solid #ddd;">制限的</td>
        <td style="padding: 12px; border: 1px solid #ddd;">中程度</td>
      </tr>
      <tr style="background-color: #f8f9fa;">
        <td style="padding: 12px; border: 1px solid #ddd; font-weight: bold;">コスト</td>
        <td style="padding: 12px; border: 1px solid #ddd;">低コスト</td>
        <td style="padding: 12px; border: 1px solid #ddd;">高コスト</td>
        <td style="padding: 12px; border: 1px solid #ddd;">中コスト</td>
      </tr>
    </tbody>
  </table>
</div>

---

# 3. n8n のアーキテクチャ概要

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

<div style="display: flex; justify-content: space-between; align-items: flex-start;">
  <div style="width: 48%;">
    <h3>📧 メール自動化</h3>
    <ul>
      <li>フォーム送信時の自動返信</li>
      <li>リード管理システム連携</li>
      <li>メール配信の自動化</li>
    </ul>
    
    <h3>📊 データ同期</h3>
    <ul>
      <li>CRMとメール配信の同期</li>
      <li>在庫管理システム連携</li>
      <li>売上データの自動集計</li>
    </ul>
  </div>
  
  <div style="width: 48%;">
    <h3>🤖 AI・機械学習</h3>
    <ul>
      <li>ChatGPT API連携</li>
      <li>画像認識・分析</li>
      <li>自然言語処理</li>
    </ul>
    
    <h3>🛠️ 開発支援</h3>
    <ul>
      <li>CI/CDパイプライン</li>
      <li>テスト自動化</li>
      <li>デプロイメント自動化</li>
    </ul>
  </div>
</div>

---

# 実用例：E コマース自動化

<div style="display: flex; justify-content: center; margin: 1em 0;">
  <img src="https://docs.n8n.io/assets/images/workflows/ecommerce-automation.png" alt="E-commerce Automation" style="width: 90%; border-radius: 8px;">
</div>

<div style="margin-top: 1em;">
  <h3>ワークフロー例</h3>
  <ol>
    <li><strong>注文受信</strong> - Shopify Webhook</li>
    <li><strong>在庫確認</strong> - データベース照会</li>
    <li><strong>メール通知</strong> - 顧客・管理者へ</li>
    <li><strong>配送手配</strong> - 配送業者API連携</li>
    <li><strong>在庫更新</strong> - リアルタイム同期</li>
  </ol>
</div>

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

<div style="display: flex; justify-content: space-around; margin: 2em 0;">
  <div style="width: 30%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>🔴 トリガーノード</h3>
    <p style="font-size: 18px;">ワークフローの開始点</p>
    <ul style="text-align: left; font-size: 16px;">
      <li>Webhook</li>
      <li>スケジュール</li>
      <li>ファイル監視</li>
    </ul>
  </div>
  <div style="width: 30%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>🟡 アクションノード</h3>
    <p style="font-size: 18px;">処理の実行</p>
    <ul style="text-align: left; font-size: 16px;">
      <li>HTTP Request</li>
      <li>データベース操作</li>
      <li>メール送信</li>
    </ul>
  </div>
  <div style="width: 30%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>🟢 変換ノード</h3>
    <p style="font-size: 18px;">データの変換・加工</p>
    <ul style="text-align: left; font-size: 16px;">
      <li>Set</li>
      <li>Function</li>
      <li>Code</li>
    </ul>
  </div>
</div>

---

# 6. コアノードと統合例

<div style="display: flex; justify-content: space-between; align-items: flex-start;">
  <div style="width: 50%;">
    <h3>🔗 統合ノード</h3>
    <ul>
      <li><strong>HTTP Request</strong> - 任意のAPI呼び出し</li>
      <li><strong>Webhook</strong> - 外部からの呼び出し受信</li>
      <li><strong>REST API</strong> - RESTful API連携</li>
      <li><strong>GraphQL</strong> - GraphQL API連携</li>
    </ul>
    
    <h3>📊 データベース</h3>
    <ul>
      <li><strong>PostgreSQL</strong> - リレーショナルDB</li>
      <li><strong>MongoDB</strong> - NoSQL DB</li>
      <li><strong>MySQL</strong> - オープンソースDB</li>
    </ul>
  </div>
  
  <div style="width: 45%;">
    <h3>📧 コミュニケーション</h3>
    <ul>
      <li><strong>Email</strong> - SMTP送信</li>
      <li><strong>Slack</strong> - チーム連携</li>
      <li><strong>Discord</strong> - ゲーミングコミュニティ</li>
    </ul>
    
    <h3>🤖 AI・機械学習</h3>
    <ul>
      <li><strong>OpenAI</strong> - ChatGPT API</li>
      <li><strong>Hugging Face</strong> - 機械学習モデル</li>
      <li><strong>Google AI</strong> - Gemini API</li>
    </ul>
  </div>
</div>

---

# 主要統合サービス

<div style="display: flex; justify-content: center; margin: 1em 0;">
  <img src="https://docs.n8n.io/assets/images/integrations/available-integrations.png" alt="Available Integrations" style="width: 90%; border-radius: 8px;">
</div>

<div style="margin-top: 1em;">
  <h3>カテゴリ別統合</h3>
  <ul>
    <li><strong>Eコマース</strong> - Shopify, WooCommerce, Stripe</li>
    <li><strong>CRM</strong> - Salesforce, HubSpot, Pipedrive</li>
    <li><strong>マーケティング</strong> - Mailchimp, ConvertKit, ActiveCampaign</li>
    <li><strong>プロジェクト管理</strong> - Trello, Asana, Monday.com</li>
  </ul>
</div>

---

# 7. 実際のワークフロー作成デモ

<div style="display: flex; justify-content: center; margin: 1em 0;">
  <img src="https://docs.n8n.io/assets/images/workflows/contact-form-automation.png" alt="Contact Form Automation" style="width: 90%; border-radius: 8px;">
</div>

<div style="margin-top: 1em;">
  <h3>お問い合わせフォーム自動化</h3>
  <ol>
    <li><strong>Webhook受信</strong> - フォーム送信をトリガー</li>
    <li><strong>データ検証</strong> - 必須項目チェック</li>
    <li><strong>CRM登録</strong> - HubSpotにリード追加</li>
    <li><strong>自動返信</strong> - 顧客へ確認メール</li>
    <li><strong>通知送信</strong> - 営業チームへSlack通知</li>
  </ol>
</div>

---

# ワークフロー作成手順

<div style="display: flex; justify-content: space-around; margin-top: 2em;">
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>1. トリガー設定</h3>
    <p style="font-size: 18px;">ワークフローの開始点を定義</p>
  </div>
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>2. ノード追加</h3>
    <p style="font-size: 18px;">必要な処理ノードを配置</p>
  </div>
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>3. 接続設定</h3>
    <p style="font-size: 18px;">ノード間のデータフローを定義</p>
  </div>
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>4. テスト実行</h3>
    <p style="font-size: 18px;">動作確認とデバッグ</p>
  </div>
</div>

<div style="margin-top: 2em; padding: 1em; background-color: #f8f9fa; border-radius: 8px;">
  <strong>ポイント:</strong> 段階的に構築し、各ステップでテストを実行することが重要
</div>

---

# 8. n8n の拡張性

<div style="display: flex; justify-content: space-between; align-items: flex-start;">
  <div style="width: 50%;">
    <h3>🔧 カスタムノード開発</h3>
    <ul>
      <li>TypeScript/JavaScriptで開発</li>
      <li>npmパッケージとして配布</li>
      <li>コミュニティへの貢献</li>
      <li>企業固有の統合</li>
    </ul>
    
    <h3>📡 API連携</h3>
    <ul>
      <li>REST API提供</li>
      <li>Webhook受信</li>
      <li>外部システム連携</li>
      <li>CI/CD統合</li>
    </ul>
  </div>
  
  <div style="width: 45%;">
    <h3>🎨 UIカスタマイズ</h3>
    <ul>
      <li>テーマカスタマイズ</li>
      <li>ブランディング対応</li>
      <li>多言語対応</li>
      <li>アクセシビリティ</li>
    </ul>
    
    <h3>🔌 プラグインシステム</h3>
    <ul>
      <li>認証方式拡張</li>
      <li>データ形式変換</li>
      <li>特殊処理追加</li>
    </ul>
  </div>
</div>

---

# カスタムノード開発例

<div style="display: flex; justify-content: center; margin: 1em 0;">
  <div style="width: 90%; background-color: #f8f9fa; padding: 1.5em; border-radius: 8px; font-family: monospace;">
    <div style="margin-bottom: 1.5em; border-left: 4px solid #2563EB; padding-left: 1em;">
      <p style="color: #555; margin-bottom: 0.3em; font-weight: bold;">カスタムノードの基本構造:</p>
      <div class="code-example">
```typescript
import { IExecuteFunctions } from 'n8n-core';
import { INodeExecutionData } from 'n8n-workflow';

export async function execute(
this: IExecuteFunctions,
items: INodeExecutionData[]
): Promise<INodeExecutionData[]> {
// カスタム処理の実装
return items.map(item => {
// データ変換処理
return item;
});
}

````
      </div>
    </div>
  </div>
</div>

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

# 10. n8nの導入方法

<div style="display: flex; justify-content: space-around; margin: 2em 0;">
  <div style="width: 30%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>☁️ n8n Cloud</h3>
    <p style="font-size: 18px;">マネージドサービス</p>
    <ul style="text-align: left; font-size: 16px;">
      <li>簡単セットアップ</li>
      <li>自動スケーリング</li>
      <li>24/7サポート</li>
      <li>有料プラン</li>
    </ul>
  </div>
  <div style="width: 30%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>🐳 Docker</h3>
    <p style="font-size: 18px;">推奨方法</p>
    <ul style="text-align: left; font-size: 16px;">
      <li>環境分離</li>
      <li>簡単デプロイ</li>
      <li>バージョン管理</li>
      <li>無料</li>
    </ul>
  </div>
  <div style="width: 30%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>📦 npm</h3>
    <p style="font-size: 18px;">直接インストール</p>
    <ul style="text-align: left; font-size: 16px;">
      <li>完全制御</li>
      <li>カスタマイズ可能</li>
      <li>開発環境向け</li>
      <li>無料</li>
    </ul>
  </div>
</div>

---

# Docker での導入例

<div style="display: flex; justify-content: center; margin: 1em 0;">
  <div style="width: 90%; background-color: #f8f9fa; padding: 1.5em; border-radius: 8px; font-family: monospace;">
    <div style="margin-bottom: 1.5em; border-left: 4px solid #2563EB; padding-left: 1em;">
      <p style="color: #555; margin-bottom: 0.3em; font-weight: bold;">docker-compose.yml:</p>
      <div class="code-example">
```yaml
version: '3.8'
services:
  n8n:
    image: n8nio/n8n
    ports:
      - "5678:5678"
    environment:
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=password
    volumes:
      - n8n_data:/home/node/.n8n
volumes:
  n8n_data:
````

      </div>
    </div>

  </div>
</div>

<div style="margin-top: 1em;">
  <h3>起動コマンド</h3>
  <div class="code-example">
    docker-compose up -d
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

<div style="display: flex; justify-content: space-between; align-items: flex-start;">
  <div style="width: 50%;">
    <h3>🏗️ 設計原則</h3>
    <ul>
      <li><strong>単一責任</strong> - 1つのノードに1つの機能</li>
      <li><strong>エラーハンドリング</strong> - 例外処理の実装</li>
      <li><strong>ログ記録</strong> - 実行履歴の保存</li>
      <li><strong>バージョン管理</strong> - 変更履歴の追跡</li>
    </ul>
    
    <h3>🔒 セキュリティ</h3>
    <ul>
      <li>機密情報の暗号化</li>
      <li>アクセス権限の最小化</li>
      <li>定期的なセキュリティ監査</li>
      <li>セキュリティパッチの適用</li>
    </ul>
  </div>
  
  <div style="width: 45%;">
    <h3>📈 運用管理</h3>
    <ul>
      <li><strong>監視体制</strong> - 24/7監視の構築</li>
      <li><strong>バックアップ</strong> - 定期的なデータバックアップ</li>
      <li><strong>障害対応</strong> - インシデント対応手順</li>
      <li><strong>更新管理</strong> - 定期的なアップデート</li>
    </ul>
    
    <h3>👥 チーム協働</h3>
    <ul>
      <li>ドキュメント整備</li>
      <li>コードレビュー</li>
      <li>知識共有</li>
      <li>継続的改善</li>
    </ul>
  </div>
</div>

---

# 14. 企業導入事例

<div style="display: flex; justify-content: space-between; align-items: flex-start;">
  <div style="width: 50%;">
    <h3>🏢 製造業での活用</h3>
    <ul>
      <li><strong>在庫管理自動化</strong> - リアルタイム在庫追跡</li>
      <li><strong>品質管理</strong> - 検査データの自動収集</li>
      <li><strong>サプライチェーン</strong> - 発注・配送の自動化</li>
      <li><strong>設備監視</strong> - IoTセンサーとの連携</li>
    </ul>
    
    <h3>🏥 医療・ヘルスケア</h3>
    <ul>
      <li>患者データの自動同期</li>
      <li>予約システムの連携</li>
      <li>医療機器の監視</li>
      <li>コンプライアンス管理</li>
    </ul>
  </div>
  
  <div style="width: 45%;">
    <h3>🏦 金融・保険</h3>
    <ul>
      <li><strong>リスク管理</strong> - リアルタイム監視</li>
      <li><strong>コンプライアンス</strong> - 規制対応の自動化</li>
      <li><strong>顧客サービス</strong> - 問い合わせ対応</li>
      <li><strong>不正検知</strong> - 異常検知システム</li>
    </ul>
    
    <h3>🛍️ 小売・Eコマース</h3>
    <ul>
      <li>在庫・価格の自動更新</li>
      <li>顧客行動分析</li>
      <li>マーケティング自動化</li>
      <li>配送・物流の最適化</li>
    </ul>
  </div>
</div>

---

# 導入効果の測定

<div style="display: flex; justify-content: center; margin: 1em 0;">
  <div style="width: 90%; background-color: #f8f9fa; padding: 1.5em; border-radius: 8px;">
    <h3>📊 定量的効果</h3>
    <div style="display: flex; justify-content: space-around; margin: 2em 0;">
      <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
        <h4>時間短縮</h4>
        <p style="font-size: 18px; color: #2563EB; font-weight: bold;">80%</p>
        <p style="font-size: 14px;">手作業の削減</p>
      </div>
      <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
        <h4>エラー削減</h4>
        <p style="font-size: 18px; color: #2563EB; font-weight: bold;">95%</p>
        <p style="font-size: 14px;">人的ミスの削減</p>
      </div>
      <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
        <h4>コスト削減</h4>
        <p style="font-size: 18px; color: #2563EB; font-weight: bold;">60%</p>
        <p style="font-size: 14px;">運用コストの削減</p>
      </div>
      <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
        <h4>ROI向上</h4>
        <p style="font-size: 18px; color: #2563EB; font-weight: bold;">300%</p>
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

<div style="display: flex; justify-content: space-between; align-items: flex-start;">
  <div style="width: 50%;">
    <h3>🌐 公式リソース</h3>
    <ul>
      <li><strong>ドキュメント</strong> - 詳細な技術文書</li>
      <li><strong>チュートリアル</strong> - ステップバイステップ</li>
      <li><strong>API リファレンス</strong> - 開発者向け</li>
      <li><strong>サンプルワークフロー</strong> - 実用例</li>
    </ul>
    
    <h3>🎓 学習コース</h3>
    <ul>
      <li><strong>ビデオコース</strong> - 初心者・上級者向け</li>
      <li><strong>テキストコース</strong> - 実践的な学習</li>
      <li><strong>認定プログラム</strong> - スキル証明</li>
    </ul>
  </div>
  
  <div style="width: 45%;">
    <h3>👥 コミュニティ</h3>
    <ul>
      <li><strong>フォーラム</strong> - 質問・回答</li>
      <li><strong>GitHub</strong> - 開発・バグ報告</li>
      <li><strong>Discord</strong> - リアルタイム交流</li>
      <li><strong>ブログ</strong> - 最新情報</li>
    </ul>
    
    <h3>🛠️ 開発支援</h3>
    <ul>
      <li><strong>カスタムノード</strong> - コミュニティ開発</li>
      <li><strong>プラグイン</strong> - 機能拡張</li>
      <li><strong>テーマ</strong> - UIカスタマイズ</li>
    </ul>
  </div>
</div>

---

# 学習パス

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

---

# 16. 今後の展望とまとめ

<div style="display: flex; justify-content: space-around; margin: 2em 0;">
  <div style="width: 45%;">
    <h3 style="color: #2563EB; margin-bottom: 1em;">🚀 技術発展</h3>
    <ul>
      <li>AI機能の強化</li>
      <li>リアルタイム処理</li>
      <li>エッジコンピューティング</li>
      <li>ブロックチェーン統合</li>
      <li>IoTデバイス連携</li>
    </ul>
  </div>

  <div style="width: 45%;">
    <h3 style="color: #e34c26; margin-bottom: 1em;">📈 市場動向</h3>
    <ul>
      <li>自動化需要の増加</li>
      <li>ノーコード/ローコードの普及</li>
      <li>企業のDX推進</li>
      <li>クラウドネイティブ化</li>
      <li>セキュリティ強化</li>
    </ul>
  </div>
</div>

<div class="highlight-box">
  <strong>n8nの価値:</strong> プライバシー重視、高度なカスタマイズ、豊富な統合、活発なコミュニティ
</div>

---

# n8n の核心価値

<div style="display: flex; justify-content: center; margin: 1em 0 2em 0;">
  <div style="width: 90%; background-color: #f0f7ff; padding: 1.5em; border-radius: 8px; box-shadow: 0 2px 6px rgba(0,0,0,0.1);">
    <ul style="list-style-type: none; padding-left: 0;">
      <li style="margin-bottom: 1em; display: flex; align-items: center;">
        <span style="background-color: #2563EB; color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">1</span>
        <span><strong>Fair-codeライセンス</strong> - プライバシーと制御の両立</span>
      </li>
      <li style="margin-bottom: 1em; display: flex; align-items: center;">
        <span style="background-color: #2563EB; color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">2</span>
        <span><strong>高度なカスタマイズ</strong> - 企業固有のニーズに対応</span>
      </li>
      <li style="margin-bottom: 1em; display: flex; align-items: center;">
        <span style="background-color: #2563EB; color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">3</span>
        <span><strong>豊富な統合</strong> - 400+のノードで幅広い連携</span>
      </li>
      <li style="display: flex; align-items: center;">
        <span style="background-color: #2563EB; color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">4</span>
        <span><strong>活発なコミュニティ</strong> - 継続的な発展と支援</span>
      </li>
    </ul>
  </div>
</div>

<div style="text-align: center; margin-top: 3em;">
  <p style="font-size: 28px; font-weight: bold; color: #2563EB;">n8nでワークフロー自動化の未来を創造しよう</p>
</div>

---

<div style="display: flex; justify-content: center; align-items: center; height: 70vh;">
  <div style="text-align: center;">
    <h2 style="font-size: 36px; margin-bottom: 1em; color: #2563EB;">Questions?</h2>
    <img src="https://cdn-icons-png.flaticon.com/512/6295/6295417.png" alt="Questions" style="width: 150px; margin: 0 auto;">
  </div>
</div>
