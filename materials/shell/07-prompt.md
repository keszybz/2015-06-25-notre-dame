Instruction to add color to shell prompt (and show git directory name)

The best to execute this is to select everything and simply paste it
into a terminal. It will append some lines to `.bashrc` file in home
directory.

~~~ {.bash}
curl -o ~/git-prompt.sh https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh
echo '. ~/git-prompt.sh' >> ~/.bashrc
echo 'PROMPT_DIRTRIM=1' >> ~/.bashrc
echo 'HOST_COLOR=32' >> ~/.bashrc
echo "PS1='"'\[\033[01;${HOST_COLOR}m\]\u@\h\[\033[00m\] \[\033[01;34m\]\w\[\033[00m\]\[\033[01;35m\]$(__git_ps1 " (%s)")\[\033[00m\]$ '"'" >> ~/.bashrc
exec bash
~~~

![Example output (user "zbyszek", host "my-machine", directory "~/something/something/shell", git branch "gh-pages")](fig/color-prompt.png)

Longer explanation:

1. `curl` downloads a file which extracts information about git branch
   and saves it in your home directory
2. `echo ... > ~/.bashrc` commands append lines at the end of your
   `.bashrc` file. You can view the results in any editor.
3. `exec bash` simply restarts your shell, so you can see the effect.
