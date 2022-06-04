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
  A --> B{What size?}
  B -->|720KB|C(2DD Format Success)
  B -->|1.23MB|D(2HD Format Success)
  B -->|1.44MB|D
  B -->|Other|E(Not Supported)
  C --> END([終了])
  D --> END([終了])
  E --> END([終了])
```

## シーケンス図
### 条件
- 3人以上
- メッセージをやり取りしない人がいないように
- 自己呼び出しを含むこと
- カッコいいほど高得点

## 解答
```mermaid
sequenceDiagram
actor 人
participant A as ドライバー
participant B as ねじ
participant C as 部品

    人 ->>+ A: 手に持つ
    A ->> B: 回す
    B -->> C: 外れる
    C ->> C: 交換
    B -->> C: 付ける
　　A ->> B: 閉める
　　A ->> 人: 置く
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
```mermaid

```
