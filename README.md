# cli-client-atcoder
AtCoderのコマンドライン提出クライアントです。

## インストール

* `PATH` の通ったところに `bin/cca` を好きな名前で置いてください。
* 回答を git 管理し、直下に `templates` ディレクトリをコピーしてください。
  * または `~/.cli-client-atcoder` に以下を記述してください。
    ```
    atcoder_assert_tmplroot() {
        TMPLROOT=templatesディレクトリ場所
    }
    ```

## 要求

- curl
- bash

## 使い方

```
% cca help
/usr/local/bin/cca <サブコマンド> [引数...] - AtCoder 提出クライアント
以下のサブコマンドが利用可能です。

check-logged-in (または whoami)
	 AtCoderへのログイン状態を表示します。

login
	 AtCoderへログインします。IDとパスワードの入力を要求します。
	 ログイン状態は /home/pla/.atcoder-cookie ファイルにセッションとして保持されます。

logout
	 AtCoderをセッションログアウトします。

md
	 コンテストの全タスクのディレクトリを掘ります。
	 コンテスト名(URLに表示されているもの)のディレクトリ下で実行してください。
	 作成されるディレクトリは a b c ... のようになります。
	 例) ~/work/abc188$ cca md

mkdir
	 コンテストの全タスクのディレクトリを掘ります。
	 コンテスト名(URLに表示されているもの)のディレクトリ下で実行してください。
	 作成されるディレクトリは abc188_a abc188_b ... のように、各タスクのURLのものになります。
	 タスク名の末尾がアルファベット一文字で定まらないようなコンテスト（abs等）で使います。

init (または i, gen)
	 引数: [template_id]
	 タスクディレクトリ下に回答テンプレートを生成します。タスクディレクトリ下で実行してください。
	 例) ~/work/abc188/a$ cca init
	 例) ~/work/abc188/b$ cca init bash

switch
	 引数: <template_id>
	 タスクディレクトリ下の回答テンプレートを別言語に切り替えます。タスクディレクトリ下で実行してください。
	 例) ~/work/abc188/a$ cca switch bash

edit (または e)
	 エディタを起動して回答を編集します。タスクディレクトリ下で実行してください。
	 デフォルトでは EDITOR 環境変数が使われます。
	 設定ファイルで atcoder_edit() シェル関数を定義してカスタマイズできます。

fetch
	 タスクディレクトリ下にサンプル入出力をダウンロードして保存します。

test (または t)
	 サンプル入力で回答を実行し、サンプル出力との結果の一致をチェックします。

submit (または sub, s)
	 回答を提出します。提出前にサンプル入出力と比較し、一致しない場合は中止します。

force-submit
	 回答を提出します。サンプル入出力との比較は行いません。

help
	 このヘルプを表示します。

連絡先: https://github.com/plaster/cli-atcoder
```
