# ユーザの権限管理

Dataware-tools のウェブアプリでは、[Role Based Access Control (RBAC)](https://ja.wikipedia.org/wiki/%E3%83%AD%E3%83%BC%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B9%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E5%88%B6%E5%BE%A1) に基づいてユーザの権限を管理しています。

「ファイルのメタ情報を見る」や「新しいファイルを追加する」といった権限は Role に紐付けられ、その Role が割り当てられたユーザがそれらの権限を持つことになります。

以下では、Dataware-tools に含まれる `app-user-manager` を使って Role の定義とユーザへの割当方法について説明します。



## Role の作成

![](<../../../.gitbook/assets/image (15).png>)

"User manager" を開きます

![](<../../../.gitbook/assets/スクリーンショット 2021-07-01 17.14.57.png>)

"Roles" タブに移動し、 "Add Role" をクリックします

![](<../../../.gitbook/assets/スクリーンショット 2021-07-01 17.16.45.png>)

①に Role の名前、②に説明文を入力します。\
その後、③のボタンをクリックします。

![](<../../../.gitbook/assets/スクリーンショット 2021-07-01 17.22.56.png>)

ここでは、①Databasesで権限を適用する対象のデータベースIDを、②Actionsで権限の内容を指定します。\
この欄は必要に応じて追加することができます。

![](<../../../.gitbook/assets/スクリーンショット 2021-07-01 17.17.12.png>)

データベースIDには、ワイルドカード (`*`) を使用することができます。\
例えば上の画像の例の場合、`test-abc` や `test-1` など `test-` で始まるデータベースが対象になります。

![](<../../../.gitbook/assets/スクリーンショット 2021-07-01 17.31.08.png>)

②Actionsでは該当のデータベースで許可する操作を指定します。\
なお、Actions には以下の内包関係が存在しています。

$$
{\rm admin} \supset {\rm read}, \ \ \ \ \   {\rm admin} \supset {\rm write}
$$

$$
{\rm read} \supset {\rm read\_public}
$$

$$
{\rm write} \supset {\rm add}, \ \ \ {\rm write} \supset {\rm update}, \ \ \ {\rm write} \supset {\rm delete}
$$



## ユーザへの Role の割り当て

上記で作成した Role をユーザに割り当てるには、 User Manager において

![](<../../../.gitbook/assets/image (23) (1).png>)

① "Users" タブに移動し、② ユーザに対する Role を指定します。

## Roleの削除

作成した Role を削除するには、UserManagerにおいて

![](<../../../.gitbook/assets/image (21).png>)

① "Roles"タブに移動し、②削除したいRole の右側にあるゴミ箱ボタンを押します。

その後、確認画面で同意するとレコードを削除することが出来ます。

