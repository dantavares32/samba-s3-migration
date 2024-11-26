# samba-s3-migration
Criação de um servidor samba e fazer a migração para a AWS S3

# Projeto: Migração de Servidor Samba para Amazon S3

## Descrição

Este projeto tem como obejtivo configurar um servidor Samba para compartilhar arquivos e migrá-los para o Amazon S3. A configuração foi feita em um servidor Ubuntu e inclui a instalação do Samba, configuração de compartilhamento de arquivos e o uso do AWS CLI para sincronizar os arquivos com o S3.

## Tecnologias Que Utilizei Nesse Projeto
- **Samba**: Para compartilhar arquivos localmente.
- **Amazon S3**: Para armazenar arquivos na nuvem.
- **AWS CLI**: Para interagir com o S3.
- **Ubuntu Server**: Sistema operacional usado para a configuração do servidor.

## Passos Que Realizei

### 1. Instalação e Configuração do Samba
- O Samba foi instalado e configurado no servidor Ubuntu para criar um compartilhamento de arquivos.
- O diretório `/srv/samba/arquivos` foi configurado para ser compartilhado com permissões adequadas.

### 2. Configuração do Bucket S3
- Um bucket S3 foi criado na AWS.
- O versionamento foi habilitado no bucket para controlar alterações de arquivos.
- Políticas de acesso foram configuradas para garantir a segurança no armazenamento de dados.

### 3. Sincronização dos Arquivos
- O AWS CLI foi instalado e configurado para permitir a sincronização dos arquivos do servidor Samba para o bucket S3.
- O script `s3_sync.sh` foi criado para automatizar o processo de backup e sincronização.

## Como Rodar o Projeto

### 1. É Preciso Instalar o Samba:
```pelo bash do ubuntu
sudo apt update
sudo apt install samba samba-common

### 2. Configurar Samba
## Utilizando mkdir para criar um diretorio e chmod para alterar algum permissão de arquivo
sudo mkdir -p /srv/samba/arquivos
sudo chmod -R 0777 /srv/samba/arquivos

