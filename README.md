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
flowchart LR
  START-->A(購入者が現れる)
  A(購入者が現れる)-->B{お金を入れたか}
  B--Yes-->C(金額を表示)
  B--No-->START
  C-->D{返却ボタンは押されたか}
  D--Yes-->返却ボタンの処理
  D--No-->E{購入ボタンが押されたか}
    subgraph 返却ボタンの処理
    direction TB
      D1(返却ボタンを押された)-->D2(お金を返却する)-->D3(金額の表示をリセットする)
    end
  返却ボタンの処理-->END
  E{購入ボタンが押されたか}--Yes-->F{指定以上の金額が入っているか}
  E--No-->B
  F--Yes-->G(飲み物を出す)
  F--No-->B
  G-->END
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
  actor 購入者
  actor 出店者
  actor 仲介業者
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
```mermaid
classDiagram
      Animal <|-- Duck
      Animal <|-- Fish
      Animal <|-- Zebra
      Animal : +int age
      Animal : +String gender
      Animal: +isMammal()
      Animal: +mate()
      class Duck{
          +String beakColor
          +swim()
          +quack()
      }
      class Fish{
          -int sizeInFeet
          -canEat()
      }
      class Zebra{
          +bool is_wild
          +run()
      }
```