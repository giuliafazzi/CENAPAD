# 🖥️ CENAPAD

# Tópicos
1. [Inicialização do ambiente virtual](#inicializa%C3%A7%C3%A3o-do-ambiente-virtual)
2. [Execução de scripts](#execu%C3%A7%C3%A3o-de-scripts)
3. [Status dos jobs](#status-dos-jobs)
4. [Transferência de arquivos](#transfer%C3%AAncia-de-arquivos)

## Inicialização do ambiente virtual

Ao acessar o ambiente Lovelace pela primeira vez, execute os seguintes comandos no terminal
```PowerShell
# Carregar o Python e outros pacotes adicionais
$ module load python/3.8.11-gcc-9.4.0

# Instalar, criar e ativar um virtual env
$ pip install --user virtualenv
$ virtualenv -p python3 <NOME DO AMBIENTE>
$ source <NOME DO AMBIENTE>/bin/activate

# Instalar pacotes necessários para o seu projeto
$ pip install <NOME DO PACOTE>
# ou o seguinte comando caso você já possua um arquivo requirements.txt
$ pip install -r requirements.txt
```


## Execução de scripts

Para executar o código desejado, é necessário que o script seja enviado para uma fila de execução por meio do seguinte comando:
```PowerShell
$ qsub <NOME DO ARQUIVO>
```

Para cancelar a execução de um job, basta usar qdel:
```PowerShell
$ qdel <ID DO JOB>
```


## Status dos jobs

Para acompanhar os status dos jobs e filas de execução, basta acessar a página do ambiente [Lovelace](https://www.cenapad.unicamp.br/parque/jobsLovelace) ou executar o seguinte comando para mostrar exclusivamente as suas submissões:
```PowerShell
$ qstat -u $USER
```

## Transferência de arquivos

Para a transferência de arquivos da sua máquina para o CENAPAD, é possível utilizar o comando abaixo:
```PowerShell
$ scp -P 31459 <CAMINHO PARA O ARQUIVO> <SEU USUÁRIO>@cenapad.unicamp.br:~/homelovelace/<CAMINHO FINAL>
```

Já para o cenário oposto, basta inverter a ordem dos caminhos de origem e destino:
```PowerShell
$ scp -P 31459 <SEU USUÁRIO>@cenapad.unicamp.br:~/homelovelace/<CAMINHO PARA O ARQUIVO> <CAMINHO LOCAL FINAL>
```
