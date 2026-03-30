# Teste de Performance - BlazeDemo

## Objetivo
Avaliar o comportamento da aplicação sob diferentes padrões de carga utilizando Apache JMeter.

## Cenários executados

### Teste de Carga (Load Test)
Simulação de aumento gradual de usuários.

- ~250 usuários
- Ramp-up gradual (60 segundos)
- Duração: ~60 segundos

### Teste de Pico (Spike Test)
Simulação de aumento abrupto de usuários.

- ~300 usuários
- Ramp-up rápido (5 segundos)
- Duração: ~30 segundos

## Fluxo testado

1. GET Home
2. POST Search Flights
3. POST Select Flight
4. POST Confirm Flight

O fluxo foi agrupado em um Transaction Controller para medir o tempo total da transação.

## Estratégias adotadas

- Uso de Transaction Controller com "Generate parent sample"
- Estratégia "Stop Thread" para evitar propagação de erros
- Utilização de dados fixos para seleção de voo (sem correlação dinâmica)

## Resultados

### Teste de Carga
- Tempo de resposta estável durante a execução
- Baixa taxa de erro
- Throughput consistente

### Teste de Pico
- Aumento no tempo de resposta
- Maior variabilidade nos tempos
- Indícios de degradação sob carga abrupta

## Conclusão

O sistema apresentou comportamento estável sob carga gradual.

No cenário de pico, foi possível observar degradação no tempo de resposta, indicando limitações sob aumento repentino de usuários.

## Execução

Para executar o teste:

jmeter -n -t agi-performance-test.jmx -l resultado.jtl
