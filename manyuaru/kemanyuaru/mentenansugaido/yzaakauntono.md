# ユーザアカウントの追加

Dataware-tools のウェブアプリケーションで使用するユーザアカウントを新たに追加するには以下の操作を行います。

### Auth0のユーザ管理ページを開く

![](../../../.gitbook/assets/demo.dataware-tools.com\_launcher.png)

トップページから `User manager` を開きます。

![](../../../.gitbook/assets/demo.dataware-tools.com\_user-manager.png)

画面右上の `ADD USER` をクリックします。\
これにより、Auth0 の管理ページに遷移します。

![](../../../.gitbook/assets/manage.auth0.com\_dashboard\_us\_dataware-tools\_userss1.png)

### Auth0 で新規ユーザアカウントを追加する

![](../../../.gitbook/assets/manage.auth0.com\_dashboard\_us\_dataware-tools\_userss.png)

メニューから `User Management` -> `Users` を選択します。

![](<../../../.gitbook/assets/manage.auth0.com\_dashboard\_us\_dataware-tools\_userss (2).png>)

`Create User` をクリックし、新しいユーザが使用するメールアドレスとパスワードを入力してください。

以上の操作で新規ユーザアカウントが登録できました。



### 新規ユーザアカウントのアクティベーション

登録された新規ユーザアカウントを有効化するために、Auth0から新規ユーザのメールアドレス宛に送信されたメールを開き、そこに記載されているURLを開いて下さい。

この操作により新規ユーザアカウントが有効化され、ログインできる状態になります。