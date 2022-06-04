# 課題
Mermaidを触ってみよう

マークダウンファイルを編集して、Mermaidで図を描いてみよう

# 取り組み方
* 本プロジェクトをforkしてください。
* README.mdを編集して、Mermaidを使いこなしてください
* できたらプルリクエストを出します

# 課題項目
## 流れ図
### 条件
- 開始と終了ノードをつける
- 条件分岐を組み込む
- 5ノード以上
- カッコいいほど高得点

## 解答
```mermaid
flowchart TD;
  START([開始]) --> A(FORMAT Floppy)
  A --> B{1.44MB?}
  B -->|YES|C(Format Success)
  B -->|NO|D{What size?}
  D -->|720KB|E(Format Success)
  D -->|1.23MB|F(Format Success)
  D -->|Other|G(Not Supported)
  C --> END([終了])
  E --> END([終了])
  F --> END([終了])
  G --> END([終了])
```

## シーケンス図
### 条件
- 3人以上
- メッセージをやり取りしない人がいないように
- 自己呼び出しを含むこと
- カッコいいほど高得点

## 解答
```mermaid
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
