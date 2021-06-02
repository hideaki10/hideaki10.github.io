---
title: aws-ハンズオン2のまとめ
date: 2021-05-10 15:35:35
tags: aws
---

# 1 構成図

# 2 


# 3 手順
### 1. ec2とRDSの復元(停止また削除する場合)

### 2. /var/www/html/index.phpを編集

### 3. EC2からAMIを作成

### 4. AMIからEC2を作成

### 5. /var/www/html/index.phpを編集

### 6. ELB(ALB)の作成

### 7. RDSにip_addressを変更
```
mysql -h terraform-20210510062902244100000001.cjwfdjb0dqi3.ap-northeast-1.rds.amazonaws.com -u admin -p
USE mydb
3
select * from wp_options where option_name IN ('siteurl','home' );
4

5 update LBのDNS名
UPDATE wp_options SET option_value = 'http://LB-1-980424830.ap-northeast-1.elb.amazonaws.com' WHERE option_name IN ('siteurl', 'home');
UPDATE wp_options SET option_value = 'http://3.112.126.54' WHERE option_name IN ('siteurl', 'home');
13.114.79.19
index.phpで修正する行の後ろに”；”を忘れずに
```

### 8. EC2セキュリティーグループの設定変更

### 9. EC2を１個シャットダウンして障害テストをする

### 10. EC2を回復してRDSを冗長化をする

### 11. RDSを再起動してRDS

