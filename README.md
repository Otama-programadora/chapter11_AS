# chapter11_AS
Google mapとRealm データベースを組合せた地図アプリの作成。

1. 現在地を取得
2. 「ここで一句」ボタンをクリック
3. 好きな言葉を書いて保存
4. Google mapにマーカーを表示。マーカーの内容は「いつ・どこで・何を書いたか」

【問題点】
AddActivityクラスの26行目 realm.executeTransactionについて

　同期処理のとき→「UIスレッドでのトランザクションが不能になりました」のエラーメッセージが出る

【行ったこと】
1.CustomApplicationクラスでのRealmの初期設定で「.allowWritesOnUiThread(true)」を追加。
realm.executeTransactionは同期処理で走らせると期待通りのプログラムができた。

2.Asyncのとき：「アクセスエラーです。Realm オブジェクトは生成されたスレッドからのみアクセス可能です」

3.Realm オブジェクトをexecuteTransactionの中で生成したらアプリが立ち上がらなくなった

【疑問】
1.は初期設定を変えているためあまり良い方法ではなさそう。
それ以外の解決方法はないか？
