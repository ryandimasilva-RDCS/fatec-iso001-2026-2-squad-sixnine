# Aula 03 - Reflexão individual

## 1. Ambiente
Kernel observado: 6.8.0-1064-azure
Memória disponível: 5.8 GiB
Uma informação que me chamou atenção: o Codespace utiliza Ubuntu e tem aproximadamente 7.8 GiB de memória total.

## 2. Processo
PID observado: 14390
PPID observado: 5292
Explique com suas palavras a diferença entre programa e processo: um programa é um conjunto de instruções armazenado e um processo é esse programa sendo executado pelo sistema operacional. O PID identifica uma execução específica do processo.

## 3. Proteção
Quem negou a leitura do arquivo e por quê? O sistema operacional, pelo controle de permissões do Linux, negou a leitura porque o arquivo estava com as permissões 000, sem permissão de leitura para o usuário.

## 4. Projeto da squad
Banco de Dados.

Esse componente rodaria como quê? Um serviço/processo em execução no sistema operacional.

Se ele falhar, qual impacto de negócio aparece? O aplicativo pode ficar indisponível ou não conseguir consultar e armazenar os dados necessários para funcionar corretamente.

Qual controle deveria existir? Healthcheck, logs e mecanismo de restart para recuperar uma falha.