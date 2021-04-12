# chapter11_AS
Google mapとRealm データベースを組合せた地図アプリの作成。

1. 現在地を取得

2. 「ここで一句」ボタンをクリック

3. 好きな言葉を書いて保存
4. Google mapにマーカーを表示。マーカーの内容は「いつ・どこで・何を書いたか」

【問題点】
realm.executeTransactionAsync は呼ばれるがRealm データベースの中身を取得できない
