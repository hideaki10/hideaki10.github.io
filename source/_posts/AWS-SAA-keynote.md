---
title: AWS SAA keynote
date: 2021-05-24 14:10:48
tags: aws
---

## AWS SAAのまとめ


### EC2
  - インスタンス多数起動 
    - ブートストラップ
    - ゴールデンイメージ
  - インスタンスのオプション
     - オンデマンドインスタンスのキャバシティー
       - saving plans
         - キャバシティーのオプション
  - タグ数の上限
    - 50個

### VPC

- サブネット
  - 上限200個
- VPNの連携
  - オンプレ側にカスタマイズゲートウェイ
  - AWS側に仮想プライベードゲートウェイ
- エンドポイント
  - gateway
    - API gateway
    - cloudwatch
  - private link
    - Dynamo DB
    - S3 
 - ENI
   - ホットアタッチ
     - 実行中のアタッチ
   - ウォームアタッチ
     - 停止中のアタッチ
   - コールドアタッチ
     - インスタンスが起動中のアタッチ
 - Transit Gateway
   - 中央ハブを介してVPCとオンプレと接続
### CloudTrail
- アカウントの操作履歴

### RDS
 - パフォーマンス改善
    - コストをかかるけど、効果が高い(高速クエリ)
      - Elastic Cache 
 - コスト重視
    - レードレプリカ
 - 自動バックアップ
    - Oracleデータベースを起動して自動バックアップする
 - AutoScaling
    - RDSインスタンスの追加ではなく容量の自動追加
 - レードレプリカ
    - リージョンごとレードレプリカ構成
 - プロキシ
 　 - アプリとRDSのコネクション管理 

### DynamoDB
  ##### 処理を分散化する
   - SQSとLamdbaとの連携
  ##### デーブルの読み書き容量を制御
   - オンデマンド
   - プロビジョニング済み
    　- 読み書きの回数を指定してその必要な分の性能が確保される 

### EMR
  - 適用バータン
    - Machine Learning
    - リアルタイムストリーミングデータ処理

### ALB
  - CLB
    - Connection Draining
    - 異常発生する場合、新しいリクエストを送信せず、既存リクエスト完了
  - ALB
    - スティッキーセッション
    - 同じリクエストを同じEC2に送信する

### QuickSight
  -  可視化ツール
     - Redshiftとの連携して可能だが、Redshift自体は可視化を機能を提供してない

### Route53

- レコード
  - CNAME
   - 別のドメインへの設定
  - AliAS
   - AWS内部サービス利用(cloudfront,)
- マルチバリュールーティング
  - IPアドレス単位でヘルスチェック
- フェールオーバールーティング
  - プライマリー、セカンダリー(IPアドレスではなく)
### Redshift
  - クラスタ間にトラフィック制御
   - 拡張VPCルーティング


### Kinesis Data Firehose
  - データ変換処理
    - Lambdaとの連携して、S3(Redshift)にデータ保存

### CloudFront
  - 課金
    - トラフィック分散数
    - リクエスト数
    - データ転送アウト数

### ElasticCache
  - Memory
     1. シンプルなデータ
     2. 複数のコアまたスレッド持つ大きなノード
  - Redis 
    1. 複雑なデータ
    2. 永続性
    3. バックアップと復元
    4. pub/sub機能を提供する
### EBS
  - プロビジョンドIOPS SSD
  - スループット最適化HDD
  - 汎用SSD
  - コールドHDD
### EFS
  - モード
    - 汎用モード
    - 最大I/Oモード
    - バーストスループットモード
    - プロビジョンドスループットモード  
  - プロトコル
    - NFSv4
### S3
   - S3マルチパートアップロード
   　大容量オブジェクトをいくつかにS3にアップロード
   - アクセスポイント
     - アクセス管理を簡素化する

   - transfer acceleration
     - クライアントとS3パケット間で長距離にわたるファイル転送
   - 誤った削除対策
     - バージョンニング機能の有効化
     - MFA認証の有効化 
   - イベント通知
     - lambda
     - SQS
     - SNS
### Glacier
  - 取り出す時間

| 迅速取り出す | 標準取り出す | 一括処理(大容量) | Glacier Deep Archive |  
| :---:  | :---: | :---:  |:---:  |
| 1~5分 | 3~5時間 | 5~12時間 | 12~48時間 |

### SQS
  - 既存保存期間
    - 4日間
  - 保存できるメッセージ数
    - 無制限

### CloudWatch
 
- 標準メトリクス
  - os以外から測定
- カスタムメトリクス
  - os内の測定
- サブスクリブション
  - Lambdaへログ連携
- ApptraximateNumberOfMessage


### レアサービス
   - SSL証明書
     - ACM
     - IAM(ACMに対応してないリージョン)
   - VPCピアリング
     - 異なるリージョンにVPCでもビア接続できる
   - AWS Managed VPN
     - オンプレミスからAWSに接続するツール
   - AWS SMS
     - Server Migration Service
     - オンプレミスからシステムに移行(ワークロード)
   - AWS DMS
     - Database Migration Service
     - データベース間のデータ移行
   - AWS ADS
     - Application Discovery Service
     - オンプレミスのインベントリと動作を検出
     - 移行計画を作成する時
   - AWS DataSync
     - オンプレミスからEFS間にデータ転送
   - AWS DLM
     - Data Lifecycle Manager
     - EBSボリュームスナップショットの定期取得や管理
   - AWS Backup
     - AWSアカウントとリソース全体のバックアップアクティビティ 
   - OpsWorks
     - スタックベース 
   - AD Connect
     - Active DirectoryとIAMを連携する
   - SAM
     - サーバレスアプリケーションデプロイツール
   - step functions
     - オンプレとEC2で分散アーキテクチャーを構築する
   -  SWF
     - ワークフローなどプロセスが作成できる
     - EC2サーバベースのオーケストレーション機能がない
   - X-ray
     - APIリクエストを追跡、分析
   - WLM(work load management)
     - RedshiftWLM
     - Redshiftで実行するクエリ処理の実行順序を定義する

### 混乱しやすい物
 - リザーブド購入方式があるサービス
   - EC2
   - RDS
   - ElasticCache
   - DynamoDB
   - Redshift
##### オンプレミスとAWS間にデータ転送
  - Snowball
    - データ量が多い場合に向く
    - 物理機器が必要
  - Direct Connect
    - 専用線接続
    - AWSへの申請が必要
  - VPN
    - 暗号化通信
    - 即時の設定が可能
  - Storage Gateway
    - データ転送やバックアップ
    - オンプレミスとAWS側両方にデータを置く

