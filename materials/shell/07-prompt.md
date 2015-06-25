~~~ {.bash}
$ curl -o ~/git-prompt.sh https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh
$ echo '. ~/git-prompt.sh' >> ~/.bashrc
$ echo 'PROMPT_DIRTRIM=1' >> ~/.bashrc
$ echo 'HOST_COLOR=32' >> ~/.bashrc
$ echo "PS1='"'\[\033[01;${HOST_COLOR}m\]\u@\h\[\033[00m\] \[\033[01;34m\]\w\[\033[00m\]\[\033[01;35m\]$(__git_ps1 " (%s)")\[\033[00m\]$ '"'" >> ~/.bashrc
$ exec bash
~~~
