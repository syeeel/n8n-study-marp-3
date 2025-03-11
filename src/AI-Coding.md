---
marp: true
theme: default
paginate: true
lang: "ja"
header: "開発業務における生成AIの活用"
footer: "©2025 Satoshi Yoshimura"
style: |
  /* プレゼンテーション全体のスタイル */
  section {
    font-family: "Noto Sans JP", "Hiragino Kaku Gothic ProN", "Hiragino Sans", Meiryo, sans-serif;
    background-color: white;
    font-size: 24px;
    line-height: 1.5;
    justify-content: flex-start;  /* 左上スタート */
    align-items: flex-start;      /* 左上スタート */
    padding: 40px;                /* 上部にパディングを追加 */
    margin: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }

  /* 見出しのスタイル */
  h1 {
    color: #2563EB;
    font-size: 40px;
    margin-top: 0;               /* 上部マージンを削除 */
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
    max-width: 80%;             /* 最大幅を制限 */
    height: auto;               /* アスペクト比を維持 */
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

  /* コンテンツエリアのスタイル */
  .content-area {
    margin-top: 60px;            /* タイトルとの重複を避けるためのマージン */
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
    justify-content: flex-start; /* 左揃え */
    align-items: flex-start;     /* 上揃え */
    gap: 20px;                   /* 要素間の間隔 */
  }
math: mathjax
mermaid: true
---

<!-- Mermaidを読み込み -->
<script type="module">
import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@11.4.1/dist/mermaid.esm.min.mjs';
mermaid.initialize({ startOnLoad: true });
</script>
<!-- Mermaidを読み込み -->

<!-- タイトルスライド -->

# AI First Coding

## コード補完から自律的コーディングへの進化

<!-- _class: title-slide -->

---

# 目次

1. コード補完 - 生成 AI の始まり
2. 対話型 AI (Chat) - 開発者の相棒へ
3. Cursor によるコード生成 - Composer の力
4. Cline による自律的コーディング - 次世代の開発

---

# 1. コード補完 - 生成 AI の始まり

<div style="display: flex; justify-content: space-between; align-items: center;">
  <div style="width: 55%;">
    <ul>
      <li><strong>GitHub Copilot</strong> - コード補完の革命</li>
      <li>コンテキストを理解した提案</li>
      <li>単純な構文から複雑なパターンまで</li>
    </ul>
    <div style="margin-top: 2em; padding: 1em; background-color: #f0f7ff; border-left: 4px solid #2563EB; border-radius: 4px;">
      <strong>効果:</strong> 開発速度の向上とタイピング量の削減
    </div>
  </div>
  <div style="width: 40%;">
    <img src="https://www.gmo-jisedai.com/wp-content/uploads/logo-1.jpg" alt="ChatGPT" style="width: 100%; margin: 0 auto;">
  </div>
</div>

---

# 対話型 AI の活用例

<div style="display: flex; justify-content: center; margin: 1em 0;">
  <div style="width: 90%; background-color: #f8f9fa; padding: 1.5em; border-radius: 8px; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
    <p style="color: #555; font-weight: bold; margin-bottom: 0.5em;">ユーザー:</p>
    <p style="background-color: #e9f5ff; padding: 0.8em; border-radius: 8px; margin-bottom: 1em;">"CSVファイルを読み込んで、特定の列の平均値を計算するPythonコードを書いて"</p>
    
      
```python
import pandas as pd

def calculate_column_average(file_path, column_name):
df = pd.read_csv(file_path)
return df[column_name].mean()

# 使用例

average = calculate_column_average('data.csv', '売上')
print(f'平均値: {average}')

```
  </div>
</div>

---

# 3. Cursor によるコード生成 - Composer の力

<div style="display: flex; justify-content: space-between; align-items: center;">
  <div style="width: 55%;">
    <ul>
      <li><strong>Composer</strong> 機能によるコード一括生成</li>
      <li>エディタに統合された生成 AI</li>
      <li>コンテキスト認識能力の向上</li>
      <li>リアルタイムの提案と修正</li>
    </ul>
    <div style="margin-top: 2em; padding: 1em; background-color: #f0f7ff; border-left: 4px solid #2563EB; border-radius: 4px;">
      <strong>効果:</strong> 複雑な機能の短時間での実装、一貫性の向上
    </div>
  </div>
  <div style="width: 40%;">
    <img src="https://assets.st-note.com/production/uploads/images/149763341/rectangle_large_type_2_07d82d560f65ae3e3fa5a61cd9c21dc3.jpeg?width=1200" alt="Cursor" style="width: 100%; margin: 0 auto;">
  </div>
</div>

---

# Cursor のワークフロー


<div style="display: flex; justify-content: space-around; margin-top: 2em;">
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>1. 記述</h3>
    <p style="font-size: 18px;">機能の概要を自然言語で記述</p>
  </div>
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>2. 生成</h3>
    <p style="font-size: 18px;">AIがコード全体を生成</p>
  </div>
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>3. 確認</h3>
    <p style="font-size: 18px;">開発者による確認と調整</p>
  </div>
  <div style="width: 22%; text-align: center; padding: 1em; background-color: #f0f7ff; border-radius: 8px;">
    <h3>4. 修正</h3>
    <p style="font-size: 18px;">リアルタイムでのフィードバック</p>
  </div>
</div>

<div style="margin-top: 2em; padding: 1em; background-color: #f8f9fa; border-radius: 8px;">
  <strong>例:</strong> "ユーザー認証機能を持つ API エンドポイントを作成" → 数十行のコードが自動生成
</div>

---

# 4. Cline による自律的コーディング - 次世代の開発

<div style="display: flex; justify-content: space-between; align-items: center;">
  <div style="width: 55%;">
    <ul>
      <li>コマンドラインからの指示でコード生成</li>
      <li>自律的な問題解決と実装</li>
      <li>複数ファイルにまたがる変更の管理</li>
      <li>テストケースの自動生成</li>
    </ul>
    <div style="margin-top: 2em; padding: 1em; background-color: #f0f7ff; border-left: 4px solid #2563EB; border-radius: 4px;">
      <strong>効果:</strong> 開発プロセスの自動化と一貫性の確保
    </div>
  </div>
  <div style="width: 40%;">
    <img src="https://assets.st-note.com/production/uploads/images/177487721/rectangle_large_type_2_0dfcf17da5c9345f9416423f3c18c993.png?width=1200" alt="AI Coding" style="width: 100%; border-radius: 8px;">
  </div>
</div>

---

# Cline の活用例

<div style="display: flex; justify-content: center; margin: 1em 0;">
  <div style="width: 85%; background-color: #f8f9fa; padding: 1.5em; border-radius: 8px; font-family: monospace;">
    <div style="margin-bottom: 1.5em; border-left: 4px solid #2563EB; padding-left: 1em;">
      <p style="color: #555; margin-bottom: 0.3em; font-weight: bold;">新機能の実装指示:</p>
      <code style="display: block; background-color: #272822; color: #f8f8f2; padding: 0.8em; border-radius: 4px;">
        "ToDoアプリに完了タスクのフィルタリング機能を追加して"
      </code>
    </div>
  </div>
</div>



---

# 生成 AI による開発の変遷

<div style="overflow-x: auto; margin: 1.5em 0;">
  <table style="width: 100%; border-collapse: collapse; border: 1px solid #ddd;">
    <thead>
      <tr style="background-color: #f0f7ff;">
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">段階</th>
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">ツール例</th>
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">開発者の役割</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="padding: 12px; border: 1px solid #ddd; font-weight: bold;">コード補完</td>
        <td style="padding: 12px; border: 1px solid #ddd;">Copilot</td>
        <td style="padding: 12px; border: 1px solid #ddd;">主導的に開発、AI は補助</td>
      </tr>
      <tr style="background-color: #f8f9fa;">
        <td style="padding: 12px; border: 1px solid #ddd; font-weight: bold;">対話型支援</td>
        <td style="padding: 12px; border: 1px solid #ddd;">ChatGPT, Claude</td>
        <td style="padding: 12px; border: 1px solid #ddd;">問題定義と評価、AI は相談相手</td>
      </tr>
      <tr>
        <td style="padding: 12px; border: 1px solid #ddd; font-weight: bold;">統合環境</td>
        <td style="padding: 12px; border: 1px solid #ddd;">Cursor</td>
        <td style="padding: 12px; border: 1px solid #ddd;">方向性の提示、AI は実装パートナー</td>
      </tr>
      <tr style="background-color: #f8f9fa;">
        <td style="padding: 12px; border: 1px solid #ddd; font-weight: bold;">自律コーディング</td>
        <td style="padding: 12px; border: 1px solid #ddd;">Cline</td>
        <td style="padding: 12px; border: 1px solid #ddd;">アーキテクチャ設計と監督、AI は実装者</td>
      </tr>
    </tbody>
  </table>
</div>

---

# 今後の展望

<div style="display: flex; justify-content: space-around; margin: 2em 0;">
  <div style="width: 45%;">
    <h3 style="color: #2563EB; margin-bottom: 1em;">発展する技術</h3>
    <ul>
      <li>AI との共同開発モデルの進化</li>
      <li>専門分野特化型の開発支援 AI</li>
      <li>セキュリティと品質保証の自動化</li>
      <li>SaaS製品の爆発的増加</li>
    </ul>
  </div>

  <div style="width: 45%;">
    <h3 style="color: #e34c26; margin-bottom: 1em;">課題と懸念点</h3>
    <ul>
      <li>倫理的な配慮</li>
      <li>依存性の管理</li>
      <li>スキル維持</li>
      <li>セキュリティリスク</li>
      <li>賃金格差、スキル格差</li>
    </ul>
  </div>
</div>


---

# まとめ

<div style="display: flex; justify-content: center; margin: 1em 0 2em 0;">
  <div style="width: 90%; background-color: #f0f7ff; padding: 1.5em; border-radius: 8px; box-shadow: 0 2px 6px rgba(0,0,0,0.1);">
    <ul style="list-style-type: none; padding-left: 0;">
      <li style="margin-bottom: 1em; display: flex; align-items: center;">
        <span style="background-color: #2563EB; color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">1</span>
        <span>生成 AI は単純なコード補完から自律的なコーディングへと進化</span>
      </li>
      <li style="margin-bottom: 1em; display: flex; align-items: center;">
        <span style="background-color: #2563EB; color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">2</span>
        <span>開発者の役割は「コードを書く人」から「設計と監督の専門家」へと変化</span>
      </li>
      <li style="margin-bottom: 1em; display: flex; align-items: center;">
        <span style="background-color: #2563EB; color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">3</span>
        <span>人間と AI の強みを組み合わせた新しい開発パラダイムが形成中</span>
      </li>
      <li style="display: flex; align-items: center;">
        <span style="background-color: #2563EB; color: white; border-radius: 50%; width: 24px; height: 24px; display: inline-flex; justify-content: center; align-items: center; margin-right: 10px;">4</span>
        <span>スキル向上と AI 活用のバランスが重要</span>
      </li>
    </ul>
  </div>
</div>

<div style="text-align: center; margin-top: 3em;">
  <p style="font-size: 28px; font-weight: bold; color: #2563EB;">AIとの共創が開発の未来を形作る</p>
</div>

---


<div style="display: flex; justify-content: center; align-items: center; height: 70vh;">
  <div style="text-align: center;">
    <h2 style="font-size: 36px; margin-bottom: 1em; color: #2563EB;">Questions?</h2>
    <img src="https://cdn-icons-png.flaticon.com/512/6295/6295417.png" alt="Questions" style="width: 150px; margin: 0 auto;">
  </div>
</div>
```
