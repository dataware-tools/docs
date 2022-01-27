# ユーザの権限管理

Dataware-tools のウェブアプリでは、[Role Based Access Control (RBAC)](https://ja.wikipedia.org/wiki/%E3%83%AD%E3%83%BC%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B9%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E5%88%B6%E5%BE%A1) に基づいてユーザの権限を管理しています。

「ファイルのメタ情報を見る」や「新しいファイルを追加する」といった権限は Role に紐付けられ、その Role が割り当てられたユーザがそれらの権限を持つことになります。

以下では、Dataware-tools に含まれる `User manager` を使って Role の定義とユーザへの割当てる方法について説明します。



## Role の作成

まず、初期状態では Role が存在しないので、Role を作成します。

### Role 作成用画面を開く

![](<../../../.gitbook/assets/image (26).png>)

トップページから、`User manager` を開きます。

![](<../../../.gitbook/assets/スクリーンショット 2021-07-01 17.14.57.png>)

① `Roles` タブに移動し、 ② `ADD ROLE` をクリックします。

### Role の内容を入力する

![](<../../../.gitbook/assets/スクリーンショット 2021-07-01 17.16.45.png>)

① に Role の名前、② に説明文を入力します。\
その後、③ のボタンをクリックします。③ のボタンをクリックすると、権限を管理するための入力欄が追加されます。

![](<../../../.gitbook/assets/スクリーンショット 2021-07-01 17.22.56.png>)

ここでは、① `Databases` で権限を適用する対象のデータベースIDを、② `Actions`で権限の内容を指定します。\
この欄は必要に応じて追加することができます。

#### Database ID の指定方法

![](<../../../.gitbook/assets/スクリーンショット 2021-07-01 17.17.12.png>)

データベースIDには、ワイルドカード (`*`) を使用することができます。\
例えば上の画像の例の場合、`test-abc` や `test-1` など `test-` で始まるデータベースが対象になります。

#### Action の指定方法

![](<../../../.gitbook/assets/スクリーンショット 2021-07-01 17.31.08.png>)

② `Actions`では該当のデータベースで許可する操作を指定します。\
なお、`Actions` で表示されるアイテムの動詞に関して、以下の内包関係が存在しています。

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

上記で作成した Role をユーザに割り当てるには、 `User manager` において

![](<../../../.gitbook/assets/image (39).png>)

① `Users` タブに移動し、② ユーザに対する Role を指定します。

## Role の削除

作成した Role を削除するには、`User manager`において

![](<../../../.gitbook/assets/image (35).png>)

①  `Roles` タブに移動し、② 削除したい Role の右側にあるゴミ箱ボタンを押します。

その後、確認画面で同意するとレコードを削除することが出来ます。

