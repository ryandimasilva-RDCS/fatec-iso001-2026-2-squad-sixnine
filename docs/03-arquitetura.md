# Arquitetura do Projeto

## Baseline do Sistema Operacional
### 1. Qual é a versão do kernel?
Linux codespaces-19280f 6.8.0-1052-azure #58~22.04.1-Ubuntu SMP Thu Mar 26 05:02:21 UTC 2026 x86_64 x86_64 x86_64 GNU/Linux

### 2. Qual distribuição aparece?
Identificamos a versão "Ubuntu 24.04.4 LTS"
### 3. Quanto de memória RAM está disponível?
De acordo com o baseline coletado, esse sistema apresente 5.4Gi disponiveis de memória RAM
### 4. Quanto de filesystem está disponível?
Ele apresenta 20GB disponiveis
### 5. Quais processos chamaram atenção no baseline?
2236    2212 codespa+ Sl   10.2  6.4 MainThread;
   2694    2267 codespa+ Sl    0.3  3.7 MainThread
### 6. Para o cenário da squad, qual recurso tende a ser mais crítico?
De acordo com nossas análises, a memória tende a ser o recurso mais critico pois nooso projeto exige que alguns processos sejam execultados simultaneamente, como o banco de dados. o seu consumo elevado pode causar lentidão ou até interrupção desses processos. Dito isso, é necessario monitorar o uso da memória e estabelecer alertas para o uso execivo.
## Mapeamento para Sistemas Operacionais
