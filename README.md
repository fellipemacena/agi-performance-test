# agi-performance-test

## Objetivo
Executar testes de performance no fluxo de compra de passagem aérea do sistema BlazeDemo, conforme o enunciado do teste técnico.

## Ferramenta utilizada
- Apache JMeter

## Cenário testado
Fluxo de compra com sucesso:
- Get Home
- POST Search Flights
- POST Select Flight
- POST Confirm Flight

## Estrutura do projeto
- `jmeter/blazedemo-load-test.jmx`: teste de carga
- `jmeter/blazedemo-spike-test.jmx`: teste de pico
- `evidences/`: prints dos resultados

## Como executar
1. Instalar o Apache JMeter
2. Abrir o arquivo `.jmx` desejado no JMeter
3. Executar o teste pela interface ou via CLI

### Execução via CLI
```bash
jmeter.bat -n -t "jmeter/blazedemo-load-test.jmx" -l "load-result.jtl" -e -o "load-report"
jmeter.bat -n -t "jmeter/blazedemo-spike-test.jmx" -l "spike-result.jtl" -e -o "spike-report"
