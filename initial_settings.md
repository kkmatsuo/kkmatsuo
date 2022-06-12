# 毎回 OS 更新
$ sudo apt update && sudo apt -y upgrade

# streamlit用の仮想環境を .venv_st にする。
# 事前確認(@2021/11/16)で、python3 -V >> 3.8.10

# Github actions for CI/CD
cd ai_projects && source .venv_st/bin/activate && cd test-cicd_btppp && code .

# loclal test & AWS deploy
$ cd ai_projects && source .venv_st/bin/activate && cd BTPPP && code .

# pip 依存関係の確認
$ pip check

# アップデート必要なパッケージのリスト(これは便利)
$ pip list -o

# パッケージのアップデート
$ pip install -U <package-name>

# requirements.txtに出力するときに使うと便利
 ** pip freeze と pip list では出力されるものに違いあり
$ pip freeze > requirements.txt

# git の初期設定
$ git config --global user.name "kkmatsuo"
$ git config --global user.email "i_got_666@yahoo.co.jp"

# コミットログを書くとき、 Ubuntu のデフォルトだと nano に設定されてしまうのでこれをvimに修正する。
$ git config --global core.editor 'vim -c "set fenc=utf-8"'

$ git remote add origin git@github.com:kkmatsuo/btppp.git

$ git clone git@github.com:kkmatsuo/btppp.git

# SHAP 導入時のエラー解決のため、以下実行。
$ apt install build-essential
 >> まだエラー。以下も追加。
参照：https://qiita.com/yuta_vamdemic/items/277a5a692840d06c4cd9
$ sudo apt-get install libssl-dev libffi-dev python3-dev
 >> でけた。
