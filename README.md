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
flowchart LR;
  A("開始") --> B["着替え"]
  B --> C["荷物の用意"]
  C --> D{"雨？"}
  D --"はい"--> E["雨具の用意"]
  D --"いいえ"--> F["マスクをつける"]
  E --> F
  F --> G("終了")
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
  participant Taro
  participant Ziro
  participant Saburo
  Taro ->> Ziro: 朝は何食べた？
  Ziro -->> Taro: 目玉焼きを食べたよ
  Taro ->> Saburo: 三郎は？
  loop 思い出している
    Saburo ->> Saburo: 何食べたったけ
  end
  Saburo -->> Taro: 忘れちゃった
  Taro ->> Saburo: お前は忘れっぽいよな
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
```mermaid
classDiagram
  学校 *-- 生徒
  学校 *-- 先生
  学校 <-- 小学校
  学校 <-- 中学校
  学校 <-- 高等学校
  生徒 : 子供
  生徒 : 学ぶ()
  先生 : 大人
  先生 : 教える()
