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
