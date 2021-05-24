---
title: AWS SAA keynote
date: 2021-05-24 14:10:48
tags:
---

#AWS SAAのまとめ


### EC2
  ##### インスタンス多数起動 
   - ブートストラップ
   - ゴールデンイメージ

### Amazon EMR
  ##### 適用バータン
   - Machine Learning
   - リアルタイムストリーミングデータ処理

### Amazon DynamoDB
  ##### 処理を分散化する
   - SQSとLamdbaとの連携

### Amazon QuickSight
  ##### 可視化ツール
   - Redshiftとの連携して可能だが、Redshift自体は可視化を機能を提供してない


### Amazon Redshift
  ##### クラスタ間にトラフィック制御
   - 拡張VPCルーティング


### Kinesis Data Firehose
  ##### データ変換処理
   - Lambdaとの連携して、S3(Redshift)にデータ保存

### CloudFront
  ##### 課金
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

### EFS
  ##### モード
   - 汎用モード
   - 最大I/Oモード
   - バーストスループットモード
   - プロビジョンドスループットモード  

### Amazon S3
   - S3マルチパートアップロード
   　大容量オブジェクトをいくつかにS3にアップロード
   - アクセスポイント
     アクセス管理を簡素化する

   - transfer acceleration
     クライアントとS3パケット間で長距離にわたるファイル転送

### レアサービス
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

### 混乱しやすい物
#####　リザーブド購入方式があるサービス
   - EC2
   - RDS
   - ElasticCache
   - DynamoDB
   - Redshift


