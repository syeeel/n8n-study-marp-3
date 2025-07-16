---
marp: true
theme: default
paginate: true
lang: "ja"
footer: "©2025 n8n Study - IT基礎知識カリキュラム"
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

# <span>Basic IT & n8n</span>

## AI ワークフロー自動化プラットフォーム

<!-- _class: title-slide -->

---

# 目次

## Part 1: 通信の基礎

<div class="card animated">
  <ol>
    <li><strong>HTTP通信の基礎</strong> - プロトコル・ステータスコード</li>
    <li><strong>API</strong> - REST API・認証・実践</li>
    <li><strong>Webhook</strong> - リアルタイム通信</li>
    <li><strong>認証とセキュリティ</strong> - 各種認証方式</li>
  </ol>
</div>

---

# 目次

## Part 2: データ処理の基礎

<div class="card animated">
  <ol>
    <li><strong>データ形式の基礎</strong> - JSON・データ構造</li>
    <li><strong>データ処理の基礎</strong> - 変換・エラーハンドリング</li>
    <li><strong>ワークフロー設計</strong> - 自動化の考え方</li>
    <li><strong>実習・演習</strong> - ハンズオン・トラブルシューティング</li>
  </ol>
</div>

---

# 目次

## Part 3: n8n への橋渡し

<div class="card animated">
  <ol>
    <li><strong>n8nとの関連性</strong> - 学習内容の活用</li>
    <li><strong>次のステップ</strong> - 実践への道筋</li>
  </ol>
</div>

---

# 1. HTTP 通信の基礎

## 1.1 HTTP プロトコル

<div class="card animated">
  <h3>🌐 インターネット通信の仕組み</h3>
  <div class="grid-2">
    <div>
      <h4>HTTPとは</h4>
      <ul>
        <li>HyperText Transfer Protocol</li>
        <li>Web上でのデータ通信の約束事</li>
        <li>クライアント・サーバー間の通信</li>
        <li>ステートレスなプロトコル</li>
      </ul>
    </div>
    <div>
      <h4>通信の流れ</h4>
      <ol>
        <li>クライアントがリクエスト送信</li>
        <li>サーバーがリクエスト処理</li>
        <li>サーバーがレスポンス返送</li>
        <li>クライアントがレスポンス受信</li>
      </ol>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>📡 HTTPリクエストとレスポンス</h3>
  
  <div class="grid-2">
    <div>
      <h4 style="color: var(--rp-iris);">リクエスト構成</h4>
      <div class="code-example">
GET /api/users HTTP/1.1
Host: example.com
Authorization: Bearer token123
Content-Type: application/json

{
"name": "John Doe"
}

</div>
</div>
<div>
<h4 style="color: var(--rp-foam);">レスポンス構成</h4>
<div class="code-example">
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 45

{
"id": 1,
"name": "John Doe",
"status": "active"
}

</div>
</div>

  </div>
</div>

---

<div class="card animated">
  <h3>🔗 URL（URI）の構造</h3>
  
  <div class="code-example" style="margin: 1em 0;">
https://api.example.com:443/v1/users/123?include=profile&format=json#section1
  </div>
  
  <div class="grid-2">
    <div>
      <h4>構成要素</h4>
      <ul>
        <li><strong>スキーム</strong>: https</li>
        <li><strong>ホスト</strong>: api.example.com</li>
        <li><strong>ポート</strong>: 443</li>
        <li><strong>パス</strong>: /v1/users/123</li>
      </ul>
    </div>
    <div>
      <h4>オプション要素</h4>
      <ul>
        <li><strong>クエリパラメータ</strong>: ?include=profile</li>
        <li><strong>フラグメント</strong>: #section1</li>
        <li><strong>認証情報</strong>: user:pass@</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🔧 HTTPメソッド</h3>
  
  <div class="grid-4">
    <div style="text-align: center; padding: 1em; background: var(--rp-pine); border-radius: 8px;">
      <h4 style="color: white; margin-bottom: 0.5em;">GET</h4>
      <p style="color: white; font-size: 0.9em; margin: 0;">データの取得</p>
    </div>
    <div style="text-align: center; padding: 1em; background: var(--rp-foam); border-radius: 8px;">
      <h4 style="color: white; margin-bottom: 0.5em;">POST</h4>
      <p style="color: white; font-size: 0.9em; margin: 0;">データの作成</p>
    </div>
    <div style="text-align: center; padding: 1em; background: var(--rp-gold); border-radius: 8px;">
      <h4 style="color: white; margin-bottom: 0.5em;">PUT</h4>
      <p style="color: white; font-size: 0.9em; margin: 0;">データの更新</p>
    </div>
    <div style="text-align: center; padding: 1em; background: var(--rp-love); border-radius: 8px;">
      <h4 style="color: white; margin-bottom: 0.5em;">DELETE</h4>
      <p style="color: white; font-size: 0.9em; margin: 0;">データの削除</p>
    </div>
  </div>
  
  <div class="highlight-box">
    <strong>CRUD操作</strong>: Create (POST), Read (GET), Update (PUT), Delete (DELETE)
  </div>
</div>

---

## 1.2 HTTP ステータスコード

<div class="card animated">
  <h3>📊 ステータスコードの分類</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-pine);">2xx: 成功</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>200 OK</strong> - 成功</li>
        <li><strong>201 Created</strong> - 作成成功</li>
        <li><strong>204 No Content</strong> - 成功（内容なし）</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">4xx: クライアントエラー</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>400 Bad Request</strong> - 不正なリクエスト</li>
        <li><strong>401 Unauthorized</strong> - 認証エラー</li>
        <li><strong>404 Not Found</strong> - 見つからない</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-love);">5xx: サーバーエラー</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>500 Internal Server Error</strong> - サーバー内部エラー</li>
        <li><strong>502 Bad Gateway</strong> - ゲートウェイエラー</li>
        <li><strong>503 Service Unavailable</strong> - サービス利用不可</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🔍 よく遭遇するステータスコード</h3>
  <div style="display: flex; justify-content: center; margin: 20px 0;">
    <div style="overflow-x: auto; max-width: 100%;">
  <div style="text-align: center !important;">
  <table style="width: 100%;">
    <thead>
      <tr>
        <th>コード</th>
        <th>意味</th>
        <th>よくある原因</th>
        <th>対処法</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>200</strong></td>
        <td>成功</td>
        <td>正常な処理</td>
        <td>そのまま継続</td>
      </tr>
      <tr>
        <td><strong>401</strong></td>
        <td>認証エラー</td>
        <td>APIキーが無効</td>
        <td>認証情報を確認</td>
      </tr>
      <tr>
        <td><strong>404</strong></td>
        <td>見つからない</td>
        <td>URLが間違っている</td>
        <td>エンドポイントを確認</td>
      </tr>
      <tr>
        <td><strong>429</strong></td>
        <td>制限超過</td>
        <td>リクエスト数が多すぎる</td>
        <td>時間をおいて再試行</td>
      </tr>
      <tr>
        <td><strong>500</strong></td>
        <td>サーバーエラー</td>
        <td>サーバー側の問題</td>
        <td>時間をおいて再試行</td>
      </tr>
    </tbody>
  </table>
</div>

---

# 2. API（Application Programming Interface）

## 2.1 API の基本概念

<div class="card animated">
  <h3>🔌 APIとは何か</h3>
  
  <div class="grid-2">
    <div>
      <h4>APIの定義</h4>
      <ul>
        <li>異なるソフトウェア間の橋渡し</li>
        <li>決められたルールでデータを交換</li>
        <li>機能を外部に公開する仕組み</li>
        <li>プログラム同士の約束事</li>
      </ul>
    </div>
    <div>
      <h4>APIの利点</h4>
      <ul>
        <li><strong>再利用性</strong> - 既存機能の活用</li>
        <li><strong>効率性</strong> - 開発時間の短縮</li>
        <li><strong>専門性</strong> - 特化したサービス利用</li>
        <li><strong>更新性</strong> - 機能の継続的改善</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🏗️ REST APIの概念</h3>
  
  <div class="highlight-box">
    <strong>REST</strong> = Representational State Transfer Webの仕組みを活用したAPI設計の考え方
  </div>
  
  <div class="grid-2">
    <div>
      <h4>RESTの原則</h4>
      <ul>
        <li><strong>ステートレス</strong> - 状態を保持しない</li>
        <li><strong>統一インターフェース</strong> - 一貫したルール</li>
        <li><strong>キャッシュ可能</strong> - 効率的な通信</li>
        <li><strong>階層化</strong> - システムの分離</li>
      </ul>
    </div>
    <div>
      <h4>RESTfulな設計例</h4>
      <div class="code-example" style="font-size: 0.8em;">
GET    /api/users      # ユーザー一覧
GET    /api/users/123  # 特定ユーザー
POST   /api/users      # ユーザー作成
PUT    /api/users/123  # ユーザー更新
DELETE /api/users/123  # ユーザー削除
      </div>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🎯 エンドポイントとは</h3>
  
  <div class="grid-2">
    <div>
      <h4>エンドポイントの構成</h4>
      <div class="code-example">
https://api.github.com/repos/owner/repo/issues
      </div>
      <ul>
        <li><strong>ベースURL</strong>: https://api.github.com</li>
        <li><strong>リソースパス</strong>: /repos/owner/repo/issues</li>
        <li><strong>バージョン</strong>: /v1, /v2 など</li>
      </ul>
    </div>
    <div>
      <h4>エンドポイントの種類</h4>
      <ul>
        <li><strong>コレクション</strong>: /users</li>
        <li><strong>リソース</strong>: /users/123</li>
        <li><strong>アクション</strong>: /users/123/activate</li>
        <li><strong>関連</strong>: /users/123/posts</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>📖 APIドキュメントの読み方</h3>
  
  <div class="grid-2">
    <div>
      <h4>確認すべき項目</h4>
      <ul>
        <li><strong>ベースURL</strong> - APIの基本アドレス</li>
        <li><strong>認証方法</strong> - API キーやトークン</li>
        <li><strong>エンドポイント</strong> - 利用可能な機能</li>
        <li><strong>パラメータ</strong> - 必須・オプション</li>
        <li><strong>レスポンス形式</strong> - 返却されるデータ</li>
        <li><strong>エラーコード</strong> - 失敗時の対応</li>
      </ul>
    </div>
    <div>
      <h4>ドキュメント例</h4>
      <div class="code-example" style="font-size: 0.8em;">
POST /api/users
Authorization: Bearer {token}
Content-Type: application/json

{
"name": "required string",
"email": "required string",
"age": "optional number"
}

Response: 201 Created
{
"id": 123,
"name": "John Doe",
"email": "john@example.com"
}

</div>
</div>

  </div>
</div>

---

## 2.2 API 認証

<div class="card animated">
  <h3>🔐 APIキーによる認証</h3>
  
  <div class="grid-2">
    <div>
      <h4>APIキーとは</h4>
      <ul>
        <li>APIアクセスのための識別子</li>
        <li>ユーザーやアプリケーションを識別</li>
        <li>利用制限や課金の基準</li>
        <li>セキュリティの第一歩</li>
      </ul>
    </div>
    <div>
      <h4>APIキーの使用方法</h4>
      <h5>Headerで送信</h5>
      <div class="code-example" style="font-size: 0.8em;">

Authorization: Bearer your-api-key-here
または
X-API-Key: your-api-key-here

</div>
</div>

  </div>
</div>

---

<div class="card animated">
  <h3>🔄 OAuth 2.0の基本</h3>
  
  <div class="highlight-box">
    <strong>OAuth 2.0</strong>: ユーザーの代わりにアプリケーションがサービスにアクセスする仕組み
  </div>
  
  <div class="grid-2">
    <div>
      <h4>OAuth 2.0の流れ</h4>
      <ol>
        <li><strong>認可要求</strong> - ユーザーに許可を求める</li>
        <li><strong>認可許可</strong> - ユーザーが許可</li>
        <li><strong>アクセストークン取得</strong> - トークン取得</li>
        <li><strong>リソースアクセス</strong> - トークンでAPI利用</li>
      </ol>
    </div>
    <div>
      <h4>主要な要素</h4>
      <ul>
        <li><strong>Client ID</strong> - アプリケーション識別子</li>
        <li><strong>Client Secret</strong> - アプリケーション秘密鍵</li>
        <li><strong>Access Token</strong> - リソースアクセス用</li>
        <li><strong>Refresh Token</strong> - トークン更新用</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🎫 Bearer Token</h3>
  
  <div class="grid-2">
    <div>
      <h4>Bearer Tokenとは</h4>
      <ul>
        <li>「Bearer」= 持参人、保持者</li>
        <li>トークンを持つ者がアクセス権を持つ</li>
        <li>HTTPヘッダーで送信</li>
        <li>OAuth 2.0で一般的</li>
      </ul>
    </div>
    <div>
      <h4>使用例</h4>
      <h3>リクエストヘッダーに含める</h3>
      <div class="code-example">
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...

</div>
</div>

  </div>
  
  <div class="highlight-box">
    <strong>注意</strong>: Bearer Tokenは機密情報です。HTTPSでの通信と適切な保管が必要です。
  </div>
</div>

---

<div class="card animated">
  <h3>🛡️ 認証が必要な理由</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🔒 セキュリティ</h4>
      <ul style="font-size: 0.9em;">
        <li>不正アクセスの防止</li>
        <li>データの保護</li>
        <li>システムの安全性確保</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">📊 利用管理</h4>
      <ul style="font-size: 0.9em;">
        <li>利用状況の追跡</li>
        <li>レート制限の適用</li>
        <li>課金の基準</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">🎯 個人化</h4>
      <ul style="font-size: 0.9em;">
        <li>ユーザー固有のデータ</li>
        <li>権限に応じたアクセス</li>
        <li>カスタマイズされた体験</li>
      </ul>
    </div>
  </div>
</div>

---

## 2.3 API リクエストの実践

<div class="card animated">
  <h3>❓ クエリパラメータ</h3>
  
  <div class="grid-2">
    <div>
      <h4>クエリパラメータとは</h4>
      <ul>
        <li>URLの「?」以降の部分</li>
        <li>key=value の形式</li>
        <li>複数は「&」で連結</li>
        <li>データのフィルタリングや設定</li>
      </ul>
    </div>
    <div>
      <h4>使用例</h4>
      <div class="code-example">

## 基本的な使用

/api/users?page=2&limit=10

## フィルタリング

/api/products?category=electronics&price_min=100

</div>
</div>

  </div>
</div>

---

<div class="card animated">
  <h3>📋 リクエストヘッダー</h3>
  
  <div class="grid-2">
    <div>
      <h4>よく使用されるヘッダー</h4>
      <ul>
        <li><strong>Authorization</strong> - 認証情報</li>
        <li><strong>Content-Type</strong> - データ形式</li>
        <li><strong>Accept</strong> - 受け入れ可能な形式</li>
        <li><strong>User-Agent</strong> - クライアント情報</li>
      </ul>
    </div>
    <div>
      <h4>ヘッダー例</h4>
      <div class="code-example">
Authorization: Bearer abc123
Content-Type: application/json
Accept: application/json
User-Agent: MyApp/1.0
X-Custom-Header: custom-value
      </div>
    </div>
  </div>
  
  <div class="highlight-box">
    <strong>重要</strong>: Content-Typeヘッダーは、送信するデータの形式をサーバーに伝える重要な情報です。
  </div>
</div>

---

<div class="card animated">
  <h3>📦 リクエストボディ</h3>
  
  <div class="grid-2">
    <div>
      <h4>ボディの用途</h4>
      <ul>
        <li><strong>POST</strong> - 新規データの作成</li>
        <li><strong>PUT</strong> - データの更新</li>
        <li><strong>PATCH</strong> - 部分的な更新</li>
        <li><strong>DELETE</strong> - 削除時の追加情報</li>
      </ul>
    </div>
    <div>
      <h4>JSON形式の例</h4>
      <div class="code-example">
{
  "name": "John Doe",
  "email": "john@example.com",
  "age": 30,
  "address": {
    "city": "Tokyo",
    "country": "Japan"
  },
  "hobbies": ["reading", "coding"]
}
      </div>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>📨 レスポンスの処理</h3>
  
  <div class="grid-2">
    <div>
      <h4>レスポンスの構成</h4>
      <ul>
        <li><strong>ステータスコード</strong> - 処理結果</li>
        <li><strong>ヘッダー</strong> - メタデータ</li>
        <li><strong>ボディ</strong> - 実際のデータ</li>
      </ul>
    </div>
    <div>
      <h4>処理の流れ</h4>
      <ol>
        <li><strong>ステータスコード確認</strong> - 成功/失敗の判定</li>
        <li><strong>ヘッダー確認</strong> - 追加情報の取得</li>
        <li><strong>ボディ解析</strong> - データの抽出</li>
        <li><strong>エラーハンドリング</strong> - 失敗時の処理</li>
      </ol>
    </div>
  </div>
  
</div>

---

  <div class="code-example">

# 成功レスポンス例

HTTP/1.1 200 OK
Content-Type: application/json
X-Rate-Limit-Remaining: 99

{
"status": "success",
"data": {
"id": 123,
"name": "John Doe"
}
}

  </div>

---

# 3. Webhook

## 3.1 Webhook の基本

<div class="card animated">
  <h3>🔔 Webhookとは何か</h3>
  
  <div class="grid-2">
    <div>
      <h4>Webhookの定義</h4>
      <ul>
        <li>イベント発生時の自動通知</li>
        <li>リアルタイムでのデータ送信</li>
        <li>「逆API」とも呼ばれる</li>
        <li>プッシュ型の通信方式</li>
      </ul>
    </div>
    <div>
      <h4>Webhookの特徴</h4>
      <ul>
        <li><strong>即座性</strong> - イベント発生と同時に通知</li>
        <li><strong>効率性</strong> - 定期的な確認が不要</li>
        <li><strong>自動性</strong> - 人間の介入なし</li>
        <li><strong>柔軟性</strong> - 様々なイベントに対応</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🔄 プッシュ型通信 vs プル型通信</h3>
  
  <div class="grid-2">
    <div>
      <h4 style="color: var(--rp-foam);">プル型通信（従来）</h4>
      <ul>
        <li>定期的にデータを確認</li>
        <li>ポーリング方式</li>
        <li>無駄な通信が発生</li>
        <li>遅延が発生する可能性</li>
      </ul>
      <div class="code-example" style="font-size: 0.7em;">
# 5分ごとに確認
while True:
    data = check_for_updates()
    if data:
        process(data)
    sleep(300)  # 5分待機
      </div>
    </div>
    <div>
      <h4 style="color: var(--rp-iris);">プッシュ型通信（Webhook）</h4>
      <ul>
        <li>イベント発生時に即座に通知</li>
        <li>効率的な通信</li>
        <li>リアルタイム性</li>
        <li>サーバーリソースの節約</li>
      </ul>
      <div class="code-example" style="font-size: 0.7em;">
# イベント発生時に自動実行
@app.route('/webhook', methods=['POST'])
def handle_webhook():
    data = request.json
    process(data)
    return 'OK'
      </div>
    </div>
  </div>
</div>

---

## 3.2 Webhook の実装

<div class="card animated">
  <h3>⚙️ Webhookエンドポイントの設定</h3>
  
  <div class="grid-2">
    <div>
      <h4>設定手順</h4>
      <ol>
        <li><strong>エンドポイントURL準備</strong> - 受信用URLを用意</li>
        <li><strong>サービスに登録</strong> - WebhookURLを設定</li>
        <li><strong>イベント選択</strong> - 通知したいイベントを選択</li>
        <li><strong>テスト実行</strong> - 動作確認</li>
      </ol>
    </div>
    <div>
      <h4>エンドポイント例</h4>
      <div class="code-example" style="font-size: 0.7em;">
https://your-app.com/webhooks/github
https://your-app.com/webhooks/stripe
https://your-app.com/webhooks/slack

## n8n での例

https://your-n8n.com/webhook/abc123

</div>
</div>

  </div>
</div>

---

<div class="card animated">
  <h3>📦 ペイロードの受信</h3>
  
  <div class="grid-2">
    <div>
      <h4>ペイロードとは</h4>
      <ul>
        <li>Webhookで送信されるデータ</li>
        <li>JSON形式が多い</li>
        <li>イベントの詳細情報を含む</li>
        <li>サービスごとに形式が異なる</li>
      </ul>
    </div>
    <div>
      <h4>GitHub Webhookの例</h4>
      <div class="code-example" style="font-size: 0.6em;">
{
  "action": "opened",
  "pull_request": {
    "id": 123,
    "title": "Fix bug",
    "user": {
      "login": "username"
    },
    "created_at": "2024-01-01T00:00:00Z"
  },
  "repository": {
    "name": "my-repo",
    "full_name": "user/my-repo"
  }
}
      </div>
    </div>
  </div>
</div>

---

# 4. 認証とセキュリティ

## 4.1 基本的な認証方式

<div class="card animated">
  <h3>🔐 認証方式の種類</h3>
  
  <div class="grid-2">
    <div>
      <h4>Basic認証</h4>
      <ul>
        <li>ユーザー名とパスワード</li>
        <li>HTTPヘッダーで送信</li>
        <li>シンプルだが安全性に課題</li>
      </ul>
      <div class="code-example" style="font-size: 0.7em;">
Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=
<br>
# username:password をBase64エンコード
      </div>
    </div>
    <div>
      <h4>トークンベース認証</h4>
      <ul>
        <li>トークンによる認証</li>
        <li>期限付きの認証情報</li>
        <li>より安全性が高い</li>
      </ul>
      <div class="code-example" style="font-size: 0.7em;">
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
      </div>
    </div>
  </div>
</div>

---

## 4.2 セキュリティの考慮事項

<div class="card animated">
  <h3>🛡️ セキュリティベストプラクティス</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">🔒 HTTPS必須</h4>
      <ul style="font-size: 0.9em;">
        <li>通信の暗号化</li>
        <li>データの盗聴防止</li>
        <li>改ざん防止</li>
        <li>なりすまし防止</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">🔑 機密情報管理</h4>
      <ul style="font-size: 0.9em;">
        <li>APIキーの適切な保管</li>
        <li>環境変数での管理</li>
        <li>定期的なローテーション</li>
        <li>最小権限の原則</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">⏱️ レート制限</h4>
      <ul style="font-size: 0.9em;">
        <li>API呼び出し回数の制限</li>
        <li>DoS攻撃の防止</li>
        <li>サーバー負荷の軽減</li>
        <li>公平な利用の確保</li>
      </ul>
    </div>
  </div>
</div>

---

# 5. データ形式の基礎

## 5.1 JSON（JavaScript Object Notation）

<div class="card animated">
  <h3>📄 JSONとは何か</h3>
  
  <div class="grid-2">
    <div>
      <h4>JSONの特徴</h4>
      <ul>
        <li>軽量なデータ交換形式</li>
        <li>人間にも読みやすい</li>
        <li>多くのプログラミング言語で対応</li>
        <li>Web APIの標準形式</li>
      </ul>
    </div>
    <div>
      <h4>JSONの基本構造</h4>
      <div class="code-example" style="font-size: 0.7em;">
{
  "name": "John Doe",
  "age": 30,
  "isActive": true,
  "hobbies": ["reading", "coding"],
  "address": {
    "city": "Tokyo",
    "country": "Japan"
  },
  "spouse": null
}
      </div>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🔤 JSONのデータ型</h3>
  
  <div class="grid-3">
    <div>
      <h4>基本データ型</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>文字列</strong>: "Hello"</li>
        <li><strong>数値</strong>: 123, 45.67</li>
        <li><strong>真偽値</strong>: true, false</li>
        <li><strong>null</strong>: null</li>
      </ul>
    </div>
    <div>
      <h4>複合データ型</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>オブジェクト</strong>: {"key": "value"}</li>
        <li><strong>配列</strong>: [1, 2, 3]</li>
        <li><strong>ネスト</strong>: {"arr": [{"id": 1}]}</li>
      </ul>
    </div>
    <div>
      <h4>JSONのルール</h4>
      <ul style="font-size: 0.9em;">
        <li><strong>キーは必ず文字列</strong></li>
        <li><strong>文字列はダブルクォート</strong></li>
        <li><strong>末尾にカンマ不可</strong></li>
        <li><strong>コメント不可</strong></li>
      </ul>
    </div>
  </div>
</div>

---

## 5.2 データ構造の基本

<div class="card animated">
  <h3>🏗️ データ構造の基本概念</h3>
  
  <div class="grid-2">
    <div>
      <h4>データ構造とは</h4>
      <ul>
        <li>データを効率的に格納・操作する方法</li>
        <li>プログラムでのデータ管理の基盤</li>
        <li>用途に応じた最適な構造選択</li>
        <li>データアクセスの効率性を決定</li>
      </ul>
    </div>
    <div>
      <h4>主要なデータ構造</h4>
      <ul>
        <li><strong>配列</strong> - 順序付きデータの集合</li>
        <li><strong>オブジェクト</strong> - キー・値ペアの集合</li>
        <li><strong>ネスト構造</strong> - 構造の入れ子</li>
        <li><strong>ツリー構造</strong> - 階層的なデータ</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🗂️ 配列（Array）とオブジェクト（Object）</h3>
  <div class="grid-2">
    <div>
      <h4>配列とオブジェクトの使い分け</h4>
      <ul>
        <li><strong>配列</strong> - 同種のデータの集合</li>
        <li><strong>オブジェクト</strong> - 属性を持つエンティティ</li>
        <li><strong>配列</strong> - ループ処理に適している</li>
        <li><strong>オブジェクト</strong> - 構造化されたデータ</li>
      </ul>
    </div>
    <div>
      <h4>実際の使用例</h4>
      <div class="code-example" style="font-size: 0.7em;">
## ユーザーリスト（配列）<br>
[
  {"id": 1, "name": "Alice"},
  {"id": 2, "name": "Bob"}
]<br>
## ユーザー詳細（オブジェクト）<br>
{
  "id": 1,
  "name": "Alice",
  "email": "alice@example.com",
  "preferences": ["music", "books"]
}
      </div>
    </div>
  </div>

---

<h4>配列の例</h4>
      <div class="code-example" style="font-size: 0.7em;">
[
  "apple",
  "banana",
  "orange"
]<br>
# アクセス例: array[0] → "apple"
      </div>
    </div>
    <div>
      <h4>オブジェクトの特徴</h4>
      <ul>
        <li>キーと値のペア</li>
        <li>キーでアクセス</li>
        <li>異なる型のデータを格納</li>
        <li>構造化されたデータ</li>
      </ul>
      <div class="code-example" style="font-size: 0.7em;">
{
  "name": "John",
  "age": 30,
  "email": "john@example.com",
  "isActive": true
}<br>
# アクセス例: object.name → "John"

---

# 6. データ処理の基礎

## 6.1 データの変換

<div class="card animated">
  <h3>🔄 データ変換の種類</h3>
  
  <div class="grid-2">
    <div>
      <h4>マッピング</h4>
      <ul>
        <li>データ形式の変換</li>
        <li>フィールド名の変更</li>
        <li>値の変換</li>
        <li>構造の再構築</li>
      </ul>
      <div>
</div>
</div>
<div>
<h4>フィルタリング</h4>
<ul>
<li>条件に基づくデータ選択</li>
<li>不要なデータの除去</li>
<li>特定条件のデータ抽出</li>
<li>データの絞り込み</li>
</ul>
</div>
</div>

  </div>
</div>

---

## 6.2 エラーハンドリング

<div class="card animated">
  <h3>⚠️ エラーの種類と対処</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-love);">ネットワークエラー</h4>
      <ul style="font-size: 0.9em;">
        <li>接続タイムアウト</li>
        <li>DNS解決失敗</li>
        <li>ネットワーク断絶</li>
        <li><strong>対処</strong>: リトライ機能</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">認証エラー</h4>
      <ul style="font-size: 0.9em;">
        <li>無効なAPIキー</li>
        <li>トークン期限切れ</li>
        <li>権限不足</li>
        <li><strong>対処</strong>: 認証情報更新</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-iris);">データエラー</h4>
      <ul style="font-size: 0.9em;">
        <li>形式不正</li>
        <li>必須フィールド欠損</li>
        <li>型不一致</li>
        <li><strong>対処</strong>: バリデーション</li>
      </ul>
    </div>
  </div>
</div>

---

# 7. ワークフロー設計の考え方

## 7.1 自動化の基本概念

<div class="card animated">
  <h3>⚙️ トリガーとアクション</h3>
  
  <div class="grid-2">
    <div>
      <h4>トリガー（きっかけ）</h4>
      <ul>
        <li><strong>時間ベース</strong>: 定期実行、特定時刻</li>
        <li><strong>イベントベース</strong>: Webhook、ファイル変更</li>
        <li><strong>手動</strong>: ユーザーが実行</li>
        <li><strong>条件ベース</strong>: 特定条件を満たした時</li>
      </ul>
    </div>
    <div>
      <h4>アクション（実行内容）</h4>
      <ul>
        <li><strong>データ取得</strong>: API呼び出し、DB検索</li>
        <li><strong>データ変換</strong>: フォーマット変更、計算</li>
        <li><strong>通知</strong>: メール、Slack、SMS</li>
        <li><strong>データ保存</strong>: DB書き込み、ファイル作成</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🌊 条件分岐とループ処理</h3>
  
  <div class="grid-2">
    <div>
      <h4>条件分岐</h4>
      <ul>
        <li>IF-THEN-ELSE の論理</li>
        <li>データに基づく判断</li>
        <li>複数の処理パス</li>
        <li>動的な処理選択</li>
      </ul>
      <div class="code-example" style="font-size: 0.6em;">
IF user.role == "admin"
  THEN grant_full_access()
  ELSE grant_limited_access()
      </div>
    </div>
    <div>
      <h4>ループ処理</h4>
      <ul>
        <li>配列データの一括処理</li>
        <li>繰り返し処理の自動化</li>
        <li>大量データの効率的処理</li>
        <li>バッチ処理の実現</li>
      </ul>
      <div class="code-example" style="font-size: 0.6em;">
FOR EACH user IN users
  send_notification(user.email)
END FOR
      </div>
    </div>
  </div>
</div>

---

## 7.2 実用的なワークフロー例

<div class="card animated">
  <h3>💼 ビジネスワークフロー例</h3>
  
  <div class="grid-2">
    <div>
      <h4>データ同期ワークフロー</h4>
      <ol style="font-size: 0.9em;">
        <li>定期的にシステムAからデータ取得</li>
        <li>データ形式をシステムB用に変換</li>
        <li>重複チェックと差分抽出</li>
        <li>システムBにデータ送信</li>
        <li>結果をSlackに通知</li>
      </ol>
    </div>
    <div>
      <h4>承認プロセスワークフロー</h4>
      <ol style="font-size: 0.9em;">
        <li>申請フォームの提出をトリガー</li>
        <li>申請内容の自動チェック</li>
        <li>承認者にメール通知</li>
        <li>承認結果の自動判定</li>
        <li>申請者に結果通知</li>
      </ol>
    </div>
  </div>
</div>

---

# 8. 実習・演習

## 8.1 ハンズオン演習

<div class="card animated">
  <h3>🛠️ 実践的な演習内容</h3>
  
  <div class="grid-2">
    <div>
      <h4>基礎演習</h4>
      <ul>
        <li><strong>JSONデータの読み書き</strong>
          <ul>
            <li>データの抽出と変換</li>
            <li>データのアウトプット</li>
          </ul>
        </li>
        <li><strong>簡単なAPI呼び出し</strong>
          <ul>
            <li>公開APIの利用</li>
            <li>レスポンスの処理</li>
          </ul>
        </li>
      </ul>
    </div>
    <div>
      <h4>応用演習</h4>
      <ul>
        <li><strong>Webhookの受信テスト</strong>
          <ul>
            <li>テスト用エンドポイント設定</li>
            <li>データの処理と保存</li>
          </ul>
        </li>
        <li><strong>データ変換の実践</strong>
          <ul>
            <li>複雑なデータ構造の変換</li>
            <li>条件分岐の実装</li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</div>

---

## 8.2 トラブルシューティング

<div class="card animated">
  <h3>🔧 よくある問題と対処法</h3>
  
  <div style="display: flex; justify-content: center; margin: 20px 0;">
    <div style="overflow-x: auto; max-width: 100%;">

  <table style="width: 100%;">
    <thead>
      <tr>
        <th>問題</th>
        <th>原因</th>
        <th>対処法</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>401 Unauthorized</td>
        <td>認証エラー</td>
        <td>APIキー・トークンの確認</td>
      </tr>
      <tr>
        <td>404 Not Found</td>
        <td>URLが間違っている</td>
        <td>エンドポイントの確認</td>
      </tr>
      <tr>
        <td>JSON解析エラー</td>
        <td>形式が不正</td>
        <td>JSONバリデーターで確認</td>
      </tr>
      <tr>
        <td>タイムアウト</td>
        <td>レスポンスが遅い</td>
        <td>タイムアウト値の調整</td>
      </tr>
      <tr>
        <td>レート制限</td>
        <td>API呼び出し過多</td>
        <td>間隔を空けて再試行</td>
      </tr>
    </tbody>
  </table>
</div>

---

# 9. n8n への橋渡し

## 9.1 n8n との関連性

<div class="card animated">
  <h3>🔗 学習内容がn8nでどう使われるか</h3>
  
  <div class="grid-2">
    <div>
      <h4>HTTP通信 → n8nノード</h4>
      <ul>
        <li><strong>HTTP Request</strong>: API呼び出し</li>
        <li><strong>Webhook</strong>: イベント受信</li>
        <li><strong>認証設定</strong>: 各種認証方式</li>
        <li><strong>エラーハンドリング</strong>: 失敗時の処理</li>
      </ul>
    </div>
    <div>
      <h4>データ処理 → n8n機能</h4>
      <ul>
        <li><strong>JSONデータ</strong>: ノード間のデータ交換</li>
        <li><strong>データ変換</strong>: Set、Code ノード</li>
        <li><strong>条件分岐</strong>: IF、Switch ノード</li>
        <li><strong>ループ処理</strong>: Loop ノード</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>🎯 n8nノード構造との対応</h3>
  
  <div class="grid-3">
    <div>
      <h4 style="color: var(--rp-iris);">トリガーノード</h4>
      <ul style="font-size: 0.9em;">
        <li>Manual Trigger</li>
        <li>Webhook</li>
        <li>Schedule Trigger</li>
        <li>Email Trigger</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-foam);">アクションノード</h4>
      <ul style="font-size: 0.9em;">
        <li>HTTP Request</li>
        <li>Gmail</li>
        <li>Slack</li>
        <li>Google Sheets</li>
      </ul>
    </div>
    <div>
      <h4 style="color: var(--rp-gold);">処理ノード</h4>
      <ul style="font-size: 0.9em;">
        <li>Set</li>
        <li>Code</li>
        <li>IF</li>
        <li>Switch</li>
      </ul>
    </div>
  </div>
</div>

---

## 9.2 次のステップ

<div class="card animated">
  <h3>🚀 実践への道筋</h3>
  
  <div class="grid-2">
    <div>
      <h4>環境セットアップ</h4>
      <ol>
        <li><strong>n8n Cloud</strong>の無料アカウント作成</li>
        <li>または<strong>Docker</strong>でローカル環境構築</li>
        <li>基本的なワークフロー作成</li>
        <li>テスト用APIサービスとの連携</li>
      </ol>
    </div>
    <div>
      <h4>学習リソース</h4>
      <ul>
        <li><strong>公式ドキュメント</strong>: n8n.io/docs</li>
        <li><strong>コミュニティフォーラム</strong>: community.n8n.io</li>
        <li><strong>YouTube チュートリアル</strong>: 実践的な例</li>
        <li><strong>GitHub</strong>: カスタムノード例</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="card animated">
  <h3>📚 推奨学習順序</h3>
  
  <div style="text-align: center; margin: 2em 0;">
    <div style="display: flex; justify-content: space-around; align-items: center;">
      <div style="text-align: center; padding: 1em; background: var(--rp-iris); border-radius: 8px; width: 20%;">
        <h4 style="color: white; margin-bottom: 0.5em;">1</h4>
        <p style="color: white; font-size: 0.9em; margin: 0;">基本ワークフロー</p>
      </div>
      <div style="font-size: 2em; color: var(--rp-muted);">→</div>
      <div style="text-align: center; padding: 1em; background: var(--rp-foam); border-radius: 8px; width: 20%;">
        <h4 style="color: white; margin-bottom: 0.5em;">2</h4>
        <p style="color: white; font-size: 0.9em; margin: 0;">API連携</p>
      </div>
      <div style="font-size: 2em; color: var(--rp-muted);">→</div>
      <div style="text-align: center; padding: 1em; background: var(--rp-gold); border-radius: 8px; width: 20%;">
        <h4 style="color: white; margin-bottom: 0.5em;">3</h4>
        <p style="color: white; font-size: 0.9em; margin: 0;">データ処理</p>
      </div>
      <div style="font-size: 2em; color: var(--rp-muted);">→</div>
      <div style="text-align: center; padding: 1em; background: var(--rp-rose); border-radius: 8px; width: 20%;">
        <h4 style="color: white; margin-bottom: 0.5em;">4</h4>
        <p style="color: white; font-size: 0.9em; margin: 0;">本格運用</p>
      </div>
    </div>
  </div>
</div>

---

# まとめ

<div class="card animated">
  <h3>🎯 学習のポイント</h3>
  
  <div style="display: flex; justify-content: center; margin: 1em 0 2em 0;">
    <div style="width: 90%; padding: 1.5em; border-radius: 8px; box-shadow: 0 2px 6px rgba(0,0,0,0.1);">
      <ul style="list-style-type: none; padding-left: 0;">
        <li style="margin-bottom: 1em; display: flex; align-items: center;">
          <span style="background-color: var(--rp-iris); color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">1</span>
          <span><strong>HTTP通信の理解</strong> - Web上でのデータ交換の基本</span>
        </li>
        <li style="margin-bottom: 1em; display: flex; align-items: center;">
          <span style="background-color: var(--rp-iris); color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">2</span>
          <span><strong>APIとWebhook</strong> - システム間連携の仕組み</span>
        </li>
        <li style="margin-bottom: 1em; display: flex; align-items: center;">
          <span style="background-color: var(--rp-iris); color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">3</span>
          <span><strong>JSONデータ処理</strong> - 現代のデータ交換標準</span>
        </li>
        <li style="display: flex; align-items: center;">
          <span style="background-color: var(--rp-iris); color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">4</span>
          <span><strong>ワークフロー思考</strong> - 自動化の設計思想</span>
        </li>
      </ul>
    </div>
  </div>

  <div style="text-align: center; margin-top: 3em;">
    <p style="font-size: 28px; font-weight: bold; color: var(--rp-iris);">これらの知識でn8nを最大限活用しよう！</p>
  </div>
</div>

---

<div class="card animated" style="display: flex; justify-content: center; align-items: center; height: 70vh;">
  <div style="text-align: center;">
    <h2 style="font-size: 36px; margin-bottom: 1em; color: var(--rp-iris);">Thank you for learning!</h2>
    <p style="font-size: 24px; color: var(--rp-foam);">n8nで素晴らしい自動化を実現してください</p>
  </div>
</div>
