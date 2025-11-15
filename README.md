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



## links
* https://www.markdownguide.org/cheat-sheet/?utm_source=chatgpt.com
* https://qiita.com/Qiita/items/c686397e4a0f4f11683d?utm_source=chatgpt.com
