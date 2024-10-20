# uv-sample-project

uv で始める Python プロジェクトのソースコードです

## はじめに

## 1.インストール編

基本的には、公式の誘導に従います。
(Windows へのインストールは本稿では扱わないので公式見てね)

### 1.1. ダウンロードする

まず、curl コマンドを実行しましょう。適したバイナリファイルが落ちてきます。

```sh
curl -LsSf https://astral.sh/uv/install.sh | sh
```

元からある、pip からも落とすこともできますが、pip に依存する形を好まないので割愛します。
rye と異なり、 $HOME/.cargo/env ($HOME/.cargo/env.fish)に PATH が通っていれば良いようです。

```sh
source $HOME/.cargo/env (sh, bash, zsh)
source $HOME/.cargo/env.fish (fish)
```

### 1.2. Shell の補完スクリプトを入れる

rye と同様に shell 補完スクリプトが提供されているため、ついで入れましょう。

```sh
# Determine your shell (e.g., with `echo $SHELL`), then run one of:
echo 'eval "$(uv generate-shell-completion bash)"' >> ~/.bashrc
echo 'eval "$(uv generate-shell-completion zsh)"' >> ~/.zshrc
echo 'uv generate-shell-completion fish | source' >> ~/.config/fish/config.fish
echo 'eval (uv generate-shell-completion elvish | slurp)' >> ~/.elvish/rc.elv
```

### 1.3. uv 自体をアップデートする

最後に uv 自体をアップデートしましょう。

```sh
uv self update
```

## 2. Python インストール編

uv では、pyenv のように Python のバージョン管理をすることが可能です。

```sh
uv python install 3.13
```

一度に複数のバージョンをインストールすることも可能です。
(リビジョンまで指定可能です)

```sh
uv python install 3.11.7 3.12 3.13
```

```sh
>>>  Searching for Python versions matching: Python 3.11.7
>>>  Searching for Python versions matching: Python 3.12
>>>  Searching for Python versions matching: Python 3.13
>>>  Installed 3 versions in 7.05s
>>>   + cpython-3.11.7-macos-x86_64-none
>>>   + cpython-3.12.7-macos-x86_64-none
>>>   + cpython-3.13.0-macos-x86_64-none
```

インストールした Python は下記のように確認可能です。
