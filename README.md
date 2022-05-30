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
```mermaid
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
