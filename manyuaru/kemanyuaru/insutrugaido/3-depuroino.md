# 3. デプロイ前の準備

### MongoDB サーバの構築

Dataware-tools ではデータのメタ情報の保存先として MongoDB を使用します。

Dataware-tools のデプロイを行う前に MongoDB サーバを用意してクラスタからアクセスできる状態にしていただくか、以下のリンク先を参照して Dataware-tools のデプロイ先と同じクラスタに MongoDB のサーバをデプロイして下さい。

{% embed url="https://github.com/bitnami/charts/tree/master/bitnami/mongodb" %}

### MongoDB サーバへのユーザ登録

Dataware-tools の Web API が使用するユーザアカウントを MongoDB に登録します。

まず、MongoDB サーバにアクセスできる環境で以下のコマンドを実行します:

```
MONGODB_HOST=<MongoDB サーバのドメインまたはIPアドレス>
MONGODB_ROOT_PASSWORD=<MongoDB サーバのrootアカウントのパスワード>
mongo --host ${MONGODB_HOST} -u root -p ${MONGODB_ROOT_PASSWORD} --eval "db.createUser({user:\"datawaretools\",pwd:\"datawaretools\",roles:[{role:\"readWrite\",db:\"datawaretools\"}]})" admin
```

次に、作成したアカウントでログインできることを以下のコマンドにより確認します:

```
mongo --host ${MONGODB_HOST} -u datawaretools -p datawaretools --authenticationDatabase admin
```

エラーが表示されなければ完了です。
