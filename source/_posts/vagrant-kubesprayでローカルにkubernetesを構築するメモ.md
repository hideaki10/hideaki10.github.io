---
title: vagrant+kubesprayでローカルにkubernetesを構築するメモ
date: 2021-06-17 22:46:28
tags: Kubernetes
---

```
 vi inventory/mycluster/hosts.yaml
 以下のように修正する
   master →　node1
   worker →　node2,node3

  vi inventory/mycluster/group_vars/k8s_cluster/k8s-cluster.yml
     適当にサブネットを修正
     kube_service_addresses　→　10.200.0.0/16　
     kube_pods_subnet　→　10.233.0.0/16

     container-managerを変更
     container_manager →　containerd

  vi ./inventory/mycluster/group_vars/etcd.yml
     deployのtypeを変更
     etcd_deployment_type →　host(二進数)
     
  vi ./inventory/mycluster/group_vars/k8s_cluster/addons.yml

     dashboard を変更
      dashboard_enabled →　true 
     ingress nginx を変更
     ingress_nginx_enabled →　true

  ansible-playbookを実行したら,no command場合
    ~/.bash_profileに以下追加
    export PATH="$PATH":"/usr/local/bin"

    source ~/.bash_profile