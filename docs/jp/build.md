# Build

## 開発

Webpack HRMを使います。
次の命令から私達がしておいた設定を使うことができます。

依存するパッケージをインストールします。

```
$ yarn
```

ビルドして実行します。

```
$ yarn run dev-start
```

このコマンドは `yarn run webpack` と `yarn run hot`を並列に実行します。つまりこのコマンドは2つのターミナルで同時にこれらのコマンドを実行するのと同じことです。

そして、Webpackが自動的にコードの変更を確認し、それを適用してくれるようになります。

もし、 `Failed to load resource: net::ERR_CONNECTION_REFUSED`というエラーが起きた場合、Boostnoteをリロードしてください。

![net::ERR_CONNECTION_REFUSED](https://cloud.githubusercontent.com/assets/11307908/24343004/081e66ae-1279-11e7-8d9e-7f478043d835.png)

> ### 注意
> 時々、直接リフレッシュをする必要があります。
> 1. コンポネントのコンストラクター関数を編集する場合
> 2. 新しいCSSクラスを追加する場合(1.の理由と同じ: CSSクラス名はコンポネントごとに書きなおされまが、この作業はコンストラクターで行われます。)

## 配布

Gruntを使います。
実際の配布は`grunt`で実行できます。しかし、これにはCodesignとAuthenticodeの仮定が含まれるので、使っては行けないです。

それで、実行ファイルを作るスクリプトを用意しておきました。

```
grunt pre-build
```

実行ファイルは`dist`から見つかります。この場合、認証されていないため、自動アップデーターは使えません。

必要であれば、この実行ファイルからCodesignやAuthenticodeなどの署名ができます。
