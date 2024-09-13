# Password Security Crypter

Um script para armazenamento de suas senhas de forma segura. (criptografia AES256)

## Descrição

O script utiliza a criptografia AES256 para criptografar seu arquivo de senhas. 
Após criptografado ele gera uma chave de descriptrografia e envia o arquivo para um servidor (ou uma máquina sua própria/VM), juntamente com o arquivo de password.
Os arquivos são enviados via SSH/SFTP de forma em que os dados são enviados criptogrados.

### Dependências

Você precisa ter instalado o módulo cryptography e o módulo paramiko instalados na sua máquina principal.



```
pip install cryptography
```



```
pip install paramiko
```


## Como usar?

A máquina que receberá o arquivo deverá estando rodando o serviço de SSH.

* No Linux: 

```
service ssh start
```

* No Windows (Powershell): 


```
Install-WindowsFeature OpenSSH-Server
```



```
Start-Service ssh-agent
```


Primeiramente o arquivo do script (cryptor.py) deve estar na mesma pasta que o arquivo de senha (password.txt, o nome pode ser alterado no script caso desejar).
Após isso, você editará o script com o número IP do host remoto, usuário e senha. Também você editar o arquivo caminho (ex: C:/Users/SEU_USER/PASSWORDS).

## Importante
A pasta deve existir e o host remoto deve estar ativo , caso contrário o script irá criptografar o arquivo de password e deixar o arquivo de descriptografia na máquina local (mesma pasta dos arquivos).

ChatGPT: 

Aqui está uma versão melhorada da descrição para o seu projeto no GitHub:


---


# Password Security Crypter 

Um script eficiente para armazenar suas senhas de forma segura, utilizando criptografia AES-256.

## Descrição 
O **Password Security Crypter**  utiliza o algoritmo de criptografia AES-256 para proteger o seu arquivo de senhas. Após criptografar o arquivo, ele gera uma chave de descriptografia e envia o arquivo criptografado para um servidor remoto ou uma máquina virtual de sua escolha. A transferência é realizada via SSH/SFTP, garantindo que todos os dados sejam enviados de forma segura e criptografada.
### Dependências 

Para utilizar este script, você precisará instalar os seguintes módulos em sua máquina principal:
 
- **cryptography** 

```Copiar código
pip install cryptography
```
 
- **paramiko** 

```Copiar código
pip install paramiko
```

## Como Usar 

Certifique-se de que a máquina que receberá o arquivo esteja com o serviço SSH ativo:
 
- **Linux:** 

```Copiar código
sudo service ssh start
```
 
- **Windows (Powershell):** 

```Copiar código
Install-WindowsFeature OpenSSH-Server
Start-Service ssh-agent
```
Coloque o script (`cryptor.py`) na mesma pasta que o arquivo de senhas (`password.txt`). Se desejar, você pode alterar o nome deste arquivo no próprio script.Em seguida, edite o script para incluir o endereço IP da máquina remota, o nome de usuário e a senha de acesso. Também é necessário configurar o caminho de destino do arquivo na máquina remota (ex: `C:/Users/SEU_USER/PASSWORDS`).
## Importante 

- A pasta de destino deve existir na máquina remota, e o host deve estar ativo no momento da execução do script.

- Caso o host remoto esteja indisponível, o arquivo de senhas será criptografado e a chave de descriptografia será mantida localmente, na mesma pasta dos arquivos originais.
