.. _api_image_list:

----------------------
API: イメージの一覧
----------------------

概要
++++++++

この演習では受講者のかたはクラスターのイメージ(仮想マシンになるテンプレート)の一覧を得ます。
あとの演習では得られたレスポンスのJSONに含まれるイメージのUUIDが必要となります。
これらのイメージはAHVのイメージサービスという機能で管理されています。

.. note::

  想定される演習時間: **5 MINUTES**



Exercise: List the images on the cluster
+++++++++++++++++++++++++++++++++++++++++++

#. Postmanの「+」ボタンをクリックして新しいリクエストのタブを作成してください

#. HTTPメソッドをPOSTにしてください

    - Nutanix API v3 ではPOSTメソッドを使ってサーバーサイドのフィルタリング、グルーピング、ソートを実施しています 

#. イメージ一覧を得るためのURLを入力してください

    - https://{{prism_central_ip}}:9440/api/nutanix/v3/images/list

#. リクエストにベーシック認証の設定をします

    - 前回までの演習と全く同じ手順で設定してください
    - v3 API はHTTPをステートレス(状態がない)なプロトコルとして扱います。そのため、認証はAPIの呼び出しごとに毎回おこなわれます

#. メディアタイプを application/json にしてください

    - 具体的な方法は最初の演習にあります

#. ボディを記述します

    - ボディタブをクリックしてください
    - 以下の空の辞書データをコピーするなり書くなりしてください

    .. code-block:: bash

      {}

    .. figure:: images/apimetajson.png

#. Sendボタンを押して v3 API を呼び出してください

  - レスポンスにはアレイ(リスト)形式でイメージの一覧があります
  - 「CentOS7」というイメージのmetadataにあるUUIDをメモしておいてください

    .. figure:: images/centosuuid.png


  - 「Windows2016」というイメージのmetadataにあるUUIDをメモしておいてください

    .. figure:: images/windowsuuid.png