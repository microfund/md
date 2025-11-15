# md
how to md files.

## 書式
**太文字**

*斜体*

***太字斜体***

<u>ここに下線</u>
※githubでは表現不可(2025/11/15)

`ハイライト`

## Outline がカーソルを追いかけるようにする(VSCode)
* OUTLINE ペインの右上にある「カーソルに追従 (Follow Cursor)」アイコン をクリックしてオンにする
 
## マークダウンで表現できる図

※VSCode では「Markdown Preview Mermaid Support」 などの拡張機能を入れると、
mermaid … ブロックがプレビューで図として表示されます。

### 1-1. 画像（いわゆる“図”）
![キャプション（代替テキスト）](images/sample.png)

### テーブル
| 項目   | 説明               |
|--------|--------------------|
| 名前   | サンプル           |
| バージョン | 1.0            |

### 箇条書き
- プロジェクト
  - フロントエンド
    - React
  - バックエンド
    - Python
      - FastAPI

### チェックリスト
- [x] 要件定義
- [ ] 設計
- [ ] 実装
- [ ] テスト

### ディレクトリ構造の図（ASCIIアート）
```
project-root/
├─ src/
│ ├─ main.py
│ └─ utils.py
└─ README.md
```

### フローチャート（flowchart）

```mermaid
flowchart TD
    A[Start] --> B{ログイン済み?}
    B -->|Yes| C[ダッシュボード表示]
    B -->|No| D[ログイン画面へリダイレクト]
    C --> E[ログアウト]
    E --> B
```

```mermaid
graph TD
    A[Start] --> B[Process]
    B --> C[End]
```


---
### 2-2. シーケンス図（sequenceDiagram）
```mermaid
sequenceDiagram
    actor User
    participant Browser
    participant Server
    User->>Browser: URLを入力
    Browser->>Server: HTTP GET /index
    Server-->>Browser: HTMLレスポンス
    Browser-->>User: ページ表示
```

---
### 2-3. クラス図（classDiagram）
```mermaid
classDiagram
    class User {
        +int id
        +string name
        +login()
        +logout()
    }
    class Session {
        +string token
        +datetime expiresAt
    }
    User "1" -- "0..*" Session : owns
```

---
### 2-4. 状態遷移図（stateDiagram）
```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Loading : ボタン押下
    Loading --> Success : 取得成功
    Loading --> Error : 取得失敗
    Success --> Idle : 再読み込み
    Error --> Idle : 再試行
```

---
### 2-5. ER 図（erDiagram）
```mermaid
erDiagram
    USER ||--o{ ORDER : places
    ORDER ||--|{ ORDER_ITEM : contains
    PRODUCT ||--o{ ORDER_ITEM : "ordered in"
    USER {
        int id
        string name
        string email
    }
    ORDER {
        int id
        datetime created_at
    }
    PRODUCT {
        int id
        string name
        int price
    }
```

---
### 2-6. ガントチャート（gantt）
```mermaid
gantt
    title 開発スケジュール
    dateFormat YYYY-MM-DD
    section 設計
        要件定義 :a1, 2025-11-01, 3d
        詳細設計 :a2, after a1, 5d
    section 実装
        コーディング :b1, after a2, 7d
        単体テスト :b2, after b1, 5d
```

---
### 2-7. 円グラフ（pie）
```mermaid
pie showData
    title ポートフォリオ内訳
    "BTC" : 50
    "ETH" : 20
    "SOL" : 15
    "その他アルト" : 15
```


---
### 2-8. タイムライン（timeline）
```mermaid
timeline
    title プロジェクトの主なイベント
    2025-11-01 : 企画開始
    2025-11-10 : 要件定義完了
    2025-11-20 : プロトタイプ完成
    2025-12-01 : ベータ版リリース
```

---
### 2-9. マインドマップ（mindmap）
```mermaid
mindmap
    root((取引戦略))
        現物
            長期保有
            インデックス
        レバレッジ
            デイトレ
            スイング
        自動売買
            Bot構築
            リスク管理
```

---
### 2-10. ユーザージャーニー図（journey）
```mermaid
journey
    title ECサイトでのユーザー行動
    section 訪問
        トップページを閲覧 : 5:User
    section 検索
        商品検索 : 4:User
        絞り込み : 3:User
    section 購入
        カートに追加 : 4:User
        決済 : 2:User
```




## links
* https://www.markdownguide.org/cheat-sheet/?utm_source=chatgpt.com
* https://qiita.com/Qiita/items/c686397e4a0f4f11683d?utm_source=chatgpt.com
