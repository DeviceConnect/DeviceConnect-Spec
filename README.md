# DeviceConnect-Spec
Device Connect API 仕様 ([Swagger 2.0](http://swagger.io/specification/) 形式)を定義したファイルを管理します。<br>
ここで標準化した API を Device Connect は実装します。

Device Connect システムについては、[こちら](https://github.com/DeviceConnect/DeviceConnect-Docs)を参照してください。<br>
Device Connect API の作成ガイドラインは[こちら](https://github.com/DeviceConnect/DeviceConnect-Docs/wiki/Specification-Api-Guidelines)を参照してください。


# ドキュメントの出力
ドキュメント作成において、以下のコマンドがインストールされていることを前提に説明を行います。

* Java
* cURL

[DeviceConnect-Codegen](https://github.com/DeviceConnect/DeviceConnect-Codegen) から DeviceConnect Codegen をダウンロードします。

```
$ curl -LkO https://github.com/DeviceConnect/DeviceConnect-Codegen/releases/download/codegen-v1.9.1/deviceconnect-codegen-project-1.9.1-dist.zip
$ unzip deviceconnect-codegen-project-1.9.1-dist.zip
```

DeviceConnect-Spec から最新の定義ファイルをダウンロードします。

```
$ curl -o DeviceConnect-Spec.zip -LkO https://github.com/DeviceConnect/DeviceConnect-Spec/archive/master.zip
$ unzip DeviceConnect-Spec.zip
```

ダウンロードした定義ファイルからドキュメントを作成します。

```
$ java -Dfile.encoding=UTF-8 -jar ./deviceconnect-codegen-project-1.9.1/bin/deviceconnect-codegen.jar \
        --lang deviceConnectHtmlDocs \
        --display-name Device_Connect_RESTful_API_Specification \
        --input-spec-dir ./DeviceConnect-Spec-master/api \
        --output ./docs
```

実行すると`--output`で指定したフォルダにDevice Connect APIのドキュメントが作成されます。

#### 各オプションの説明

> `--input-spec-dir`
> > 定義ファイルが置いてあるフォルダを指定します。
>
> `--output`
> > ドキュメントを出力する先のフォルダ名を指定します。<br>
> > 指定されたフォルダが存在しない場合には作成します。
>
> `--lang`
> > ドキュメントを出力するので、*deviceConnectHtmlDocs*を指定します。
>
> `--display-name`
> > ドキュメントのタイトルを指定します。

上記に記載したオプションが知りたい場合には[こちら](https://github.com/DeviceConnect/DeviceConnect-Codegen/blob/master/MANUAL.md)を参照してください。
