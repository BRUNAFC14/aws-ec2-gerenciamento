🧠 Projeto: Gerenciamento de Instâncias EC2 com AMI e Snapshots EBS
📄 Descrição

Este projeto foi desenvolvido como parte do desafio prático da DIO, com o objetivo de consolidar conhecimentos sobre EC2, AMIs, EBS e S3 na AWS.
Foram criadas e documentadas instâncias, volumes e imagens, além de exploradas boas práticas de armazenamento e versionamento de ambiente.

🏗️ Arquitetura Base (AMI + EC2 + EBS + RDS)

Explicação

EC2: instância principal para execução do ambiente.

D-EBS / E-EBS: volumes de armazenamento conectados à EC2, usados para dados e logs.

RDS: banco de dados relacional gerenciado.

Actor: usuário que envia arquivos e interage com a aplicação hospedada.

Essa arquitetura demonstra o fluxo entre a instância EC2, volumes EBS e o banco RDS.

☁️ Arquitetura Serverless (S3 + Lambda + DynamoDB)

Explicação

S3: armazenamento de objetos (arquivos enviados pelo usuário).

Lambda: execução de funções (NodeJS / Python / .NET) para processar os arquivos.

DynamoDB: persistência dos metadados processados.

AWS CLI: ferramenta usada para transferir arquivos para o S3.

Essa segunda arquitetura ilustra um cenário mais avançado, sem servidor (serverless), integrando serviços AWS de forma automatizada.

⚙️ AMI Base

A AMI base é uma imagem customizada da instância EC2 que inclui:

Sistema operacional configurado (ex: Amazon Linux ou Ubuntu);

Aplicações e pacotes necessários;

Permissões e políticas associadas à instância;

Snapshot dos volumes EBS.

Essa AMI pode ser reutilizada para criar novas instâncias idênticas rapidamente.
