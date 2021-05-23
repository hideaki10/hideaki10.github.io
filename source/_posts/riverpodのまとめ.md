---
title: riverpodのまとめ
date: 2021-02-14 23:02:09
tags:
---


# providersの特徴
1.
2.
3.
4.

# providerの作成

```dart
final testProvider = Provider((ref) {
    return TestValue();
    // 他のProviderの参照やStateへの処理など
})

// testProviderはimmutableで宣言が必要 
// Providerは基本のプロバイターで、他にもStreamProvider,StateNotifierProviderがある
 
```
# provider使用上の注意点

1. 一番上のルートにProvideScopeを追記する
```dart
   void main(){
       runApp(ProviderScope(child: MyApp()));
   }
```
2. stateをdestroyedするのはonDispose使う(Providerの種類によって、自動的に実行する場合もある、例えばStateNotifier)
```dart
final test = StreamProvider.autoDispose((ref){
    final streamController = StreamController<int>();

    ref.onDispose((){
        streamController.close();
    })
})
```



