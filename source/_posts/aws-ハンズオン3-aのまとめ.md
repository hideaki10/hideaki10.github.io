---
title: aws-ハンズオン3-aのまとめ
date: 2021-06-01 17:44:26
tags: aws
---

1. EC2にCloudWatchのlogエージェントをインストール
```
 sudo yum install awslogs

```

2. logsのconfを設定する
```
 /etc/awslogs/awscli.conf
 regionを変更

 /etc/awslogs/awslogs.conf

 [HttpAccessLog]
file = /var/log/httpd/access_log
log_group_name = HttpAccessLog
log_stream_name = {instance_id}
datetime_format = %b %d %H:%M:%S

[HttpErrorLog]
file = /var/log/httpd/error_log
log_group_name = HttpErrorLog
log_stream_name = {instance_id}
datetime_format = %b %d %H:%M:%S

設定追加
```

3. IAMポリシーを追加する
