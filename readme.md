# What is this?
WSLで使用するターミナルのデザインを変更する手順です。

# Setup
- 以下から好きなフォントをダウンロードする  
[ここから](https://www.nerdfonts.com/font-downloads)  
今回はCousin Nerd Fontを使う  
インストールが終わったらZIPを解凍し、使いたいフォントを右クリックしてインストールする。
Terminalの設定でそのフォントを選択する。
- HomeBrewをインストールする  
Debian系
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
sudo apt-get update
sudo apt-get install build-essential
test -d ~/.linuxbrew && eval "$(~/.linuxbrew/bin/brew shellenv)"
test -d /home/linuxbrew/.linuxbrew && eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
test -r ~/.bash_profile && echo "eval \"\$($(brew --prefix)/bin/brew shellenv)\"" >> ~/.bash_profile
echo "eval \"\$($(brew --prefix)/bin/brew shellenv)\"" >> ~/.profile
```

- デザイン変更に必要なものをインストールする

```bash
brew install jandedobbeleer/oh-my-posh/oh-my-posh
brew install screenfetch
```

以下のディレクトリに移動
```bash
cd $(brew --prefix oh-my-posh)/themes
```
[ここから](https://ohmyposh.dev/docs/themes)テーマを確認して、好きなものをいれる  
今回はkaliを選択する
```bash
cp ./kali.omp.json $HOME
```

- .bashrcに追加
```bash
eval "$(oh-my-posh init bash --config ~/kali.omp.json)"
```

