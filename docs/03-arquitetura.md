# Arquitetura do Projeto

## Mapeamento para Sistemas Operacionais

### 1. Qual é a versão do kernel?Qual distribuição aparece?
Linux codespaces-19280f 6.8.0-1052-azure #58~22.04.1-Ubuntu SMP Thu Mar 26 05:02:21 UTC 2026 x86_64 x86_64 x86_64 GNU/Linux ;
Identificamos a versão "Ubuntu 24.04.4 LTS"

### 2. Quanto de memória RAM está disponível?Quanto de filesystem está disponível?
De acordo com o baseline coletado, esse sistema apresente 5.4Gi disponiveis de memória RAM ; Ele apresenta 20GB de filesystem disponiveis

### 3. Quais processos chamaram atenção no baseline?
2236    2212 codespa+ Sl   10.2  6.4 MainThread;
   2694    2267 codespa+ Sl    0.3  3.7 MainThread
### 4. Para o cenário da squad, qual recurso tende a ser mais crítico?
De acordo com nossas análises, a memória tende a ser o recurso mais critico pois nooso projeto exige que alguns processos sejam execultados simultaneamente, como o banco de dados. o seu consumo elevado pode causar lentidão ou até interrupção desses processos. Dito isso, é necessario monitorar o uso da memória e estabelecer alertas para o uso exessivo.

### 5. Qual componente da arquitetura da squad executará como processo ou serviço?
Os componentes que executam processos e serviços são o backend e o banco de dados. Sendo o backend responsável pelos processamentos dos chamados e execução da lógica.O Banco de Dados é responsável pelo armazenamento e gerenciamento dos dados ultilizados pelo sistema.

### 6. Se esse processo morrer, qual função de negócio deixa de funcionar?
Se o Backend parar de funcionar, os chamados dos usuários não conseguirão ser processados.
Se o Banco de Dados parar, o Backend não conseguirá consultar, inserir ou atualizar os dados necessários para executar as funcionalidades do sistema.

### 7. A solução precisa reiniciar automaticamente? registrar log? gerar alerta? possuir health check? Registre uma decisão.
Para solucionar este problema é nescessário possuir um health check para verificar quais serviços estão funcionando e gerar alertas para indentificar as falhas.

### 8. Quem negou o acesso: o programa, o SSD ou o kernel?
Kernel

### 9. Qual operação relacionada a arquivo aparece ou seria esperada no trace?
"trace indisponivel"

### 10. Por que a aplicação não consegue simplesmente ignorar a permissão?
Pois ela não tem autoridade para decidir que a permissão não importa.Ela segue apenas comandos e limitações impostas.

### 11. No seu cenário de negócio, qual arquivo/diretório/volume teria risco equivalente?
Os dados dos usuários, que podem ser alterados apenas pelo gerente.

## Mapeamento para Sistemas Operacionais

Componente	         Executa como	      Recurso/abstração do SO	   Risco operacional	   Controle/Evidência

Backend              Processo/serviço     CPU, memória,              Queda ou lentidão     Health check e monitoramento
                                          sockets/rede e logs        do serviço

Banco de Dados       Processo + arquivos  Memória, filesystem e I/O  Disco cheio           Backup e Limite de recursos

Frontend             Processo/            CPU, memória,              Lentidão no acesso    Monitoramento de acessos
                     serviço ou arquivos  rede/sockets e filesystem  
                      

Storage de Arquivos  Arquivos/diretórios  Filesystem, permissões     Invasão e             Controle de permissões e 
                                          e armazenamento            perda de dados        backup

git## Mapeamento para Sistemas Operacionais
https://github.com/ryandimasilva-RDCS/fatec-iso001-2026-2-squad-sixnine/pull/1