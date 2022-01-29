# 環境構築

## WSL2

[ガイド](https://docs.microsoft.com/ja-jp/windows/wsl/install-win10)に従い、WSL2をインストールする。  
Linuxディストリビューションは`Ubuntu 20.04 LTS`を使用する。

## Ubuntu 20.04

1. Windowsで`wsl -d Ubuntu-20.04`を実行しUbuntuを起動する。
1. エクスプローラーから`\\wsl$\Ubuntu-20.04`にアクセスし、プロジェクトを任意の場所に移動させる。  
1. 以下の設定は任意で行う。
   - `wsl -s Ubuntu-20.04`  
     既定のディストリビューションを`Ubuntu-20.04`に設定する。
   - `ubuntu2004 config --default-user root`  
     デフォルトユーザをrootに変更する。

## Docker

[ガイド](https://docs.docker.com/docker-for-windows/wsl/)に従いDockerをインストールし、WSL2バックエンドで動作するよう設定する。

## VSCode

1. [VSCode](https://code.visualstudio.com/download)をインストールする。
1. VSCodeに以下の拡張機能をインストールする。
   - [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
   - [Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl)
   - [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
1. Ubuntuで以下のコマンドを実行する。
   - `code {project directory path}`
1. 起動したVSCodeでコマンドパレットで以下を実行する。
   - `Remote-Containers: Reopen in Container`

## Rust

### Windows向けBuild方法

以下のコマンドを順に実行すると、`target/x86_64-pc-windows-gnu/debug/`以下に`.exe`が生成される。

  1. `apt update`
  1. `apt install -y mingw-w64`
  1. `rustup target add x86_64-pc-windows-gnu`
  1. `cargo build --target x86_64-pc-windows-gnu`
