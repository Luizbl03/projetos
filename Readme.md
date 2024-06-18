Usando o linux:
Primeiro verifiquei a versão do git. Era: git version 2.39.2 
Tentei fazer um update na versão.Esta era a versão mais recente.
Criei um diretorio.
Quando tentei fazer o primeir git add no arquivo deu o seguinte erro:
fatal: detected dubious ownership in repository at '/home/lblima/myproject'
To add an exception for this directory, call:

	git config --global --add safe.directory /home/lblima/myproject
Possivel causa apresentada foi:
Cause

A change was introduced in git 2.35.2 (and newer) to prevent a user from executing git commands in a repository owned by a different user. This is to address a security risk, CVE-2022-24765,  for more details see setup_git_directory and Git security vulnerability announced. The change to setup_git_directory prevents git invocations from executing commands on a repository owned by another user.

Tentei a seguinte solução:
chown -R username:group <path to the repository>
Funcionou.

Ao fazer o primeiro commit, deu o seguinte erro:

[master (root-commit) 2af2d18] O primeiro commit deste arquivo.
 Committer: Luiz Lima <lblima@limalinux.LIMAHOUSE>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly:

    git config --global user.name "Your Name"
    git config --global user.email you@example.com

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 16 insertions(+)
 create mode 100644 Readme.md
Tentei a solução recomendada acima.

 
