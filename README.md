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
### RPGの戦闘
- プレイヤーとエネミーがいる
- プレイヤーは剣での攻撃と魔法攻撃、逃走が出来る
- エネミーは攻撃してくるだけ
```mermaid
flowchart LR;
  Start([開始]) --> PlayerTurn[/入力/]
  PlayerTurn --> PlayerInput{選択}
  
  PlayerInput -- たたかう --> Attack[攻撃]
  Attack --> EnemyHPDown[敵のHPを減らす]
  EnemyHPDown --> CheckEnemyHP{HPの確認}
  CheckEnemyHP -- 0 --> End([終了])
  CheckEnemyHP -- 0以外 -->EnemyTurn
  
  PlayerInput -- まほう--> MagicChoice[/選択/]
  MagicChoice --> CheckMP{MP確認}
  CheckMP -- ある --> Magic[魔法発射]
  Magic --> CheckEnemyHP
  CheckMP -- ない --> PlayerInput

  PlayerInput -- にげる --> Check{逃げられるか}
  Check -- 成功 --> End
  Check -- 失敗 --> EnemyTurn[敵のターン]
  
  EnemyTurn --> EnemyAttack[攻撃]
  EnemyAttack --> PlayerHPDown[プレイヤーのHPを減らす]
  PlayerHPDown --> CheckPlayerHP{HPの確認}
  CheckPlayerHP -- 0 --> End
  CheckPlayerHP -- 0以外 --> PlayerTurn
  
  
  
```

## シーケンス図
### 条件
- 3人以上
- メッセージをやり取りしない人がいないように
- 自己呼び出しを含むこと
- カッコいいほど高得点

## 解答
### レジ
- POSレジを想定
- 有人のレジを想定
```mermaid
sequenceDiagram
%% ライフラインの定数的なやつを宣言しておく
participant User as 客
participant Employee as 店員
participant CashRegister as POSレジ
participant Server as サーバー

    loop 商品数
      User ->> Employee : 購入依頼
      Employee ->>+ CashRegister : スキャン
      CashRegister ->> Server : 商品情報を提供
      CashRegister -->>- CashRegister : 商品情報を表示
      opt 年齢確認が必要
        CashRegister -->>+ Employee: 年齢確認を要求 
        Employee ->>+ User : 年齢確認を要求
        User ->> Employee : 年齢
        opt 未成年の場合
          Employee ->>- User : 販売を拒否
        end
      end
    end
    
    CashRegister ->> CashRegister : 商品総額を表示
    Employee ->>+ User : 支払い方法を尋ねる
    User ->> Employee : 支払い方法
    Employee ->> User : 支払いの要求
    User ->>- Employee : 支払い
    Employee -->> CashRegister : お金を入れる
    opt お釣りがある
      CashRegister ->> Employee : お釣り
      Employee -->> User : お釣りの返却
    end
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
### 五目並べのクラス図
- 五目並べ本体ではなくプレイヤーやCPUとの関係性
- Stoneはenumの型で None,White,Blackを保有している
```mermaid
  classDiagram
    Entity <|-- Player
    Entity <|-- Computer
    Gomoku "1" o-- "0..2" Player
    Gomoku "1" o-- "0..2" Computer
    class Entity {
        <<abstract>>
        # string name
        # Stone stoneColor
        + void SetName(string)
        + string GetName()
        + void SetColor(Stone)
        + Stone GetColor()
    }
    class Player {
        + Player(Stone ,string)
    }
    class Computer {
        - int level
        - int MaxLevel
        - int minLevel
        
        + Computer(Stone,int string)
    }
    class Gomoku {
        - int Width
        - int Height
        - Stone[,] board 
        
        + Start()
    }
    
```
