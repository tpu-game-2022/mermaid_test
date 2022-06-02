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
-「双六」をテーマにしました。
```mermaid
flowchart LR;
  A([開始]) --> B[/マス目の入力/];
  B --> C{0以上100以下である}
  C --真--> E[ランダムにマスを3種類生成];
  C --偽--> D[[もう一度]];
  D --> B;
  E --> F[入力された値分のマス目とゴールマスを生成];
  F --> G[/ダイスを振る/];
  G --> P[ダイスの出目だけ進む];
  P --> I{ノーマルマスである}
  I --真--> G;
  I --偽--> J{1進むマスである}
  J --偽--> K{1戻るマスである};
  J --真--> O[1マス進む];
  O --> G;
  K --偽--> H[ゴール];
  K --真--> Q[1マス戻る];
  Q --> G;
  H --> M{もう一度遊ぶ}
  M --真--> B;
  M --偽--> N([終了]);
  
```

## シーケンス図
### 条件
- 3人以上
- メッセージをやり取りしない人がいないように
- 自己呼び出しを含むこと
- カッコいいほど高得点

## 解答
-「ゲーム制作」をテーマにしました。
```mermaid
sequenceDiagram
participant Kikaku
participant Design
participant Program
loop Prepare a proposal.
Kikaku->>Kikaku:Brainstorm ideas.
end
Kikaku->>Design: Please give me a RoughDesign!
loop Making texture
Design->>Design: Keep adding to one's revisions
end
Design-->>Kikaku:Douzo
Program->>Design:Give me a textur too, please.
Design-->>Program:OK.
Kikaku->>Program:Can you make this System?
loop Writing Programs
Program->>Program:Debug.
end
Program-->>Kikaku:Douzo.
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
```mermaid
classDiagram
Kougeidai o-- AtsugiCampus
Kougeidai o-- NakanoCampus
AtsugiCampus *-- KouGakubu
KouGakubu:Machine
KouGakubu:Electronics
KouGakubu:IT
KouGakubu:Chemistry
KouGakubu:Artchitecture
NakanoCampus *-- GeizyutsuGakubu
GeizyutsuGakubu:Picture
GeizyutsuGakubu:Movie
GeizyutsuGakubu:Design
GeizyutsuGakubu:IM
GeizyutsuGakubu:Animation
GeizyutsuGakubu:Game
GeizyutsuGakubu:Comic
```
