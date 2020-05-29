.. _api_cluster_list:

----------------------
API: クラスターの一覧
----------------------

概要
++++++++

この演習では Prism Central に接続さているクラスタ一覧を取得します。
後ほどおこなう演習では得られたJSONレスポンスに含まれるクラスタのUUIDが必要となります。

.. note::

  想定演習時間: ** 5分　**



Exercise: クラスター一覧の取得
+++++++++++++++++++++++++++++++++++++++++++

#. Postmanでメイン画面にある「+」をクリックして新しいタブを作成します

#. HTTPメソッドのドロップダウンをクリックしてPOSTを選択します

    - Nutanix v3 API では POST を使ってサーバーサイドでのフィルタリング、グルーピング、ソートが標準化されています

#. クラスターをリスト表示するためのURLを入力してください

    - https://{{prism_central_ip}}:9440/api/nutanix/v3/clusters/list

#. API呼び出しのためのベーシック認証の設定をしてください

        - **Authorization** タブをクリックし、 **Basic Auth** をTypeのドロップダウンから選択してください。
        - クラスターのクレデンシャル情報を入力し, **Update Request** をクリックしてください。
            - **Username** - admin
            - **Password** - 講師から与えられた“Prism login password”を使ってください

        .. figure:: images/basicauth.png

#. メディアタイプを「JSON」にします

        - Bodyタブをクリック
        - ラジオボタン(選択ボタン)でrawを選択します
        - Textのドロップダウンをクリックし、JSONを選択します

        .. figure:: images/jsonmediatype.png

#. Bodyにリクエストペイロードの値を書きます

    - Bodyタブをクリック
    - コピーするか手打ちで空データをJSONで記載します。

    .. code-block:: bash

      {}

    .. figure:: images/apimetajson.png

#. Sendボタンをクリックし、v3 APIのリクエストをサーバーに投げます

    - 期待されるレスポンスでは一連のクラスターリソースを表示します
    - metadataの下に定義されているクラスターUUIDをメモしておいてください

  .. figure:: images/clusteruuid.png



まとめ
+++++++++
この演習ではクラスターをリスト表示するAPIの呼び出しをおこないました。
全てのNutanix v3 APIの呼び出しではクラスターUUIDが必要となります。
なお、ここで設定したクラスターの認証情報は同様に残りの演習でも利用します。
