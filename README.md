# Password Security Crypter

Um script feito para você armazenar suas senhas de forma segura. (AES256)

## Descrição

O script utiliza a criptografia AES256 para criptografar seu arquivo de senhas. 
Após criptografado ele gera uma chave de descriptrografia e envia o arquivo para um servidor (ou uma máquina sua própria/VM), juntamente com o arquivo de password.
Os arquivos são enviados via SSH/SFTP de forma em que os dados são enviados criptogrados.

### Dependências

Você precisa ter instalado o módulo cryptography e o módulo paramiko instalados na sua máquina principal.

pip install cryptography # Instalar o cryptography
pip install paramiko
## Como usar?

A máquina que receberá o arquivo deverá estando rodando o serviço de SSH.
No Linux: service ssh start
No Windows (Powershell): 
Install-WindowsFeature OpenSSH-Server
Start-Service ssh-agent

Primeiramente o arquivo do script (cryptor.py) deve estar na mesma pasta que o arquivo de senha (password.txt, o nome pode ser alterado no script caso desejar).
Após isso, você editará o script com o número IP do host remoto, usuário e senha. Também você editar o arquivo caminho (ex: C:/Users/SEU_USER/PASSWORDS).

## Importante
A pasta deve existir e o host remoto deve estar ativo , caso contrário o script irá criptografar o arquivo de password e deixar o arquivo de descriptografia na máquina local (mesma pasta dos arquivos).
