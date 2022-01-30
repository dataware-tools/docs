# 2. Auth0 のテナントを作る

Dataware-tools のウェブアプリケーションではユーザの認証基盤として Auth0 を使用しています。  
従って、Dataware-tools をデプロイする事前準備として Auth0 に新しいテナントを作る必要があります。

Auth0 のテナントの作成は以下の手順で行うことができます。



### 1. Auth0 にサインアップする

[Auth0: Secure access for everyone. But not just anyone.](https://auth0.com/jp)

![](../../../.gitbook/assets/_2021-06-21_17.21.02.png)

右上の「無料トライアル」をクリックし、必要な情報を入力してアカウントを作成します。

アカウント作成が完了したらテナント作成のウィザードが始まるので、指示に従って進めます。



### 2. アプリケーションの作成

テナントが作成できたら、以下の手順でアプリケーションを作成します。

![](../../../.gitbook/assets/_2021-06-21_17.26.02.png)

右上の "Create Application" をクリック

![](../../../.gitbook/assets/_2021-06-21_17.26.35.png)

Name に "dataware-tools" と入力し、"Single Page Web Applications" を選択

![](../../../.gitbook/assets/_2021-06-21_17.28.22.png)

画面が切り替わったら "Settings" をクリック

![](../../../.gitbook/assets/_2021-06-21_17.28.34.png)

"Domain" と "Client ID" に表示されている値は後ほど使うのでどこかにメモしておきます

![](../../../.gitbook/assets/_2021-06-21_17.30.12.png)

下の方にスクロールし、以下の項目を設定します

* Allowed Callback URLs: `https://<dataware-toolsのデプロイ先のドメイン名>,https://<dataware-toolsのデプロイ先のドメイン名>/callbacks`
* Allowed Logout URLs: `https://<dataware-toolsのデプロイ先のドメイン名>/`
* Allowed Web Origins: `https://<dataware-toolsのデプロイ先のドメイン名>/`
* Allowed Origins (CORS): `https://<dataware-toolsのデプロイ先のドメイン名>/`

![](../../../.gitbook/assets/_2021-06-21_17.30.35.png)

最下部の "Save Changes" をクリックして保存します



### 3. API の作成

アプリケーションが作成できたら、次に以下の手順でAPIを作成します。

![](../../../.gitbook/assets/_2021-06-21_17.36.46.png)

左側の "APIs" をクリック

![](../../../.gitbook/assets/_2021-06-21_17.36.50.png)

"Create API" をクリック

![](../../../.gitbook/assets/_2021-06-21_17.40.25.png)

この図の様に以下の項目を入力します

* Name: `dataware-tools`
* Identifier: `https://<dataware-toolsのデプロイ先のドメイン名>/`

![](../../../.gitbook/assets/_2021-06-21_17.42.07.png)

APIを作成したら、 "Settings" を開きます

![](../../../.gitbook/assets/_2021-06-21_17.42.25.png)

下部の、"Enable RBAC" と "Add Permissions in the Access Token" をオンにし、Save します

![](../../../.gitbook/assets/_2021-06-21_17.44.30.png)

次に、 "Permissions" に移動し、

![](../../../.gitbook/assets/_2021-06-21_17.45.08.png)

図の様な Permission を追加します

###

### 4. ユーザの作成

#### 4.1. Auth0内にユーザを作成する

![](../../../.gitbook/assets/_2021-06-21_17.48.46.png)

Auth0 内にユーザを作成するには、左側の "User Management" → "Users" をクリックし、 "Create User" をクリックします

![](../../../.gitbook/assets/_2021-06-21_17.51.44.png)

アカウント情報を入力し、"Create" をクリックする



**※以下は特権ユーザに対してのみ実施する作業です**

![](../../../.gitbook/assets/_2021-06-21_17.52.13.png)

"Permissions" を選択し、

![](../../../.gitbook/assets/_2021-06-21_17.52.19.png)

"Assign Permissions" をクリックします

![](../../../.gitbook/assets/_2021-06-21_17.52.29.png)

"dataware-tools" を選択し、

![](../../../.gitbook/assets/_2021-06-21_17.52.36.png)

"admin:user" にチェックを入れて "Add Permissions" をクリックします



#### 4.2 Auth0外のアカウントを使用する

![](../../../.gitbook/assets/_2021-06-21_17.57.40.png)

Auth0 では Social 機能を使うことで Auth0 の外部のアカウント (例えば Google, GitHubなど) を使用して認証することができます。

詳しくは Auth0 のヘルプを参照してください。



### 5. app-user-manager用のセットアップ

以下は `app-user-manager` を使えるようにするための作業です。

![](../../../.gitbook/assets/_2021-06-21_18.00.51.png)

"Extensions" 画面に移動し、

![](../../../.gitbook/assets/_2021-06-21_18.01.00.png)

"Auth0 Authorization" という Extension をインストールします

![](../../../.gitbook/assets/_2021-06-21_18.01.07.png)

設定は変更せず "Install" でインストールできます

![](../../../.gitbook/assets/_2021-06-21_18.01.22.png)

その後、 "Applications" に移動し、 "auth0-authz" をクリックします

![](../../../.gitbook/assets/_2021-06-21_18.01.28.png)

この画面に表示される "Domain", "Client ID", "Client Secret" を `api-permission-manager` のデプロイ時に使用します
