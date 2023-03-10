# Criando um ambiente virtual
- Instalar a versão do python necessária (aqui utilizamos a versão 3.9)

- Primeiro, atualizar os pacotes do ubuntu: 
--> sudo apt update 
--> sudo apt upgrade

- Agora vamos ativar o repositório do ubuntu que permite ter diferentes versões do python em uma mesma máquina:
--> sudo add-apt-repository ppa:deadsnakes/ppa

- Instalar o python:
--> sudo apt install python3.9

- Instalar o pacote de ambientes virtuais do python 3.9 para criar ambientes virtuais para instalar o airflow da forma mais organizada possivel:
--> sudo apt install python3.9-venv

- Dentro de uma pasta, podemos criar o ambiente virtual onde será instalado o airflow
--> python3.9 -m venv venv

- Rodar o ambiente virtual do airflow:
--> source venv/bin/activate

- Com o ambiente virtual ativado, podemos instalar o airflow:
--> pip install 'apache-airflow==2.3.2' --constraint "https://raw.githubusercontent.com/apache/airflow/constraint-2.3.2/constraints-3.9.txt"

- Com o airflow instalado, podemo rodar localmente. Antes disso, precisaremos exporta a variável de ambiente:
--> export AIRFLOW_HOME=~/Documents/airflow-alura

- Precisaremos exportar a variável sempre que rodarmos o airflow.


- Rodar localmente o airflow. Assim, sera iniciado o banco de dados padrão do airflow, será criado um usuário e senha para acessar o airflow, e também os dois principais serviços do airflow (WebServer e Scheduler):  
--> airflow standalone