FROM rust:1.58.1-buster
WORKDIR /workspace
# apt install
RUN apt update && apt install -y \
  bash-completion \
  vim && \
  apt clean
# git setting
RUN curl -o ~/.git-completion.bash https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash && \
  echo 'source ~/.git-completion.bash' >> ~/.bashrc && \
  curl -o ~/.git-prompt.sh https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh && \
  echo 'source ~/.git-prompt.sh' >> ~/.bashrc && \
  echo "PS1='\[\e[1;32m\]\u@\h\[\e[0m\]:\[\e[1;33m\]\w\[\e[1;36m\]"'$(__git_ps1)\[\e[0m\]$ '"'" >> ~/.bashrc
# rust
RUN rustup component add rustfmt
