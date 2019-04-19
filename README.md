# Common-Understanding（ドリルししゃもでの共通認識）
- ライブラリ: ツール 
- ディレクトリ: フォルダ 
## 当日の役割
- tozastation: フロントエンド．バックエンド
- tekoneko1997: フロントエンド，UIデザイン，スライド作成
- butachin: フロントエンド，車運転
- ShotaroOkada: フロントエンド，ファシリテート，発表
## 命名規則の確立
### ディレクトリ
- １単語で収める．２単語以上にはしない．
- ex: domain, infrastructure
### 変数
- Lower Camel Case
- ex: userId, accessToken
### 関数
- Lower Camel Case
- ex: getUserId, getUserName
### クラス
- Upper Camel Case
- ex: UserService, LoginRepository
## コーディングルール
### インスタンス生成時:
`new`は付けない
### コンストラクタ定義
コンストラクタ引数に`@required`を付け必須項目に  
nullが代入された時に警告を出すため，`assert`を追加
```
LoginBloc({
    @required this.userService,
    @required this.authenticationBloc,
  })  : assert(userService != null),
        assert(authenticationBloc != null);
```
## アーキテクチャ