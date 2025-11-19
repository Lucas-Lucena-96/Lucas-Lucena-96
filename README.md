Impacta Streaming – Aula Prática Kafka (Data Integration)
Curso: MBA em Data Engineering
Disciplina: Integrated Data Platforms
Aluno: Lucas S L Candido
RA: 2501934

📋 Sobre o Projeto
Este repositório contém o projeto da aula prática de Data Integration com Apache Kafka, utilizando Docker, JupyterLab e Kafka UI para simular um cenário de streaming de dados de uma "rede social".

🎯 Objetivo
Demonstrar, de ponta a ponta:

✅ Geração de eventos (producer)

✅ Ingestão e transporte via Kafka (cluster com 2 brokers)

✅ Consumo dos eventos (consumer)

✅ Persistência dos dados em arquivos CSV para análise posterior

🏗️ Arquitetura da Solução
✅ Zookeeper: Coordenação do cluster Kafka

✅ Kafka 1 e Kafka 2: Dois brokers para simular ambiente com mais de um servidor

✅ Kafka UI: Interface web para inspecionar tópicos, partições e mensagens

✅ JupyterLab: Ambiente para executar os notebooks de producer e consumer

🔄 Fluxo Resumido
Producer.ipynb gera mensagens simulando eventos de usuários em uma rede social

As mensagens são publicadas em um tópico Kafka

Consumer.ipynb consome as mensagens do tópico

As mensagens consumidas são gravadas periodicamente em arquivos CSV na pasta data

📁 Estrutura de Pastas
text
impacta_streaming/
├─ docker-compose.yml
└─ notebooks/
   ├─ producer.ipynb
   ├─ consumer.ipynb
   ├─ run_jupyterlab.sh
   ├─ requirements.txt
├─ data/                # Arquivos CSV gerados pelo consumer
└─ imagens/             # Evidências de execução (prints e vídeo)
As evidências de execução, incluindo prints e vídeo, estão disponíveis na pasta imagens.

🚀 Como Executar
1. Clone o repositório:
bash
git clone https://github.com/seu-usuario/impacta_streaming.git
cd impacta_streaming
2. Suba o ambiente Docker:
bash
docker-compose up -d
3. Instale as dependências Python:
bash
pip install -r notebooks/requirements.txt
4. Acesse o JupyterLab:
O JupyterLab estará disponível em http://localhost:8888 (verifique o token no log do container ou use o script run_jupyterlab.sh).

5. Execute os notebooks:
producer.ipynb: Gera e envia eventos para o Kafka

consumer.ipynb: Consome eventos do Kafka e salva em CSV na pasta data

6. Acesse o Kafka UI:
Interface web disponível em http://localhost:8080 para monitorar tópicos e mensagens.

⚡ Observações de Performance
Escrita em CSV otimizada com buffer e encoding utf-8

Decodificação e escrita de mensagens em lote para melhor eficiência

Prints reduzidos para evitar overhead desnecessário

Producer faz flush periódico para garantir envio eficiente

O consumer cria automaticamente a pasta data para armazenar os arquivos CSV, mantendo o projeto organizado

📋 Requisitos
Docker e Docker Compose

Python 3.8+

Navegador web para acessar JupyterLab e Kafka UI

📄 Licença
Uso acadêmico.
