# データベースの管理

## データベースの作成

![](<../.gitbook/assets/image (17).png>)

"Data Browser" を開きます

![](<../.gitbook/assets/スクリーンショット 2021-07-01 18.11.52.png>)

右上の "+ Database" ボタンをクリックし、

![](<../.gitbook/assets/image (34).png>)

必要な情報を入力した後、 "Save" をクリックすることで新しいデータベースを作成することができます。

"Database ID" は，データベースの識別子となっているため，後から変更できません。

なお、この操作をするためには `Add Database` の権限が必要になります。

## 情報の更新

![](<../.gitbook/assets/image (31).png>)

Data Browser で，更新したいデータベースを選択します

![](<../.gitbook/assets/image (15) (1).png>)

右上のメニューから，"Update database info" を選択します

![](../.gitbook/assets/image.png)

必要な情報を書き換えた後，"Save" を押すと情報が更新されます

なお，この操作をするためには `Write Database` の権限が必要です

## 設定の変更

![](<../.gitbook/assets/image (6).png>)

Data Browser で，設定を更新したいデータベースを選択します

![](<../.gitbook/assets/image (27).png>)

右上のメニューから，"Configure database" を選択します

![](<../.gitbook/assets/image (16).png>)

以下で各設定の変更方法を述べていきますが，変更を保存するには "SAVE" をクリックする必要があります

なお，設定の変更に `Write databases` の権限が必要です

### 入力設定の変更

![](<../.gitbook/assets/image (2).png>)

"INPUT FIELDS" タブからは，入力設定を編集できます

#### 入力項目の追加

![](<../.gitbook/assets/image (4).png>)

”＋”ボタンをクリックすると，入力項目を追加できます

![](<../.gitbook/assets/image (3).png>)

以下の項目を入力して "ADD" をクリックすると入力項目が追加されます

* Name: 新しい入力項目の名前です．データベース上ではこの値を識別子として扱っています．
* Display name: 新しい入力項目の，DataBrowser上での表示名です．
* Data type: 新しい入力項目の型です．どの値をとるかで，Data Browserからレコードを追加する時の挙動が変化します．
  * String: プレーンな入力欄に，任意の文字列が入力できるようになります．
  * Number: 昇降ボタンのついた入力欄に，数値のみを入力できるようになります．
  * Date: デートピッカーのついた入力欄に，日時のみを入力できるようになります．
* Necessity: 新しい入力項目の入力が必須であるかを決める値です．どの値をとるかで，DataBrowserからレコードを追加する時の挙動が変化します．
  * Required: この項目が未入力だとデータベースにレコードを追加できません．
  * Recommended:この項目が未入力だと，未入力のままで良いか確認が出ます．
  * Optional: この項目が未入力でも何も起こりません．
* Visibility: 新しい入力項目が公開された値かどうかを決める値です．チェックを入れると， `Read public` の権限のみを持つユーザーにはこの項目は表示されなくなります．

#### 入力項目の削除

![](<../.gitbook/assets/image (35).png>)

入力項目右側のごみ箱アイコンをクリックすると入力項目を削除できます

#### 入力項目の編集

![](../.gitbook/assets/DandD.gif)

入力項目をドラッグすると入力項目の順番を入れ替えることが出来ます

![](<../.gitbook/assets/image (32).png>)

入力項目右側の歯車アイコンをクリックすると，入力項目の設定を変更できます

### 表示設定の変更

![](<../.gitbook/assets/image (14).png>)

"DISPLAY FIELDS" タブからは，表示設定の変更が出来ます

#### レコード一覧画面に表示される項目の編集

![](<../.gitbook/assets/image (19).png>)

"+" をクリックすると項目を追加できます

![](<../.gitbook/assets/image (20).png>)

項目名右側にあるごみ箱アイコンをクリックすると，項目を削除できます

![](<../.gitbook/assets/image (1) (1).png>)

項目名をクリックすると，その項目を変更できます

![](<../.gitbook/assets/image (12) (1).png>)

項目名左側のアイコンをドラッグすると順番を変更できます

#### レコード詳細画面のタイトルに表示される項目の変更

![](<../.gitbook/assets/image (18).png>)

"Record title" 下の項目名をクリックすると，レコード詳細画面のタイトルに表示される項目を変更できます
