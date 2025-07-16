---
marp: true
theme: default
paginate: true
lang: "ja"
footer: "©2025 n8n実践編勉強会 - 自動化ワークフロー構築"
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

  ul ul, ul ol, ol ul, ol ol {
    font-size: 20px;
    margin-top: 0.3em;
    margin-bottom: 0.3em;
    color: var(--rp-subtle);
  }

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

  /* ハイライトボックスのスタイル */
  .highlight-box {
    background: linear-gradient(135deg, var(--rp-highlight-low) 0%, var(--rp-overlay) 100%);
    border-left: 4px solid var(--rp-iris);
    padding: 1.5em;
    border-radius: 8px;
    margin: 1em 0;
    box-shadow: 0 4px 12px rgba(0,0,0,0.2);
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

  /* 強調テキスト */
  strong {
    color: var(--rp-gold);
  }

  /* リストマーカー */
  ul li::marker {
    color: var(--rp-iris);
  }

  ol li::marker {
    color: var(--rp-foam);
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

  /* グリッドレイアウト */
  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5em;
    margin: 1em 0;
  }

  .grid-3 {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1em;
    margin: 1em 0;
  }

  .grid-4 {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 0.8em;
    margin: 1em 0;
  }
---

<!-- タイトルスライド -->

# <span>n8n 実践編</span>

## 自動化ワークフロー構築マスタークラス

<!-- _class: title-slide -->

---

# 目次

## Part 1: 基礎とワークフロー

<div class="card animated">
  <ol>
    <li><strong>基礎知識の確認</strong> - n8nの概要・UI・特徴</li>
    <li><strong>ワークフローの基本</strong> - 作成方法・ノード・実行モード</li>
    <li><strong>Credential管理</strong> - 認証情報の安全な管理</li>
    <li><strong>Slack連携の実装</strong> - メッセージ・チャンネル・ファイル操作</li>
  </ol>
</div>

---

# 目次

## Part 2: データ処理と高度な機能

<div class="card animated">
  <ol start="5">
    <li><strong>Structured Outputの活用</strong> - JSONスキーマ・バリデーション</li>
    <li><strong>PineconeによるRAG</strong> - ベクトル検索・LLM連携</li>
    <li><strong>エラーハンドリング</strong> - デバッグ・最適化</li>
    <li><strong>実用的なワークフロー例</strong> - 具体的な実装例</li>
  </ol>
</div>

---

# 目次

## Part 3: 運用と応用

<div class="card animated">
  <ol start="9">
    <li><strong>運用とメンテナンス</strong> - 管理・バックアップ・セキュリティ</li>
    <li><strong>応用テクニック</strong> - 条件分岐・ループ・カスタム関数</li>
    <li><strong>実践ワークショップ</strong> - ハンズオン・Q&A</li>
    <li><strong>まとめと今後の学習方針</strong> - 振り返り・参考資料</li>
  </ol>
</div>

---

# 1. 基礎知識の確認

## 1.1 n8n とは何か（簡単な復習）

<div class="card animated">
  <h3>🔧 n8nの基本概念</h3>
  
  <div class="grid-2">
    <div>
      <h4>n8nとは</h4>
      <ul>
        <li><strong>Node-based automation tool</strong></li>
        <li><strong>視覚的なワークフロー作成</li>
        <li>200+ のサービス連携</li>
        <li>オープンソース</li>
        <li>セルフホスト可能</li>
      </ul>
    </div>
    <div>
      <h4>主要な用途</h4>
      <ul>
        <li><strong>API連携</strong> - サービス間のデータ転送</li>
        <li><strong>データ処理</strong> - 変換・集計・分析</li>
        <li><strong>通知システム</strong> - アラート・レポート</li>
        <li><strong>業務自動化</strong> - 反復作業の自動化</li>
      </ul>
    </div>
  </div>
</div>

---

## 1.2 n8n の特徴と利点

<div class="card animated">
  <h3>⭐ n8nの強み</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🎨 視覚的操作</h4>
      <ul style="font-size: 0.9em;">
        <li>ドラッグ&ドロップ</li>
        <li>フローチャート形式</li>
        <li>直感的なUI</li>
        <li>コードレス開発</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">🔌 豊富な連携</h4>
      <ul style="font-size: 0.9em;">
        <li>200+ プリビルトノード</li>
        <li>REST API対応</li>
        <li>Webhook対応</li>
        <li>カスタムノード作成可能</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">🛡️ セキュリティ</h4>
      <ul style="font-size: 0.9em;">
        <li>セルフホスト可能</li>
        <li>データ暗号化</li>
        <li>権限管理</li>
        <li>監査ログ</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🆚 他のツールとの比較</h3>
  
  <div style="display: flex; justify-content: center; margin: 20px 0;">
    <div style="overflow-x: auto; max-width: 100%;">
      <table style="width: 100%;">
        <thead>
          <tr>
            <th>特徴</th>
            <th>n8n</th>
            <th>Zapier</th>
            <th>Power Automate</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>料金</strong></td>
            <td>オープンソース / 有料プラン</td>
            <td>有料プランのみ</td>
            <td>Microsoft 365連携</td>
          </tr>
          <tr>
            <td><strong>セルフホスト</strong></td>
            <td>✅ 可能</td>
            <td>❌ 不可</td>
            <td>❌ 不可</td>
          </tr>
          <tr>
            <td><strong>カスタマイズ性</strong></td>
            <td>✅ 高い</td>
            <td>⚠️ 限定的</td>
            <td>⚠️ 中程度</td>
          </tr>
          <tr>
            <td><strong>学習コスト</strong></td>
            <td>⚠️ 中程度</td>
            <td>✅ 低い</td>
            <td>⚠️ 中程度</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

---

## 1.3 UI 概要とナビゲーション

<div class="card animated">
  <h3>🖥️ n8n UI の構成</h3>
  
  <div class="grid-2">
    <div>
      <h4>メイン画面の要素</h4>
      <ul>
        <li><strong>左サイドバー</strong>
          <ul>
            <li>ワークフロー一覧</li>
            <li>Credentials</li>
            <li>Executions</li>
            <li>Settings</li>
          </ul>
        </li>
        <li><strong>中央エリア</strong>
          <ul>
            <li>キャンバス（ワークフロー編集）</li>
            <li>ノード配置・接続</li>
          </ul>
        </li>
      </ul>
    </div>
    <div>
      <h4>右パネルの機能</h4>
      <ul>
        <li><strong>ノード設定</strong>
          <ul>
            <li>パラメータ設定</li>
            <li>認証情報選択</li>
            <li>テスト実行</li>
          </ul>
        </li>
        <li><strong>データビューア</strong>
          <ul>
            <li>入力データ確認</li>
            <li>出力データ確認</li>
            <li>JSON表示</li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🎛️ 重要なナビゲーション機能</h3>
  
  <div class="grid-2">
    <div>
      <h4>キーボードショートカット</h4>
      <div class="code-example" style="font-size: 0.8em;">
Ctrl + S     # 保存
Ctrl + Z     # 元に戻す
Ctrl + Y     # やり直し
Delete       # ノード削除
Ctrl + A     # 全選択
Ctrl + C/V   # コピー&ペースト
Space        # ノード追加
Tab          # ノード検索
      </div>
    </div>
    <div>
      <h4>便利な機能</h4>
      <ul>
        <li><strong>ズーム機能</strong> - マウスホイール</li>
        <li><strong>パン機能</strong> - 中クリック + ドラッグ</li>
        <li><strong>選択範囲</strong> - Shift + ドラッグ</li>
        <li><strong>接続線</strong> - ドラッグで接続</li>
        <li><strong>ノード複製</strong> - Ctrl + ドラッグ</li>
        <li><strong>グリッドスナップ</strong> - 整列機能</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>💡 効率的な作業のコツ</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🔍 検索活用</h4>
      <ul style="font-size: 0.9em;">
        <li>Tabキーでノード検索</li>
        <li>カテゴリ別フィルタ</li>
        <li>よく使うノードをブックマーク</li>
        <li>テンプレート活用</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">📋 整理整頓</h4>
      <ul style="font-size: 0.9em;">
        <li>ノードに分かりやすい名前</li>
        <li>Sticky Noteでコメント</li>
        <li>グループ化で見やすく</li>
        <li>一貫したレイアウト</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">🔄 効率化</h4>
      <ul style="font-size: 0.9em;">
        <li>テンプレート保存</li>
        <li>よく使う設定を複製</li>
        <li>実行履歴を活用</li>
        <li>エラーログを確認</li>
      </ul>
    </div>
  </div>
</div>

---

# 2. ワークフローの基本

## 2.1 ワークフローの作成方法

<div class="card animated">
  <h3>🏗️ ワークフロー作成の基本手順</h3>
  
  <div class="grid-2">
    <div>
      <h4>作成手順</h4>
      <ol>
        <li><strong>新規ワークフロー作成</strong> - "New Workflow"ボタン</li>
        <li><strong>トリガーノード追加</strong> - 開始点の設定</li>
        <li><strong>アクションノード追加</strong> - 処理内容の定義</li>
        <li><strong>ノード接続</strong> - データフローの構築</li>
        <li><strong>設定とテスト</strong> - パラメータ設定と動作確認</li>
        <li><strong>保存とアクティブ化</strong> - 本番運用開始</li>
      </ol>
    </div>
    <div>
      <h4>ワークフロー設計のポイント</h4>
      <ul>
        <li><strong>目的の明確化</strong> - 何を自動化するか</li>
        <li><strong>データフローの設計</strong> - 入力から出力まで</li>
        <li><strong>エラーハンドリング</strong> - 失敗時の対応</li>
        <li><strong>テスト戦略</strong> - 段階的な検証</li>
        <li><strong>ドキュメント化</strong> - 後で理解できるように</li>
      </ul>
    </div>
  </div>
</div>

---

## 2.2 ノードの種類と役割

<div class="card animated">
  <h3>🔗 ノードの分類</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🚀 トリガーノード</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>Manual Trigger</strong> - 手動実行</li>
        <li><strong>Webhook</strong> - HTTP リクエスト受信</li>
        <li><strong>Schedule Trigger</strong> - 時間ベース実行</li>
        <li><strong>Email Trigger</strong> - メール受信</li>
        <li><strong>File Trigger</strong> - ファイル変更監視</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">⚡ アクションノード</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>HTTP Request</strong> - API呼び出し</li>
        <li><strong>Email</strong> - メール送信</li>
        <li><strong>Slack</strong> - Slack操作</li>
        <li><strong>Google Sheets</strong> - スプレッドシート操作</li>
        <li><strong>Database</strong> - DB操作</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">🔧 処理ノード</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>Set</strong> - データ設定・変換</li>
        <li><strong>Code</strong> - JavaScript実行</li>
        <li><strong>IF</strong> - 条件分岐</li>
        <li><strong>Switch</strong> - 多分岐</li>
        <li><strong>Loop</strong> - 繰り返し処理</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🎯 よく使用されるノード詳細</h3>
  
  <div style="display: flex; justify-content: center; margin: 20px 0;">
    <div style="overflow-x: auto; max-width: 100%;">
      <table style="width: 100%;">
        <thead>
          <tr>
            <th>ノード名</th>
            <th>主な用途</th>
            <th>設定のポイント</th>
            <th>使用例</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>Manual Trigger</strong></td>
            <td>手動実行・テスト</td>
            <td>シンプルな設定</td>
            <td>開発・デバッグ時</td>
          </tr>
          <tr>
            <td><strong>HTTP Request</strong></td>
            <td>API呼び出し</td>
            <td>URL・メソッド・認証</td>
            <td>外部サービス連携</td>
          </tr>
          <tr>
            <td><strong>Set</strong></td>
            <td>データ変換・設定</td>
            <td>フィールドマッピング</td>
            <td>データ整形</td>
          </tr>
          <tr>
            <td><strong>IF</strong></td>
            <td>条件分岐</td>
            <td>条件式の設定</td>
            <td>データによる処理切り替え</td>
          </tr>
          <tr>
            <td><strong>Code</strong></td>
            <td>複雑な処理</td>
            <td>JavaScript記述</td>
            <td>カスタムロジック実装</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

---

## 2.3 データフローの理解

<div class="card animated">
  <h3>🌊 データの流れ</h3>
  
  <div class="grid-2">
    <div>
      <h4>データ構造の基本</h4>
      <ul>
        <li><strong>JSON形式</strong> - 全てのデータはJSONで流れる</li>
        <li><strong>アイテム単位</strong> - 配列の各要素が一つのアイテム</li>
        <li><strong>フィールド</strong> - アイテム内のプロパティ</li>
        <li><strong>メタデータ</strong> - 実行に関する情報</li>
      </ul>
    </div>
    <div>
      <h4>データ例</h4>
      <div class="code-example" style="font-size: 0.7em;">
[
  {
    "id": 1,
    "name": "John Doe",
    "email": "john@example.com",
    "created_at": "2024-01-01T00:00:00Z"
  },
  {
    "id": 2,
    "name": "Jane Smith", 
    "email": "jane@example.com",
    "created_at": "2024-01-02T00:00:00Z"
  }
]
      </div>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>📊 データ参照方法</h3>
  
  <div class="grid-2">
    <div>
      <h4>式エディタの使用</h4>
      <ul>
        <li><strong>{{ }}</strong> - 式の記述</li>
        <li><strong>$json</strong> - 現在のJSONデータ</li>
        <li><strong>$node</strong> - 特定ノードのデータ</li>
        <li><strong>$parameter</strong> - パラメータ値</li>
        <li><strong>$workflow</strong> - ワークフロー情報</li>
      </ul>
    </div>
    <div>
      <h4>実際の使用例</h4>
      <div class="code-example" style="font-size: 0.7em;">
# 現在のデータから名前取得
{{ $json.name }}

# 前のノードのデータ参照

{{ $node["HTTP Request"].json.data }}

# 条件式での使用

{{ $json.age > 18 }}

# 複数データの結合

{{ $json.firstName + " " + $json.lastName }}

# 配列の処理

{{ $json.items.length }}

</div>
</div>

  </div>
</div>

---

## 2.4 実行モード（Manual、Trigger、Webhook）

<div class="card animated">
  <h3>🔄 実行モードの種類</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🖱️ Manual（手動）</h4>
      <ul style="font-size: 0.9em;">
        <li>開発・テスト時に使用</li>
        <li>即座に実行される</li>
        <li>デバッグに最適</li>
        <li>Manual Triggerノード使用</li>
      </ul>
      <div class="highlight-box" style="font-size: 0.8em;">
        <strong>使用場面</strong>: ワークフロー開発・動作確認・一回限りの処理
      </div>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">⏰ Trigger（定期実行）</h4>
      <ul style="font-size: 0.9em;">
        <li>スケジュールに基づく実行</li>
        <li>Cron式での設定</li>
        <li>定期的なデータ処理</li>
        <li>Schedule Triggerノード使用</li>
      </ul>
      <div class="highlight-box" style="font-size: 0.8em;">
        <strong>使用場面</strong>: 日次レポート・データ同期・ヘルスチェック
      </div>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">🔗 Webhook（イベント駆動）</h4>
      <ul style="font-size: 0.9em;">
        <li>外部からのHTTP リクエスト</li>
        <li>リアルタイム処理</li>
        <li>イベント駆動型</li>
        <li>Webhookノード使用</li>
      </ul>
      <div class="highlight-box" style="font-size: 0.8em;">
        <strong>使用場面</strong>: フォーム送信処理・API連携・通知システム
      </div>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>⚙️ 実行モードの設定詳細</h3>
  
  <div class="grid-2">
    <div>
      <h4>Schedule Trigger設定例</h4>
      <div class="code-example" style="font-size: 0.8em;">
# 毎日午前9時に実行
0 9 * * *

# 毎週月曜日の午前 10 時

0 10 \* \* 1

# 毎月 1 日の午後 2 時

0 14 1 \* \*

# 平日の毎時 0 分（営業時間内）

0 9-17 \* \* 1-5

</div>
</div>
<div>
<h4>Webhook 設定のポイント</h4>
<ul>
<li><strong>URL パス</strong> - ユニークなパス設定</li>
<li><strong>HTTP メソッド</strong> - GET/POST 等の選択</li>
<li><strong>認証</strong> - セキュリティ設定</li>
<li><strong>レスポンス</strong> - 返却データの設定</li>
</ul>
<div class="code-example" style="font-size: 0.7em;">

# Webhook URL 例

https://your-n8n.com/webhook/user-signup
https://your-n8n.com/webhook/payment-completed

</div>
</div>

  </div>
</div>

---

## 2.5 デバッグとテストの方法

<div class="card animated">
  <h3>🐛 効果的なデバッグ手法</h3>
  
  <div class="grid-2">
    <div>
      <h4>デバッグの基本手順</h4>
      <ol>
        <li><strong>単体テスト</strong> - 各ノードを個別にテスト</li>
        <li><strong>データ確認</strong> - 各段階でのデータ状態確認</li>
        <li><strong>エラーログ確認</strong> - 詳細なエラー情報の分析</li>
        <li><strong>段階的実行</strong> - 部分的にワークフローを実行</li>
        <li><strong>本番テスト</strong> - 実環境での動作確認</li>
      </ol>
    </div>
    <div>
      <h4>デバッグツールの活用</h4>
      <ul>
        <li><strong>Execute Node</strong> - 単一ノードの実行</li>
        <li><strong>Pin Data</strong> - テストデータの固定</li>
        <li><strong>Execution Log</strong> - 実行履歴の確認</li>
        <li><strong>JSON Viewer</strong> - データ構造の視覚化</li>
        <li><strong>Error Information</strong> - エラーの詳細情報</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🔍 よくあるエラーと対処法</h3>
  
  <div style="display: flex; justify-content: center; margin: 20px 0;">
    <div style="overflow-x: auto; max-width: 100%;">
      <table style="width: 100%;">
        <thead>
          <tr>
            <th>エラータイプ</th>
            <th>よくある原因</th>
            <th>確認方法</th>
            <th>対処法</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>接続エラー</strong></td>
            <td>認証情報の不備</td>
            <td>Credential設定確認</td>
            <td>正しい認証情報を設定</td>
          </tr>
          <tr>
            <td><strong>データエラー</strong></td>
            <td>フィールド参照ミス</td>
            <td>JSON構造の確認</td>
            <td>正しいパス指定</td>
          </tr>
          <tr>
            <td><strong>タイムアウト</strong></td>
            <td>処理時間超過</td>
            <td>実行時間確認</td>
            <td>タイムアウト値調整</td>
          </tr>
          <tr>
            <td><strong>レート制限</strong></td>
            <td>API呼び出し過多</td>
            <td>API制限値確認</td>
            <td>Waitノード追加</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>📈 パフォーマンステスト</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">⚡ 実行時間測定</h4>
      <ul style="font-size: 0.9em;">
        <li>各ノードの処理時間</li>
        <li>全体の実行時間</li>
        <li>ボトルネックの特定</li>
        <li>最適化ポイントの発見</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">📊 リソース使用量</h4>
      <ul style="font-size: 0.9em;">
        <li>メモリ使用量</li>
        <li>CPU使用率</li>
        <li>ネットワーク使用量</li>
        <li>ストレージ使用量</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">🔧 最適化手法</h4>
      <ul style="font-size: 0.9em;">
        <li>並列処理の活用</li>
        <li>データ量の制限</li>
        <li>キャッシュの活用</li>
        <li>不要な処理の削除</li>
      </ul>
    </div>
  </div>
</div>

---

# 3. Credential（認証情報）の管理

## 3.1 Credential とは何か

<div class="card animated">
  <h3>🔐 Credentialの基本概念</h3>
  
  <div class="grid-2">
    <div>
      <h4>Credentialとは</h4>
      <ul>
        <li><strong>認証情報の集約管理</strong> - API キー、トークン、パスワード</li>
        <li><strong>セキュアな保存</strong> - 暗号化されて保管</li>
        <li><strong>再利用可能</strong> - 複数のワークフローで共有</li>
        <li><strong>権限管理</strong> - ユーザーごとのアクセス制御</li>
      </ul>
    </div>
    <div>
      <h4>なぜCredentialが重要なのか</h4>
      <ul>
        <li><strong>セキュリティ</strong> - 機密情報の安全な管理</li>
        <li><strong>効率性</strong> - 一度設定すれば再利用可能</li>
        <li><strong>メンテナンス性</strong> - 一箇所で更新すれば全体に反映</li>
        <li><strong>監査性</strong> - アクセス履歴の追跡</li>
      </ul>
    </div>
  </div>
</div>

---

## 3.2 各種サービスの Credential 設定方法

<div class="card animated">
  <h3>🌐 主要サービスのCredential設定</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🔑 API Key型</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>OpenAI</strong> - API Key</li>
        <li><strong>Slack</strong> - Bot User OAuth Token</li>
        <li><strong>SendGrid</strong> - API Key</li>
        <li><strong>Pinecone</strong> - API Key</li>
      </ul>
      <div class="code-example" style="font-size: 0.7em;">
# 設定例
API Key: sk-xxx...xxx
Environment: production
      </div>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">🔄 OAuth2型</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>Google Sheets</strong> - OAuth2</li>
        <li><strong>Microsoft 365</strong> - OAuth2</li>
        <li><strong>GitHub</strong> - OAuth2</li>
        <li><strong>Salesforce</strong> - OAuth2</li>
      </ul>
      <div class="code-example" style="font-size: 0.7em;">
# 設定項目
Client ID: your-client-id
Client Secret: your-secret
Scope: read,write
      </div>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">🔐 Basic認証型</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>HTTP Basic Auth</strong></li>
        <li><strong>Legacy APIs</strong></li>
        <li><strong>Internal Systems</strong></li>
        <li><strong>Database接続</strong></li>
      </ul>
      <div class="code-example" style="font-size: 0.7em;">
# 設定例
Username: admin
Password: secure-password
Host: api.example.com
      </div>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>⚙️ Credential設定の実践手順</h3>
  
  <div class="grid-2">
    <div>
      <h4>設定手順</h4>
      <ol>
        <li><strong>Credentialsメニューを開く</strong></li>
        <li><strong>"Add Credential"をクリック</strong></li>
        <li><strong>サービスタイプを選択</strong></li>
        <li><strong>必要な情報を入力</strong></li>
        <li><strong>接続テストを実行</strong></li>
        <li><strong>保存して完了</strong></li>
      </ol>
    </div>
    <div>
      <h4>設定時の注意点</h4>
      <ul>
        <li><strong>正確な情報入力</strong> - スペースや改行に注意</li>
        <li><strong>権限スコープ</strong> - 必要最小限の権限設定</li>
        <li><strong>有効期限確認</strong> - トークンの更新時期</li>
        <li><strong>テスト実行</strong> - 設定後は必ず動作確認</li>
        <li><strong>命名規則</strong> - 分かりやすい名前付け</li>
      </ul>
    </div>
  </div>
</div>

---

## 3.3 セキュリティのベストプラクティス

<div class="card animated">
  <h3>🛡️ セキュリティ対策</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🔒 アクセス制御</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>最小権限の原則</strong></li>
        <li><strong>役割ベースのアクセス</strong></li>
        <li><strong>定期的な権限見直し</strong></li>
        <li><strong>不要な権限の削除</strong></li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">🔄 定期メンテナンス</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>定期的なローテーション</strong></li>
        <li><strong>有効期限の管理</strong></li>
        <li><strong>未使用認証情報の削除</strong></li>
        <li><strong>セキュリティログの監視</strong></li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">📊 監査とモニタリング</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>アクセスログの記録</strong></li>
        <li><strong>異常検知アラート</strong></li>
        <li><strong>使用状況の監視</strong></li>
        <li><strong>コンプライアンス確認</strong></li>
      </ul>
    </div>
  </div>
</div>

---

## 3.4 環境変数との連携

<div class="card animated">
  <h3>🌍 環境変数を活用したCredential管理</h3>
  
  <div class="grid-2">
    <div>
      <h4>環境変数の利点</h4>
      <ul>
        <li><strong>環境分離</strong> - 開発/本番環境の切り分け</li>
        <li><strong>セキュリティ</strong> - コードに機密情報を含めない</li>
        <li><strong>柔軟性</strong> - デプロイ時の設定変更が容易</li>
        <li><strong>チーム開発</strong> - 個人の認証情報管理</li>
      </ul>
    </div>
    <div>
      <h4>設定例</h4>
      <div class="code-example" style="font-size: 0.8em;">
# 環境変数設定
export OPENAI_API_KEY="sk-xxx...xxx"
export SLACK_BOT_TOKEN="xoxb-xxx...xxx"
export DATABASE_URL="postgresql://..."

# n8n での参照

{{ $env.OPENAI_API_KEY }}
{{ $env.SLACK_BOT_TOKEN }}
{{ $env.DATABASE_URL }}

</div>
</div>

  </div>
</div>

---

# 4. Slack 連携の実装

## 4.1 Slack Credential の設定

<div class="card animated">
  <h3>🚀 Slack アプリの作成とCredential設定</h3>
  
  <div class="grid-2">
    <div>
      <h4>Slack App作成手順</h4>
      <ol>
        <li><strong>api.slack.com</strong> にアクセス</li>
        <li><strong>"Create New App"</strong> をクリック</li>
        <li><strong>"From scratch"</strong> を選択</li>
        <li><strong>アプリ名とワークスペース</strong> を設定</li>
        <li><strong>"OAuth & Permissions"</strong> で権限設定</li>
        <li><strong>"Install to Workspace"</strong> を実行</li>
        <li><strong>Bot User OAuth Token</strong> をコピー</li>
      </ol>
    </div>
    <div>
      <h4>必要な権限（Scopes）</h4>
      <ul>
        <li><strong>chat:write</strong> - メッセージ送信</li>
        <li><strong>chat:write.public</strong> - パブリックチャンネル投稿</li>
        <li><strong>channels:read</strong> - チャンネル情報取得</li>
        <li><strong>users:read</strong> - ユーザー情報取得</li>
        <li><strong>files:write</strong> - ファイルアップロード</li>
        <li><strong>files:read</strong> - ファイル読み取り</li>
      </ul>
    </div>
  </div>
</div>

---

## 4.2 メッセージ送信の基本

<div class="card animated">
  <h3>💬 Slackメッセージ送信の実装</h3>
  
  <div class="grid-2">
    <div>
      <h4>基本的なメッセージ送信</h4>
      <div class="code-example" style="font-size: 0.8em;">
# シンプルなテキストメッセージ
{
  "channel": "#general",
  "text": "Hello from n8n!"
}

# リッチテキストメッセージ

{
"channel": "#alerts",
"text": "System Alert",
"blocks": [
{
"type": "section",
"text": {
"type": "mrkdwn",
"text": "*Alert:* System maintenance required"
}
}
]
}

</div>
</div>
<div>
<h4>高度なメッセージ機能</h4>
<ul>
<li><strong>Markdown 記法</strong> - _太字_、_斜体_、`コード`</li>
<li><strong>メンション</strong> - @user、@channel</li>
<li><strong>チャンネルリンク</strong> - #channel-name</li>
<li><strong>絵文字</strong> - :smile:、:warning:</li>
<li><strong>URL</strong> - 自動リンク化</li>
<li><strong>コードブロック</strong> - ```でコード整形</li>
</ul>
</div>

  </div>
</div>

---

<div class="card animated">
  <h3>🎨 Block Kit を使用したリッチメッセージ</h3>
  
  <div class="grid-2">
    <div>
      <h4>Block Kit の主要要素</h4>
      <ul>
        <li><strong>Section</strong> - テキストと画像の表示</li>
        <li><strong>Divider</strong> - 区切り線</li>
        <li><strong>Actions</strong> - ボタンやメニュー</li>
        <li><strong>Context</strong> - 補足情報</li>
        <li><strong>Header</strong> - 見出し</li>
        <li><strong>Image</strong> - 画像表示</li>
      </ul>
    </div>
    <div>
      <h4>実装例</h4>
      <div class="code-example" style="font-size: 0.7em;">
{
  "blocks": [
    {
      "type": "header",
      "text": {
        "type": "plain_text",
        "text": "🚨 System Alert"
      }
    },
    {
      "type": "section",
      "text": {
        "type": "mrkdwn",
        "text": "*Status:* Critical\n*Time:* {{ $now }}"
      }
    },
    {
      "type": "actions",
      "elements": [
        {
          "type": "button",
          "text": {
            "type": "plain_text",
            "text": "Acknowledge"
          },
          "value": "ack",
          "action_id": "acknowledge"
        }
      ]
    }
  ]
}
      </div>
    </div>
  </div>
</div>

---

## 4.3 チャンネル操作

<div class="card animated">
  <h3>📢 チャンネルの管理と操作</h3>
  
  <div class="grid-2">
    <div>
      <h4>チャンネル関連の操作</h4>
      <ul>
        <li><strong>チャンネル一覧取得</strong> - conversations.list</li>
        <li><strong>チャンネル作成</strong> - conversations.create</li>
        <li><strong>チャンネル情報取得</strong> - conversations.info</li>
        <li><strong>メンバー管理</strong> - conversations.invite</li>
        <li><strong>履歴取得</strong> - conversations.history</li>
      </ul>
    </div>
    <div>
      <h4>実装例</h4>
      <div class="code-example" style="font-size: 0.8em;">
# チャンネル作成
{
  "name": "project-alerts",
  "is_private": false
}

# メンバー招待

{
"channel": "C1234567890",
"users": "U1234567890,U0987654321"
}

# 履歴取得

{
"channel": "C1234567890",
"limit": 100,
"oldest": "1234567890.123456"
}

</div>
</div>

  </div>
</div>

---

## 4.4 ファイルアップロード

<div class="card animated">
  <h3>📎 ファイル共有とアップロード</h3>
  
  <div class="grid-2">
    <div>
      <h4>ファイルアップロードの方法</h4>
      <ul>
        <li><strong>直接アップロード</strong> - ローカルファイルから</li>
        <li><strong>URL指定</strong> - 外部URLから取得</li>
        <li><strong>Base64データ</strong> - エンコードされたデータ</li>
        <li><strong>生成ファイル</strong> - n8nで作成したファイル</li>
      </ul>
    </div>
    <div>
      <h4>対応ファイル形式</h4>
      <ul>
        <li><strong>画像</strong> - JPG、PNG、GIF、SVG</li>
        <li><strong>ドキュメント</strong> - PDF、DOC、XLS、PPT</li>
        <li><strong>テキスト</strong> - TXT、CSV、JSON、XML</li>
        <li><strong>アーカイブ</strong> - ZIP、RAR、TAR</li>
        <li><strong>動画・音声</strong> - MP4、AVI、MP3</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>💾 ファイルアップロード実装例</h3>
  
  <div class="grid-2">
    <div>
      <h4>CSVレポートのアップロード</h4>
      <div class="code-example" style="font-size: 0.7em;">
# 1. データをCSV形式に変換（Codeノード）
const csvData = items.map(item => 
  `${item.id},${item.name},${item.date}`
).join('\n');

return [{ json: { csvContent: csvData } }];

# 2. Slack にファイルアップロード

{
"channels": "#reports",
"content": "{{ $json.csvContent }}",
"filename": "daily*report*{{ $now.format('YYYY-MM-DD') }}.csv",
"filetype": "csv",
"title": "Daily Report - {{ $now.format('YYYY/MM/DD') }}"
}

</div>
</div>
<div>
<h4>スクリーンショット共有</h4>
<div class="code-example" style="font-size: 0.7em;">

# 画像 URL からアップロード

{
"channels": "#screenshots",
"file": "https://example.com/screenshot.png",
"filename": "screenshot.png",
"title": "System Status Screenshot",
"initial_comment": "Current system status as of {{ $now }}"
}

# Base64 データから

{
"channels": "#images",
"content": "{{ $binary.data }}",
"filename": "generated_chart.png",
"filetype": "png"
}

</div>
</div>

  </div>
</div>

---

## 4.5 Interactive 要素の活用

<div class="card animated">
  <h3>🎛️ インタラクティブな要素</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🔘 ボタン</h4>
      <ul style="font-size: 0.9em;">
        <li>アクション実行</li>
        <li>承認フロー</li>
        <li>選択肢提示</li>
        <li>外部リンク</li>
      </ul>
      <div class="code-example" style="font-size: 0.6em;">
{
  "type": "button",
  "text": {
    "type": "plain_text",
    "text": "Approve"
  },
  "style": "primary",
  "value": "approve_123"
}
      </div>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">📋 選択メニュー</h4>
      <ul style="font-size: 0.9em;">
        <li>ドロップダウン</li>
        <li>複数選択</li>
        <li>ユーザー選択</li>
        <li>チャンネル選択</li>
      </ul>
      <div class="code-example" style="font-size: 0.6em;">
{
  "type": "static_select",
  "placeholder": {
    "type": "plain_text",
    "text": "Select priority"
  },
  "options": [
    {
      "text": { "type": "plain_text", "text": "High" },
      "value": "high"
    }
  ]
}
      </div>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">📝 入力フィールド</h4>
      <ul style="font-size: 0.9em;">
        <li>テキスト入力</li>
        <li>数値入力</li>
        <li>日付選択</li>
        <li>時刻選択</li>
      </ul>
      <div class="code-example" style="font-size: 0.6em;">
{
  "type": "plain_text_input",
  "placeholder": {
    "type": "plain_text",
    "text": "Enter comment"
  },
  "multiline": true
}
      </div>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🔄 インタラクティブ要素の応答処理</h3>
  
  <div class="grid-2">
    <div>
      <h4>Webhook応答の設定</h4>
      <ul>
        <li><strong>Interactivity Webhook URL</strong> を設定</li>
        <li><strong>Request URL</strong> にn8n Webhook URLを指定</li>
        <li><strong>ペイロード解析</strong> でユーザーアクションを取得</li>
        <li><strong>条件分岐</strong> でアクション別の処理を実装</li>
      </ul>
    </div>
    <div>
      <h4>応答処理の実装例</h4>
      <div class="code-example" style="font-size: 0.7em;">
# Webhookで受信したペイロードの解析
const payload = JSON.parse($json.payload);
const action = payload.actions[0];

// アクションに応じた処理
if (action.action_id === 'approve') {
// 承認処理を実行
return [{ json: { action: 'approve', user: payload.user.id } }];
} else if (action.action_id === 'reject') {
// 拒否処理を実行
return [{ json: { action: 'reject', user: payload.user.id } }];
}

</div>
</div>

  </div>
</div>

---

# 5. Structured Output の活用

## 5.1 Structured Output とは

<div class="card animated">
  <h3>🏗️ Structured Output の概念</h3>
  
  <div class="grid-2">
    <div>
      <h4>Structured Output の特徴</h4>
      <ul>
        <li><strong>構造化されたデータ出力</strong> - 予測可能な形式</li>
        <li><strong>スキーマ定義</strong> - データ構造の事前定義</li>
        <li><strong>バリデーション</strong> - データ整合性の確保</li>
        <li><strong>型安全性</strong> - データ型の保証</li>
        <li><strong>一貫性</strong> - 出力形式の統一</li>
      </ul>
    </div>
    <div>
      <h4>活用場面</h4>
      <ul>
        <li><strong>API レスポンス</strong> - 一貫したデータ形式</li>
        <li><strong>データ変換</strong> - 標準化された変換</li>
        <li><strong>レポート生成</strong> - 定型レポート作成</li>
        <li><strong>システム連携</strong> - データ交換の標準化</li>
        <li><strong>エラーハンドリング</strong> - 予測可能なエラー情報</li>
      </ul>
    </div>
  </div>
</div>

---

## 5.2 JSON スキーマの定義

<div class="card animated">
  <h3>📋 JSON スキーマの作成</h3>
  
  <div class="grid-2">
    <div>
      <h4>基本的なスキーマ構造</h4>
      <div class="code-example" style="font-size: 0.7em;">
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "type": "object",
  "required": ["id", "name", "email"],
  "properties": {
    "id": {
      "type": "integer",
      "minimum": 1
    },
    "name": {
      "type": "string",
      "minLength": 1,
      "maxLength": 100
    },
    "email": {
      "type": "string",
      "format": "email"
    },
    "age": {
      "type": "integer",
      "minimum": 0,
      "maximum": 150
    }
  }
}
      </div>
    </div>
    <div>
      <h4>複雑なスキーマ例</h4>
      <div class="code-example" style="font-size: 0.7em;">
{
  "type": "object",
  "properties": {
    "user": {
      "type": "object",
      "properties": {
        "profile": { "$ref": "#/definitions/Profile" },
        "preferences": {
          "type": "array",
          "items": { "type": "string" }
        }
      }
    }
  },
  "definitions": {
    "Profile": {
      "type": "object",
      "properties": {
        "firstName": { "type": "string" },
        "lastName": { "type": "string" },
        "birthDate": { "type": "string", "format": "date" }
      }
    }
  }
}
      </div>
    </div>
  </div>
</div>

---

## 5.3 データバリデーション

<div class="card animated">
  <h3>✅ バリデーション機能の実装</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🔍 型チェック</h4>
      <ul style="font-size: 0.9em;">
        <li>データ型の検証</li>
        <li>必須フィールドの確認</li>
        <li>形式の検証</li>
        <li>範囲の確認</li>
      </ul>
      <div class="code-example" style="font-size: 0.6em;">
// Code ノードでのバリデーション
const Ajv = require('ajv');
const ajv = new Ajv();

const validate = ajv.compile(schema);
const valid = validate(data);

if (!valid) {
throw new Error(ajv.errorsText(validate.errors));
}

</div>
</div>
<div>
<h4 style="color: var(--rp-foam);">⚠️ エラーハンドリング</h4>
<ul style="font-size: 0.9em;">
<li>詳細なエラーメッセージ</li>
<li>エラー位置の特定</li>
<li>復旧処理の実装</li>
<li>ログ記録</li>
</ul>
<div class="code-example" style="font-size: 0.6em;">
// エラー情報の構造化
{
"valid": false,
"errors": [
{
"field": "email",
"message": "Invalid email format",
"value": "invalid-email"
}
]
}
</div>
</div>
<div>
<h4 style="color: var(--rp-gold);">🔄 自動修正</h4>
<ul style="font-size: 0.9em;">
<li>データの正規化</li>
<li>デフォルト値の設定</li>
<li>フォーマット変換</li>
<li>クリーニング処理</li>
</ul>
<div class="code-example" style="font-size: 0.6em;">
// データの自動修正
if (data.email) {
data.email = data.email.toLowerCase().trim();
}
if (!data.created_at) {
data.created_at = new Date().toISOString();
}
</div>
</div>

  </div>
</div>

---

# 6. Pinecone による RAG システム

## 6.1 Pinecone とは

<div class="card animated">
  <h3>🌲 Pinecone ベクトルデータベースの概要</h3>
  
  <div class="grid-2">
    <div>
      <h4>Pinecone の特徴</h4>
      <ul>
        <li><strong>ベクトル検索</strong> - 高速な類似性検索</li>
        <li><strong>スケーラビリティ</strong> - 大規模データ対応</li>
        <li><strong>マネージドサービス</strong> - インフラ管理不要</li>
        <li><strong>高精度</strong> - 意味的類似性の検索</li>
        <li><strong>リアルタイム</strong> - 即座のインデックス更新</li>
      </ul>
    </div>
    <div>
      <h4>RAG システムでの役割</h4>
      <ul>
        <li><strong>知識ベース</strong> - 文書の埋め込み保存</li>
        <li><strong>文脈検索</strong> - 関連情報の取得</li>
        <li><strong>情報拡張</strong> - LLM への追加情報提供</li>
        <li><strong>精度向上</strong> - 回答の根拠となる情報</li>
        <li><strong>コスト削減</strong> - 効率的な情報取得</li>
      </ul>
    </div>
  </div>
</div>

---

## 6.2 ベクトル検索の実装

<div class="card animated">
  <h3>🔍 ベクトル検索ワークフローの構築</h3>
  
  <div class="grid-2">
    <div>
      <h4>データ準備とインデックス作成</h4>
      <div class="code-example" style="font-size: 0.7em;">
# 1. テキストの埋め込み生成（OpenAI ノード）
{
  "input": "{{ $json.content }}",
  "model": "text-embedding-ada-002"
}

# 2. Pinecone インデックスへの保存

{
"id": "{{ $json.id }}",
"values": "{{ $json.embedding }}",
"metadata": {
"title": "{{ $json.title }}",
"content": "{{ $json.content }}",
"created_at": "{{ $json.created_at }}"
}
}

# 3. バッチ挿入の最適化

{
"vectors": [
{
"id": "doc1",
"values": [0.1, 0.2, ...],
"metadata": {"title": "Document 1"}
}
]
}

</div>
</div>
<div>
<h4>検索クエリの実装</h4>
<div class="code-example" style="font-size: 0.7em;">

# 1. ユーザークエリの埋め込み生成

{
"input": "{{ $json.query }}",
"model": "text-embedding-ada-002"
}

# 2. Pinecone での類似性検索

{
"vector": "{{ json.embedding }}",
"topK": 5,
"includeMetadata": true,
"filter": {
"category": {"$eq": "technical"}
}
}

# 3. 結果のフィルタリングと整形

const results = $json.matches.map(match => ({
score: match.score,
title: match.metadata.title,
content: match.metadata.content
}));

</div>
</div>

  </div>
</div>

---

## 6.3 LLM との連携

<div class="card animated">
  <h3>🤖 RAG システムの完全な実装</h3>
  
  <div class="grid-2">
    <div>
      <h4>コンテキスト生成</h4>
      <div class="code-example" style="font-size: 0.7em;">
// 検索結果からコンテキストを生成
const context = searchResults
  .filter(result => result.score > 0.8)
  .map(result => `Title: ${result.title}\nContent: ${result.content}`)
  .join('\n\n---\n\n');

const prompt = `
Context information:
${context}

Question: ${userQuery}

Please answer the question based on the provided context.
If the answer is not in the context, say "I don't have information about that."
`;

return [{ json: { prompt, context } }];

</div>
</div>
<div>
<h4>回答生成と品質管理</h4>
<div class="code-example" style="font-size: 0.7em;">

# OpenAI ノードでの回答生成

{
"model": "gpt-4",
"messages": [
{
"role": "system",
"content": "You are a helpful assistant. Use only the provided context to answer questions."
},
{
"role": "user",
"content": "{{ $json.prompt }}"
}
],
"temperature": 0.7,
"max_tokens": 500
}

# 回答の品質チェック

const response = $json.choices[0].message.content;
const hasSourceInfo = response.includes("based on") || response.includes("according to");
const confidence = $json.usage.total_tokens < 400 ? "high" : "medium";

</div>
</div>

  </div>
</div>

---

# 7. エラーハンドリングとデバッグ

## 7.1 一般的なエラーの種類と対処法

<div class="card animated">
  <h3>🚨 エラーの分類と対応戦略</h3>
  
  <div style="display: flex; justify-content: center; margin: 20px 0;">
    <div style="overflow-x: auto; max-width: 100%;">
      <table style="width: 100%;">
        <thead>
          <tr>
            <th>エラータイプ</th>
            <th>原因</th>
            <th>症状</th>
            <th>対処法</th>
            <th>予防策</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>認証エラー</strong></td>
            <td>無効な認証情報</td>
            <td>401 Unauthorized</td>
            <td>Credential の再設定</td>
            <td>定期的なトークン更新</td>
          </tr>
          <tr>
            <td><strong>レート制限</strong></td>
            <td>API 呼び出し過多</td>
            <td>429 Too Many Requests</td>
            <td>Wait ノード追加</td>
            <td>呼び出し頻度の調整</td>
          </tr>
          <tr>
            <td><strong>データエラー</strong></td>
            <td>不正なデータ形式</td>
            <td>400 Bad Request</td>
            <td>データバリデーション</td>
            <td>スキーマ検証の実装</td>
          </tr>
          <tr>
            <td><strong>タイムアウト</strong></td>
            <td>処理時間超過</td>
            <td>504 Gateway Timeout</td>
            <td>タイムアウト値調整</td>
            <td>処理の最適化</td>
          </tr>
          <tr>
            <td><strong>ネットワークエラー</strong></td>
            <td>接続の問題</td>
            <td>Connection failed</td>
            <td>リトライ機能実装</td>
            <td>冗長化・監視</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

---

## 7.2 高度なデバッグ手法

<div class="card animated">
  <h3>🔧 効果的なデバッグ戦略</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">📊 ログ活用</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>詳細ログ</strong> - 実行ステップの記録</li>
        <li><strong>エラーログ</strong> - エラー内容の詳細</li>
        <li><strong>パフォーマンスログ</strong> - 実行時間の測定</li>
        <li><strong>カスタムログ</strong> - 独自の情報記録</li>
      </ul>
      <div class="code-example" style="font-size: 0.6em;">
// Code ノードでのログ出力
console.log('Processing item:', $json.id);
console.error('Error occurred:', error.message);
console.time('processing-time');
// 処理実行
console.timeEnd('processing-time');
      </div>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">🔍 データ追跡</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>データフロー可視化</strong> - 各段階のデータ確認</li>
        <li><strong>変数監視</strong> - 変数値の変化追跡</li>
        <li><strong>条件分岐</strong> - 実行パスの確認</li>
        <li><strong>データ変換</strong> - 変換前後の比較</li>
      </ul>
      <div class="code-example" style="font-size: 0.6em;">
// データ追跡用の情報追加
const debugInfo = {
  nodeId: 'data-transform',
  inputData: $input.all(),
  timestamp: new Date().toISOString(),
  executionId: $execution.id
};

return [{ json: { ...processedData, _debug: debugInfo } }];

</div>
</div>
<div>
<h4 style="color: var(--rp-gold);">⚡ パフォーマンス分析</h4>
<ul style="font-size: 0.9em;">
<li><strong>実行時間測定</strong> - ボトルネック特定</li>
<li><strong>メモリ使用量</strong> - リソース監視</li>
<li><strong>API 呼び出し回数</strong> - 効率性評価</li>
<li><strong>並列処理</strong> - 最適化の検討</li>
</ul>
<div class="code-example" style="font-size: 0.6em;">
// パフォーマンス測定
const startTime = Date.now();
const initialMemory = process.memoryUsage();

// 処理実行

const endTime = Date.now();
const finalMemory = process.memoryUsage();

return [{
json: {
executionTime: endTime - startTime,
memoryUsed: finalMemory.heapUsed - initialMemory.heapUsed
}
}];

</div>
</div>

  </div>
</div>

---

## 7.3 エラー回復とリトライ機能

<div class="card animated">
  <h3>🔄 堅牢なエラーハンドリング実装</h3>
  
  <div class="grid-2">
    <div>
      <h4>リトライ戦略の実装</h4>
      <div class="code-example" style="font-size: 0.7em;">
// 指数バックオフによるリトライ
const maxRetries = 3;
let retryCount = 0;
let lastError;

while (retryCount < maxRetries) {
try {
const result = await makeAPICall();
return [{ json: result }];
} catch (error) {
lastError = error;
retryCount++;

    if (retryCount < maxRetries) {
      const delay = Math.pow(2, retryCount) * 1000; // 指数バックオフ
      await new Promise(resolve => setTimeout(resolve, delay));
    }

}
}

throw new Error(`Failed after ${maxRetries} retries: ${lastError.message}`);

</div>
</div>
<div>
<h4>回復処理の設計</h4>
<ul>
<li><strong>フォールバック</strong> - 代替処理の実行</li>
<li><strong>部分回復</strong> - 可能な部分だけ処理</li>
<li><strong>状態保存</strong> - 中断ポイントの記録</li>
<li><strong>通知機能</strong> - エラー発生の報告</li>
<li><strong>手動介入</strong> - 人的確認が必要な場合</li>
</ul>
<div class="code-example" style="font-size: 0.7em;">
// フォールバック処理
try {
result = await primaryAPI();
} catch (error) {
console.warn('Primary API failed, using fallback');
try {
result = await fallbackAPI();
} catch (fallbackError) {
// 手動処理用キューに追加
await addToManualQueue(originalData);
throw new Error('Both primary and fallback failed');
}
}
</div>
</div>

  </div>
</div>

---

# 8. 実用的なワークフロー例

## 8.1 顧客サポート自動化

<div class="card animated">
  <h3>🎧 カスタマーサポートワークフロー</h3>
  
  <div class="grid-2">
    <div>
      <h4>ワークフローの構成</h4>
      <ol>
        <li><strong>メール受信</strong> - Email Trigger</li>
        <li><strong>内容分析</strong> - OpenAI による分類</li>
        <li><strong>優先度判定</strong> - IF ノードによる分岐</li>
        <li><strong>チケット作成</strong> - CRM への登録</li>
        <li><strong>自動回答</strong> - テンプレート返信</li>
        <li><strong>担当者通知</strong> - Slack 通知</li>
      </ol>
    </div>
    <div>
      <h4>実装のポイント</h4>
      <ul>
        <li><strong>感情分析</strong> - 緊急性の自動判定</li>
        <li><strong>カテゴリ分類</strong> - 適切な部署への振り分け</li>
        <li><strong>FAQ 自動回答</strong> - よくある質問の即答</li>
        <li><strong>エスカレーション</strong> - 複雑な案件の人間対応</li>
        <li><strong>追跡機能</strong> - 対応状況の監視</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>💡 実装例: メール分析と自動分類</h3>
  
  <div class="grid-2">
    <div>
      <h4>OpenAI を使用した分析</h4>
      <div class="code-example" style="font-size: 0.7em;">
{
  "model": "gpt-4",
  "messages": [
    {
      "role": "system",
      "content": "Analyze customer email and categorize: URGENT, HIGH, MEDIUM, LOW. Also determine department: TECH, BILLING, GENERAL"
    },
    {
      "role": "user",
      "content": "{{ $json.emailContent }}"
    }
  ],
  "functions": [
    {
      "name": "categorize_email",
      "parameters": {
        "type": "object",
        "properties": {
          "priority": {"type": "string", "enum": ["URGENT", "HIGH", "MEDIUM", "LOW"]},
          "department": {"type": "string", "enum": ["TECH", "BILLING", "GENERAL"]},
          "sentiment": {"type": "string", "enum": ["POSITIVE", "NEUTRAL", "NEGATIVE"]},
          "summary": {"type": "string"}
        }
      }
    }
  ]
}
      </div>
    </div>
    <div>
      <h4>分岐とアクション</h4>
      <div class="code-example" style="font-size: 0.7em;">
// IF ノード: 優先度による分岐
{{ $json.priority === "URGENT" }}

// 緊急時の処理
{
"channel": "#support-urgent",
"text": "🚨 URGENT: New ticket #{{ $json.ticketId }}",
"blocks": [
{
"type": "section",
"text": {
"type": "mrkdwn",
"text": "_Customer:_ {{ $json.customerName }}\n*Issue:* {{ $json.summary }}"
}
},
{
"type": "actions",
"elements": [
{
"type": "button",
"text": {"type": "plain_text", "text": "Take Case"},
"value": "{{ $json.ticketId }}"
}
]
}
]
}

</div>
</div>

  </div>
</div>

---

## 8.2 レポート自動生成

<div class="card animated">
  <h3>📊 日次・週次レポート自動化</h3>
  
  <div class="grid-2">
    <div>
      <h4>データ収集と集計</h4>
      <div class="code-example" style="font-size: 0.7em;">
// 複数ソースからのデータ収集
const salesData = await fetchSalesData();
const trafficData = await fetchTrafficData();
const supportData = await fetchSupportData();

// データの統合と集計
const report = {
date: new Date().toISOString().split('T')[0],
sales: {
total: salesData.reduce((sum, item) => sum + item.amount, 0),
transactions: salesData.length,
avgOrderValue: salesData.reduce((sum, item) => sum + item.amount, 0) / salesData.length
},
traffic: {
visitors: trafficData.uniqueVisitors,
pageViews: trafficData.pageViews,
conversionRate: (salesData.length / trafficData.uniqueVisitors \* 100).toFixed(2)
},
support: {
tickets: supportData.totalTickets,
resolved: supportData.resolvedTickets,
avgResponseTime: supportData.avgResponseTime
}
};

return [{ json: report }];

</div>
</div>
<div>
<h4>可視化と配信</h4>
<ul>
<li><strong>チャート生成</strong> - Chart.js でグラフ作成</li>
<li><strong>HTML レポート</strong> - テンプレートエンジン使用</li>
<li><strong>PDF 変換</strong> - レポートの PDF 化</li>
<li><strong>配信設定</strong> - 関係者への自動送信</li>
<li><strong>ダッシュボード更新</strong> - リアルタイム表示</li>
</ul>
<div class="code-example" style="font-size: 0.7em;">
// HTML レポートテンプレート
const htmlTemplate = `

<h1>Daily Report - ${report.date}</h1>
<div class="metrics">
  <div class="metric">
    <h3>Sales</h3>
    <p>Total: $${report.sales.total}</p>
    <p>Transactions: ${report.sales.transactions}</p>
  </div>
  <div class="metric">
    <h3>Traffic</h3>
    <p>Visitors: ${report.traffic.visitors}</p>
    <p>Conversion: ${report.traffic.conversionRate}%</p>
  </div>
</div>
`;
      </div>
    </div>
  </div>
</div>

---

## 8.3 在庫管理自動化

<div class="card animated">
  <h3>📦 在庫監視とアラートシステム</h3>
  
  <div class="grid-2">
    <div>
      <h4>在庫監視ロジック</h4>
      <div class="code-example" style="font-size: 0.7em;">
// 在庫データの取得と分析
const inventoryData = await fetchInventoryData();

const lowStockItems = inventoryData.filter(item => {
const daysOfStock = item.currentStock / item.avgDailySales;
return daysOfStock < item.reorderPoint;
});

const outOfStockItems = inventoryData.filter(item =>
item.currentStock <= 0
);

const fastMovingItems = inventoryData.filter(item =>
item.avgDailySales > item.expectedDailySales \* 1.5
);

// アラートレベルの決定
const alertLevel = outOfStockItems.length > 0 ? 'CRITICAL' :
lowStockItems.length > 5 ? 'HIGH' : 'MEDIUM';

return [{
json: {
alertLevel,
lowStockItems,
outOfStockItems,
fastMovingItems,
totalItems: inventoryData.length
}
}];

</div>
</div>
<div>
<h4>自動発注システム</h4>
<ul>
<li><strong>発注ポイント</strong> - 在庫レベルでの自動発注</li>
<li><strong>季節要因</strong> - 過去データによる需要予測</li>
<li><strong>サプライヤー連携</strong> - API を通じた自動発注</li>
<li><strong>承認ワークフロー</strong> - 高額商品の承認プロセス</li>
<li><strong>配送追跡</strong> - 発注後の進捗管理</li>
</ul>
<div class="code-example" style="font-size: 0.7em;">
// 自動発注の実装
for (const item of lowStockItems) {
if (item.autoReorder && item.value < 10000) {
// 自動発注実行
const orderQuantity = item.reorderQuantity;
await createPurchaseOrder({
supplierId: item.supplierId,
productId: item.id,
quantity: orderQuantity,
urgency: item.currentStock === 0 ? 'URGENT' : 'NORMAL'
});
} else {
// 承認待ちキューに追加
await addToApprovalQueue(item);
}
}
</div>
</div>

  </div>
</div>

---

# 9. 運用とメンテナンス

## 9.1 本番環境でのワークフロー管理

<div class="card animated">
  <h3>🏭 本番運用のベストプラクティス</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🔄 デプロイ戦略</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>段階的デプロイ</strong> - Dev → Staging → Prod</li>
        <li><strong>ブルーグリーンデプロイ</strong> - ダウンタイム最小化</li>
        <li><strong>カナリアリリース</strong> - 段階的な本番適用</li>
        <li><strong>ロールバック準備</strong> - 迅速な巻き戻し</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">📊 監視とアラート</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>実行監視</strong> - ワークフローの成功・失敗率</li>
        <li><strong>パフォーマンス監視</strong> - 実行時間・リソース使用量</li>
        <li><strong>エラー監視</strong> - エラー率とパターン分析</li>
        <li><strong>SLA 監視</strong> - サービスレベルの維持</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">🔐 セキュリティ管理</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>アクセス制御</strong> - ユーザー権限の管理</li>
        <li><strong>監査ログ</strong> - 操作履歴の記録</li>
        <li><strong>機密情報保護</strong> - Credential の暗号化</li>
        <li><strong>コンプライアンス</strong> - 規制要件の遵守</li>
      </ul>
    </div>
  </div>
</div>

---

## 9.2 バックアップとディザスタリカバリ

<div class="card animated">
  <h3>💾 データ保護とビジネス継続性</h3>
  
  <div class="grid-2">
    <div>
      <h4>バックアップ戦略</h4>
      <ul>
        <li><strong>定期バックアップ</strong> - 自動スケジュールによる保存</li>
        <li><strong>増分バックアップ</strong> - 効率的なストレージ利用</li>
        <li><strong>クロスリージョン</strong> - 地理的分散によるリスク軽減</li>
        <li><strong>バージョン管理</strong> - 複数世代の保持</li>
        <li><strong>復旧テスト</strong> - 定期的な復旧訓練</li>
      </ul>
    </div>
    <div>
      <h4>ディザスタリカバリ計画</h4>
      <ul>
        <li><strong>RTO (Recovery Time Objective)</strong> - 復旧目標時間</li>
        <li><strong>RPO (Recovery Point Objective)</strong> - 復旧目標地点</li>
        <li><strong>代替サイト</strong> - 障害時の運用継続</li>
        <li><strong>緊急時対応</strong> - エスカレーション手順</li>
        <li><strong>文書化</strong> - 復旧手順の明文化</li>
      </ul>
    </div>
  </div>
</div>

---

# 10. 応用テクニック

## 10.1 高度な制御フロー

<div class="card animated">
  <h3>🌊 複雑な条件分岐とループ</h3>
  
  <div class="grid-2">
    <div>
      <h4>高度な条件分岐</h4>
      <div class="code-example" style="font-size: 0.7em;">
// 複数条件の組み合わせ
{{ $json.status === "active" && $json.priority > 5 }}

// 配列の条件チェック
{{ $json.tags.includes("urgent") }}

// 正規表現による判定
{{ /^\d{4}-\d{2}-\d{2}/.test($json.date) }}

// ネストしたプロパティの確認
{{ $json.user?.profile?.verified === true }}

</div>
</div>
<div>
<h4>動的なループ処理</h4>
<div class="code-example" style="font-size: 0.7em;">
// 配列の各要素に対して処理
for (const item of $input.all()) {
if (item.json.amount > 1000) {
// 高額な取引の処理
await processHighValueTransaction(item.json);
}
}

// 条件に基づくバッチ処理
const batchSize = 50;
for (let i = 0; i < items.length; i += batchSize) {
const batch = items.slice(i, i + batchSize);
await processBatch(batch);
}

</div>
</div>

  </div>
</div>

---

## 10.2 カスタム関数とヘルパー

<div class="card animated">
  <h3>🔧 再利用可能な関数の作成</h3>
  
  <div class="grid-2">
    <div>
      <h4>ユーティリティ関数</h4>
      <div class="code-example" style="font-size: 0.7em;">
// 日付フォーマット関数
function formatDate(date, format = 'YYYY-MM-DD') {
  const d = new Date(date);
  return d.toISOString().split('T')[0];
}

// データ検証関数
function validateEmail(email) {
const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
return regex.test(email);
}

// エラーハンドリング関数
function safeJsonParse(jsonString, defaultValue = {}) {
try {
return JSON.parse(jsonString);
} catch (error) {
console.error('JSON parse error:', error);
return defaultValue;
}
}

</div>
</div>
<div>
<h4>データ変換ヘルパー</h4>
<div class="code-example" style="font-size: 0.7em;">
// オブジェクトの平坦化
function flattenObject(obj, prefix = '') {
return Object.keys(obj).reduce((acc, k) => {
const pre = prefix.length ? prefix + '.' : '';
if (typeof obj[k] === 'object' && obj[k] !== null) {
Object.assign(acc, flattenObject(obj[k], pre + k));
} else {
acc[pre + k] = obj[k];
}
return acc;
}, {});
}

// 配列のグループ化
function groupBy(array, key) {
return array.reduce((groups, item) => {
const group = item[key];
groups[group] = groups[group] || [];
groups[group].push(item);
return groups;
}, {});
}

</div>
</div>

  </div>
</div>

---

## 10.3 外部サービス統合パターン

<div class="card animated">
  <h3>🔌 API オーケストレーション</h3>
  
  <div class="grid-2">
    <div>
      <h4>サーキットブレーカーパターン</h4>
      <div class="code-example" style="font-size: 0.7em;">
// サーキットブレーカーの実装
class CircuitBreaker {
  constructor(threshold = 5, timeout = 60000) {
    this.threshold = threshold;
    this.timeout = timeout;
    this.failureCount = 0;
    this.state = 'CLOSED'; // CLOSED, OPEN, HALF_OPEN
    this.nextAttempt = Date.now();
  }

async call(fn) {
if (this.state === 'OPEN') {
if (Date.now() < this.nextAttempt) {
throw new Error('Circuit breaker is OPEN');
}
this.state = 'HALF_OPEN';
}

    try {
      const result = await fn();
      this.onSuccess();
      return result;
    } catch (error) {
      this.onFailure();
      throw error;
    }

}
}

</div>
</div>
<div>
<h4>レート制限対応</h4>
<div class="code-example" style="font-size: 0.7em;">
// レート制限を考慮した API 呼び出し
class RateLimitedAPI {
constructor(requestsPerMinute = 60) {
this.requestsPerMinute = requestsPerMinute;
this.requests = [];
}

async makeRequest(apiCall) {
const now = Date.now();
const oneMinuteAgo = now - 60000;

    // 1分以内のリクエストをフィルタ
    this.requests = this.requests.filter(time => time > oneMinuteAgo);

    if (this.requests.length >= this.requestsPerMinute) {
      const waitTime = this.requests[0] + 60000 - now;
      await new Promise(resolve => setTimeout(resolve, waitTime));
    }

    this.requests.push(now);
    return await apiCall();

}
}

</div>
</div>

  </div>
</div>

---

# 11. 実践ワークショップ

## 11.1 ハンズオン: E コマース注文処理システム

<div class="card animated">
  <h3>🛒 実践的なワークフロー構築</h3>
  
  <div class="grid-2">
    <div>
      <h4>システム要件</h4>
      <ul>
        <li><strong>注文受信</strong> - Webhook で注文データ取得</li>
        <li><strong>在庫確認</strong> - 在庫管理システムとの連携</li>
        <li><strong>決済処理</strong> - 決済サービス API 呼び出し</li>
        <li><strong>配送手配</strong> - 配送業者 API との連携</li>
        <li><strong>通知送信</strong> - 顧客とスタッフへの通知</li>
        <li><strong>データ記録</strong> - CRM・分析システムへの登録</li>
      </ul>
    </div>
    <div>
      <h4>実装フロー</h4>
      <ol>
        <li><strong>Webhook 設定</strong> - 注文データの受信</li>
        <li><strong>データ検証</strong> - 必須項目と形式チェック</li>
        <li><strong>在庫チェック</strong> - 商品在庫の確認</li>
        <li><strong>決済処理</strong> - クレジットカード決済</li>
        <li><strong>注文確定</strong> - 在庫の減算と注文確定</li>
        <li><strong>配送準備</strong> - 配送ラベル作成</li>
        <li><strong>通知送信</strong> - Email と SMS 通知</li>
      </ol>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>💻 実装例: 注文処理ワークフロー</h3>
  
  <div class="grid-2">
    <div>
      <h4>Step 1: データ検証</h4>
      <div class="code-example" style="font-size: 0.6em;">
// 注文データの検証
const order = $json;

// 必須フィールドの確認
const requiredFields = ['orderId', 'customerId', 'items', 'total'];
const missingFields = requiredFields.filter(field => !order[field]);

if (missingFields.length > 0) {
throw new Error(`Missing fields: ${missingFields.join(', ')}`);
}

// 商品データの検証
for (const item of order.items) {
if (!item.productId || !item.quantity || !item.price) {
throw new Error(`Invalid item data: ${JSON.stringify(item)}`);
}
}

return [{ json: { ...order, validated: true } }];

</div>
</div>
<div>
<h4>Step 2: 在庫確認</h4>
<div class="code-example" style="font-size: 0.6em;">
// 在庫確認ロジック
const items = $json.items;
const stockCheckResults = [];

for (const item of items) {
// 在庫 API 呼び出し（HTTP Request ノードで実行）
const stockResponse = await fetch(`/api/inventory/${item.productId}`);
const stock = await stockResponse.json();

if (stock.available < item.quantity) {
stockCheckResults.push({
productId: item.productId,
requested: item.quantity,
available: stock.available,
status: 'insufficient'
});
} else {
stockCheckResults.push({
productId: item.productId,
requested: item.quantity,
available: stock.available,
status: 'available'
});
}
}

return [{ json: { items, stockCheckResults } }];

</div>
</div>

  </div>
</div>

---

## 11.2 チーム演習とコードレビュー

<div class="card animated">
  <h3>👥 協働学習のアプローチ</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🔍 ペアプログラミング</h4>
      <ul style="font-size: 0.9em;">
        <li>2人1組でワークフロー作成</li>
        <li>一人が設計、一人が実装</li>
        <li>定期的な役割交換</li>
        <li>リアルタイムでの知識共有</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">📋 コードレビュー</h4>
      <ul style="font-size: 0.9em;">
        <li>ワークフローの構造確認</li>
        <li>エラーハンドリングの妥当性</li>
        <li>パフォーマンスの最適化</li>
        <li>セキュリティ観点での検証</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">🎯 ベストプラクティス</h4>
      <ul style="font-size: 0.9em;">
        <li>命名規則の統一</li>
        <li>ドキュメント化の習慣</li>
        <li>テスト戦略の確立</li>
        <li>運用を考慮した設計</li>
      </ul>
    </div>
  </div>
</div>

---

## 11.3 Q&A セッション

<div class="card animated">
  <h3>❓ よくある質問と回答</h3>
  
  <div style="display: flex; justify-content: center; margin: 20px 0;">
    <div style="overflow-x: auto; max-width: 100%;">
      <table style="width: 100%;">
        <thead>
          <tr>
            <th>質問カテゴリ</th>
            <th>よくある質問</th>
            <th>回答のポイント</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>パフォーマンス</strong></td>
            <td>大量データ処理時の最適化は？</td>
            <td>バッチ処理、並列実行、メモリ管理</td>
          </tr>
          <tr>
            <td><strong>エラー対応</strong></td>
            <td>APIエラーの適切な処理方法は？</td>
            <td>リトライ機能、フォールバック、ログ記録</td>
          </tr>
          <tr>
            <td><strong>セキュリティ</strong></td>
            <td>機密情報の安全な管理方法は？</td>
            <td>環境変数、暗号化、アクセス制御</td>
          </tr>
          <tr>
            <td><strong>運用</strong></td>
            <td>本番環境での監視方法は？</td>
            <td>ログ監視、アラート設定、パフォーマンス測定</td>
          </tr>
          <tr>
            <td><strong>拡張性</strong></td>
            <td>将来の要件変更への対応は？</td>
            <td>モジュール化、設定の外部化、バージョン管理</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

---

# 12. まとめと今後の学習方針

## 12.1 学習内容の振り返り

<div class="card animated">
  <h3>📚 学習達成度の確認</h3>
  
  <div class="grid-2">
    <div>
      <h4>習得したスキル</h4>
      <ul>
        <li><strong>基礎知識</strong>
          <ul>
            <li>n8n の概要と特徴</li>
            <li>UI の使い方とナビゲーション</li>
            <li>ワークフローの基本概念</li>
          </ul>
        </li>
        <li><strong>実践スキル</strong>
          <ul>
            <li>Credential 管理</li>
            <li>Slack 連携の実装</li>
            <li>データ処理とエラーハンドリング</li>
          </ul>
        </li>
      </ul>
    </div>
    <div>
      <h4>応用技術</h4>
      <ul>
        <li><strong>高度な機能</strong>
          <ul>
            <li>Structured Output の活用</li>
            <li>RAG システムの構築</li>
            <li>外部サービスとの統合</li>
          </ul>
        </li>
        <li><strong>運用知識</strong>
          <ul>
            <li>本番環境での管理</li>
            <li>監視とメンテナンス</li>
            <li>セキュリティ対策</li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</div>

---

## 12.2 次のステップと推奨学習リソース

<div class="card animated">
  <h3>🚀 継続的な学習のために</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">📖 学習リソース</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>公式ドキュメント</strong>
          <ul>
            <li>docs.n8n.io</li>
            <li>最新機能の確認</li>
          </ul>
        </li>
        <li><strong>コミュニティ</strong>
          <ul>
            <li>community.n8n.io</li>
            <li>Discord サーバー</li>
          </ul>
        </li>
        <li><strong>YouTube チャンネル</strong>
          <ul>
            <li>公式チュートリアル</li>
            <li>ユースケース事例</li>
          </ul>
        </li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">🛠️ 実践プロジェクト</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>個人プロジェクト</strong>
          <ul>
            <li>日常業務の自動化</li>
            <li>データ収集システム</li>
          </ul>
        </li>
        <li><strong>チームプロジェクト</strong>
          <ul>
            <li>部署横断の自動化</li>
            <li>顧客サポート改善</li>
          </ul>
        </li>
        <li><strong>オープンソース</strong>
          <ul>
            <li>カスタムノード開発</li>
            <li>テンプレート共有</li>
          </ul>
        </li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">🎯 認定・資格</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>n8n 認定</strong>
          <ul>
            <li>公式認定プログラム</li>
            <li>スキル証明</li>
          </ul>
        </li>
        <li><strong>関連技術</strong>
          <ul>
            <li>API 設計・開発</li>
            <li>クラウドサービス</li>
          </ul>
        </li>
        <li><strong>業界認定</strong>
          <ul>
            <li>自動化エンジニア</li>
            <li>システム統合</li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</div>

---

## 12.3 30 日間のアクションプラン

<div class="card animated">
  <h3>📅 具体的な学習スケジュール</h3>
  
  <div class="grid-4">
    <div style="text-align: center; padding: 1em; background: var(--rp-iris); border-radius: 8px;">
      <h4 style="color: white; margin-bottom: 0.5em;">Week 1</h4>
      <ul style="color: white; font-size: 0.8em; list-style: none; padding: 0;">
        <li>• 基本ワークフロー作成</li>
        <li>• HTTP Request 練習</li>
        <li>• データ変換の習得</li>
      </ul>
    </div>
    <div style="text-align: center; padding: 1em; background: var(--rp-foam); border-radius: 8px;">
      <h4 style="color: white; margin-bottom: 0.5em;">Week 2</h4>
      <ul style="color: white; font-size: 0.8em; list-style: none; padding: 0;">
        <li>• Slack 連携実装</li>
        <li>• Webhook 設定</li>
        <li>• エラーハンドリング</li>
      </ul>
    </div>
    <div style="text-align: center; padding: 1em; background: var(--rp-gold); border-radius: 8px;">
      <h4 style="color: white; margin-bottom: 0.5em;">Week 3</h4>
      <ul style="color: white; font-size: 0.8em; list-style: none; padding: 0;">
        <li>• 複雑なワークフロー</li>
        <li>• 外部サービス統合</li>
        <li>• パフォーマンス最適化</li>
      </ul>
    </div>
    <div style="text-align: center; padding: 1em; background: var(--rp-rose); border-radius: 8px;">
      <h4 style="color: white; margin-bottom: 0.5em;">Week 4</h4>
      <ul style="color: white; font-size: 0.8em; list-style: none; padding: 0;">
        <li>• 本番環境デプロイ</li>
        <li>• 監視・運用設定</li>
        <li>• チーム共有・発表</li>
      </ul>
    </div>
  </div>
</div>

---

## 12.4 コミュニティ参加と情報共有

<div class="card animated">
  <h3>🌐 n8n エコシステムへの参加</h3>
  
  <div class="grid-2">
    <div>
      <h4>コミュニティリソース</h4>
      <ul>
        <li><strong>公式フォーラム</strong>
          <ul>
            <li>community.n8n.io</li>
            <li>質問・回答・議論</li>
          </ul>
        </li>
        <li><strong>GitHub</strong>
          <ul>
            <li>github.com/n8n-io/n8n</li>
            <li>Issue 報告・機能要望</li>
          </ul>
        </li>
        <li><strong>Discord</strong>
          <ul>
            <li>リアルタイム議論</li>
            <li>カジュアルな情報交換</li>
          </ul>
        </li>
      </ul>
    </div>
    <div>
      <h4>貢献の方法</h4>
      <ul>
        <li><strong>ナレッジ共有</strong>
          <ul>
            <li>ブログ記事の執筆</li>
            <li>チュートリアル作成</li>
          </ul>
        </li>
        <li><strong>コード貢献</strong>
          <ul>
            <li>カスタムノード開発</li>
            <li>バグ修正・機能改善</li>
          </ul>
        </li>
        <li><strong>コミュニティ支援</strong>
          <ul>
            <li>質問への回答</li>
            <li>イベント・勉強会開催</li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🎉 最終メッセージ</h3>
  
  <div style="text-align: center; padding: 2em;">
    <h2 style="color: var(--rp-iris); margin-bottom: 1em;">おめでとうございます！</h2>
    <p style="font-size: 24px; margin-bottom: 1.5em;">
      皆さんは n8n の基礎から応用まで、包括的な知識とスキルを身につけました。
    </p>
    <div class="highlight-box" style="margin: 2em 0;">
      <p style="font-size: 20px; margin-bottom: 1em;">
        <strong>これからが本当のスタートです。</strong>
      </p>
      <p style="font-size: 18px;">
        学んだ知識を活用して、日々の業務を効率化し、<br>
        新しい価値を創造していってください。
      </p>
    </div>
    <p style="font-size: 22px; color: var(--rp-foam);">
      自動化の力で、より創造的で意味のある仕事に集中できるようになることを願っています。
    </p>
    <div style="margin-top: 2em; font-size: 28px;">
      <span style="color: var(--rp-gold);">🚀</span>
      <span style="color: var(--rp-iris); font-weight: bold;">Happy Automating!</span>
      <span style="color: var(--rp-foam);">🤖</span>
    </div>
  </div>
</div>
