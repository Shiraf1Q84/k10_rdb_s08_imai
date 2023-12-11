
# メモ管理アプリ

## 概要
このメモ管理アプリは、Streamlitをフロントエンドに、FastAPIとSQLiteをバックエンドに使用して、メモの登録と一覧表示の機能を提供します。
Streamlitを通じてユーザーはメモを入力し、FastAPIバックエンドはそれらのメモを処理してSQLiteデータベースに保存します。

## 構造
プロジェクトは以下のような構造になっています：

```
.
├── main.py          # Streamlitメイン関数
├── memo.db          # メモデータ用DB
└── memoback
   ├── __init__.py   
   ├── crud.py       # CRUD処理を記載
   ├── database.py   # DB接続処理を記載
   ├── main.py       # バックエンドメイン関数
   ├── model.py      # DBモデル定義
   └── schema.py     # 型情報
```

## 始め方

### 前提条件
- Python 3.6以上
- Streamlit
- FastAPI
- Uvicorn (FastAPIを実行するため)
- SQLAlchemy
- SQLite



### 仮想環境を立てる方法

仮想環境を立てる場合は以下の指示にしたがってください。


```bash
python -m venv env
```

```bash
.\env\Scripts\Activate.ps1
```

### インストール方法
依存関係をインストールするには、以下のコマンドを実行してください：



```bash
pip install streamlit fastapi uvicorn sqlalchemy
```




```bash
deactivate
```



### 実行方法
1. バックエンドサーバーの起動：
   ```bash
   uvicorn memoback.main:app --reload
   ```
   これにより、FastAPIがポート8000で実行されます。

2. Streamlitフロントエンドの起動：
   ```bash
   streamlit run main.py
   ```
   これにより、フロントエンドがポート8501で実行されます。

### 使用方法
- ブラウザで `http://localhost:8501` にアクセスして、メモの登録と一覧表示を行います。
- メモ登録時は、入力フォームに内容を入力し、「メモ登録」ボタンをクリックします。
- メモ一覧表示では、登録された全てのメモが表示されます。

