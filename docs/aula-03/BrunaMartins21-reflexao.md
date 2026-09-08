# Aula 03 - Reflexão individual

## 1. Ambiente

Kernel observado: Linux
Memória disponível: ambiente de execução do GitHub Codespaces.
Uma informação que me chamou atenção: o sistema operacional controla os processos e também controla o acesso aos arquivos por meio de permissões.

## 2. Processo

PID observado: 8172
PPID observado: 1869

O processo é uma instância de um programa que está sendo executada pelo sistema operacional. O programa é o código, enquanto o processo é esse programa em execução, utilizando recursos do sistema.

## 3. Proteção

Quem negou a leitura do arquivo e por quê?

A leitura foi negada porque o arquivo estava com permissões restritas. O Sistema Operacional verificou as permissões antes de permitir o acesso e retornou "Permission denied". Isso mostra que o kernel controla e protege o acesso aos arquivos.

## 4. Projeto da squad

Componente escolhido: API/Serviço do Service Desk.

Esse componente será executado como um processo ou serviço no sistema operacional.

Se ele falhar, os usuários poderão deixar de abrir e consultar chamados, prejudicando o funcionamento do Service Desk.

Controle definido: registrar logs, possuir health check e permitir reinício automático do serviço em caso de falha.