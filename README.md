# Comando linux
## _Comandos que eu aprendi do linux_

- dir
diretorios
```sh
dir /etc/ARQUIVOS
arquivo1  Gabriel-pasta  Gustavo-pasta  pasta1  porta
```   

- cd
trocar diretorios 
```sh
cd /local/da/pasta
```   

- pwd 
pegar a localização atual
```sh
pwd
/local/da/pasta
```   

- ls
listar os itens de dentro de uma pasta
```sh
ls 
arquivo1  Gabriel-pasta  Gustavo-pasta  pasta1  porta
```   

- ls -la
listar TODOS os itens de dentro de uma pasta
```sh
ls -la
drwxrwx--x+   5 gabrielantunes  desenvolvedores  4096 jan  8 14:37 .
drwxr-xr-x  110 root            root             4096 jan  7 16:04 ..
-rw-rw-r--    1 gustavo.cardoso gustavo.cardoso    18 jan  8 14:31 arquivo1
drwxr-x---+   2 gabrielantunes  root             4096 jan  8 14:37 Gabriel-pasta
drwxr-x---+   2 gustavo.cardoso root             4096 jan  8 15:09 Gustavo-pasta
drwxrwxr-x    2 gustavo.cardoso gustavo.cardoso  4096 jan  8 14:32 pasta1
-rwxr-xr-x    1 root            root              101 jan  7 15:41 porta
-rw-------    1 root            root            12288 jan  7 15:34 .swp

```   

- ls -latr
listar TODOS os arquivos por ordem de utilização invertida
```sh
ls -latr
-rw-------    1 root            root            12288 jan  7 15:34 .swp
-rwxr-xr-x    1 root            root              101 jan  7 15:41 porta
drwxr-xr-x  110 root            root             4096 jan  7 16:04 ..
-rw-rw-r--    1 gustavo.cardoso gustavo.cardoso    18 jan  8 14:31 arquivo1
drwxrwxr-x    2 gustavo.cardoso gustavo.cardoso  4096 jan  8 14:32 pasta1
drwxr-x---+   2 gabrielantunes  root             4096 jan  8 14:37 Gabriel-pasta
drwxrwx--x+   5 gabrielantunes  desenvolvedores  4096 jan  8 14:37 .
drwxr-x---+   2 gustavo.cardoso root             4096 jan  8 15:09 Gustavo-pasta

```   

- tail
vai ler so o final de um arquivo de texto
```sh
tail Text.txt
final do texto
```

- passwd
define ou altera a senha de um usuario
```sh
passwd usuario1
New password:*exemplo*
Retype new password:*exemplo*
passwd: password updated successfully
```
- cat 
concactena o arquivo e printa oque tiver que printar
```sh 
cat exemplo
"Isto é um exemplo"
```

- sudo
executa comandos como administrador 

- history
mostra o historico de comandos que voce utilizou no usuario conectado
```sh
history
cat
passwd
tail
ls -latr
-ls -la
```

- groups
mostra o(s) grupo(s) que o usuario esta
```sh
groups usuario1
usuario1: usuarios ADM suporte
```

- chown
muda o dono do arquivo ou grupo
```sh
chown usuario1:ADM /local/da/pasta
```

- adduser 
adciona um usuario "configurado"
```sh
adduser usuario2
info: Adding user `usuario2´
info: Selecting UID/GID from range 1000 to 59999 ...
info: Adding new group `usuario2' (1009) ...
info: Adding new user `usuario2' (1009) with group `usuario2 (1009)' ...
info: Creating home directory `/home/usuario2' ...
info: Copying files from `/etc/skel' ...
New password:teste
Retype new password:teste
passwd: password updated successfully
Changing the user information for teste
Enter the new value, or press ENTER for the default
        Full Name []: 
        Room Number []:
        Work Phone []:
        Home Phone []:
        Other []:
Is the information correct? [Y/n] y
info: Adding new user `usuario2' to supplemental / extra groups `users' ...
info: Adding user `usuario2' to group `users' ...

```

- useradd 
adiciona um usuario não "configurado"
```sh
useradd teste
```
- Help
Ajuda em geral

- sudo visudo
altera a pasta sudoers
```sh
visudo
*SUDOERSFILE*
```

- man 
ele te da a referencia de um comando
```sh
man passwd
PASSWD(1)                                                                 User Commands                                                                 PASSWD(1)

NAME
       passwd - change user password

SYNOPSIS

       passwd [options] [LOGIN]

DESCRIPTION
       The passwd command changes passwords for user accounts. A normal user may only change the password for their own account, while the superuser may change
       the password for any account.  passwd also changes the account or associated password validity period.

   Password Changes
       The user is first prompted for their old password, if one is present. This password is then encrypted and compared against the stored password. The user
       has only one chance to enter the correct password. The superuser is permitted to bypass this step so that forgotten passwords may be changed.

       After the password has been entered, password aging information is checked to see if the user is permitted to change the password at this time. If not,
       passwd refuses to change the password and exits.

       The user is then prompted twice for a replacement password. The second entry is compared against the first and both are required to match in order for the
       password to be changed.

       Then, the password is tested for complexity. As a general guideline, passwords should consist of 6 to 8 characters including one or more characters from
       each of the following sets:

       •   lower case alphabetics

       •   digits 0 thru 9

       •   punctuation marks

       Care must be taken not to include the system default erase or kill characters.  passwd will reject any password which is not suitably complex.
```
 
- O comando init no Linux é usado para inicializar diferentes estados do sistema (runlevels), controlando quais serviços e processos estarão ativos. Cada runlevel é projetado para atender a uma necessidade específica. Confira os principais exemplos:

```sh
init 0: Desliga o sistema de forma segura.

init 1: Entra no modo de usuário único, ideal para manutenção ou recuperação, onde apenas o administrador (root) tem acesso.

init 2: Ativa o modo multiusuário sem suporte de rede.

init 3: Habilita o modo multiusuário com rede, normalmente usado em servidores sem interface gráfica.

init 4: Runlevel não utilizado por padrão, podendo ser personalizado conforme as necessidades do sistema.

init 5: Inicia o modo multiusuário com interface gráfica, geralmente usado em desktops.

init 6: Reinicializa o sistema.
```

- O Bash (Bourne Again Shell) é um interpretador de comandos usado como interface entre o usuário e o sistema operacional, sendo padrão na maioria das distribuições Linux. Ele permite executar comandos, criar scripts para automatizar tarefas e gerenciar processos do sistema. Além disso, oferece suporte a variáveis, loops e condições para operações avançadas.

1. Criando o Script de Backup
Abra um editor de texto e crie um script chamado backup.sh:
```sh
bash
Copiar código
#!/bin/bash

# Diretório de origem
origem="/home/usuario/documentos"

# Diretório de destino
destino="/home/usuario/backups"

# Nome do arquivo de backup com a data atual
arquivo="backup-$(date +%F).tar.gz"

# Criando o backup
tar -czf "$destino/$arquivo" "$origem"

# Mensagem de confirmação
echo "Backup criado em: $destino/$arquivo"
```
2. Tornar o Script Executável
Depois de salvar o arquivo, torne-o executável com o comando:
```sh
bash
Copiar código
chmod +x backup.sh
```

3. Executar o Script
Para criar o backup, basta executar o script:
```sh

bash
Copiar código
./backup.sh

```