# Projeto_Ecossistema_BigData_AWS
Projeto Criando um Ecossistema de Big Data na Nuvem 




Projeto:

Implementa um cluster para processamento distribuído de dados utilizando o serviço AWS EMR com o Hadoop MapReduce para contar palavras em um arquivo de texto armazenado no AWS S3, através de um algoritmo em Python.


---
Serviços:

Sistema de arquivos distribuídos HDFS
Framework Map Reduce (jobs)
Mapeamento de tds ocorrências por chave valor
Ordenação de ocorrências
Redução de dados agrupando as ocorrências

----

Arquitetura:

Datalake: temp; data; outputs ( S3 )

<<<<<< MapReduce; Mr Job ( Python ) >>>>

>>>> Hadoop; Master; Nodes ( EMR ) >>>>>>


----


Bucket: datalake-rodglins
Create folder: data
Create folder: output
Create folder: temp (para o hadoop utilizar durante o processamento de dados)

Criando chaves ssh para acessar as instâncias: EC2 , elastic cloud services, gestao de vm. criar chave. arquivo .pem (SSH) ou .ppk (parar usar no putty)

Identity and Access Management (IAM)>>


sudo apt-add-repository universe
sudo apt-get update
sudo apt-get install virtualenv

virtualenv --python=python3.8 venv_prod

Fazer upload de arquivo para o S3:
s3://datalake-rodglins/data/domCasmurro.txt

Criando um arquivo .mrjob.conf com as configurações de criação de instancia por ssh

Criando uma pasta .ssh com o arquivo .pem

python3 wordcount.py -r emr s3://datalake-rodglins/data/domCasmurro.txt --output-dir=s3://datalake-rodglins/output/logs1 --cloud-tmp-dir=s3://datalake-rodglins/temp/

---

Referências:

https://aws.amazon.com/pt/big-data/datalakes-and-analytics/
https://github.com/cassianobrexbit/DIO-LiveCoding-AWS
https://aws.amazon.com/pt/big-data/what-is-big-data/
http://hadoop.apache.org/
https://pt.wikipedia.org/wiki/MapReduce
https://mrjob.readthedocs.io/en/latest/
