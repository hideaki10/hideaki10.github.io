---
title: DDDソース分析
date: 2021-02-02 16:33:38
tags:
---
## Presentation
grrr
## Application

- useCase
- アプリケーションからリポジトリを利用する
- Domain_serviceを呼ぶ
- Repositoryを呼ぶ

## Domain

- abstract repository_base(Impl)　①
- abstract factory_base(Impl)  ①
  - オブジェクトの生成を担うものです。 アプリケーションサービスでカテゴリやメモのオブジェクトを生成するのに使っています
- value_object
- entity  
- service (domain_service)
  - エンティティに関係するロジックであるけれども、エンティティに実装すると違和感を産むロジックは必ず存在します。
    そういったロジックを受け持つものとして[ドメイン](http://d.hatena.ne.jp/keyword/%A5%C9%A5%E1%A5%A4%A5%F3)サービスが存在します。 

## Infrastructure

- repository　①
- factory 　　①


