# Laboratório: Teste de Mutação com a "Calculadora Mutante"

Bem-vindo ao trabalho prático de Teste de Mutação. O objetivo deste projeto é usar a ferramenta StrykerJS para avaliar e fortalecer uma suíte de testes que, à primeira vista, parece boa.

## Contexto

Este repositório contém uma biblioteca de cálculos simples. A suíte de testes inicial em `__tests__/` foi projetada para ter uma alta **cobertura de código**, mas esconde fraquezas que só o **teste de mutação** pode revelar.

Sua missão é atuar como um engenheiro de qualidade para encontrar essas fraquezas e escrever testes mais robustos para corrigi-las.

## Tarefas

1.  **Prepare o ambiente:** Clone o repositório e rode `npm install`.
2.  **Análise Inicial:**
    - Rode `npm test` para ver os testes passando.
    - Rode `npm run coverage` e anote o percentual de cobertura.
3.  **Análise de Mutação:**
    - Configure o StrykerJS (`npx stryker init`).
    - Execute a análise com `npx stryker run` (ou `npm run mutate` após configurar o script).
    - Abra o relatório HTML e analise os **mutantes que sobreviveram**.
4.  **Aprimore os Testes:**
    - Para cada mutante sobrevivente, entenda por que ele não foi "morto".
    - Adicione novos testes em `__tests__/operacoes.test.js` focados em asserções mais específicas para matar esses mutantes.
5.  **Validação Final:**
    - Rode o Stryker novamente e verifique se sua pontuação de mutação aumentou, idealmente para mais de 95%.

Siga as instruções do documento do trabalho para a entrega final. Boa sorte!

## Entrega

Trabalho de Gabriel Cardoso dos Santos (matrícula 830691).

| O que | Onde |
|---|---|
| Testes (os 50 originais + 27 novos) | [`test/operacoes.test.js`](test/operacoes.test.js) |
| Configuração do Stryker | [`stryker.config.json`](stryker.config.json) |
| Relatório (PDF) | [`relatorio/Relatorio_Teste_Mutacao_Gabriel_Cardoso.pdf`](relatorio/Relatorio_Teste_Mutacao_Gabriel_Cardoso.pdf) |

Os testes ficam na pasta `test/`, que é a pasta usada neste repositório (e não `__tests__/`). Os 50 testes originais não foram alterados; os novos estão no bloco "Testes que matam os mutantes sobreviventes".

### Como rodar

```bash
npm install
npm test
npm run coverage
npm run mutate
```

O relatório HTML do Stryker é gerado em `reports/mutation/mutation.html`.

### Resultados

| | Cobertura de linhas | Mutation score |
|---|---|---|
| Suíte original (50 testes) | 98,64% | 73,71% |
| Com os 27 testes novos | 100% | 97,65% |
| Final | 100% | 100% |

Os 5 mutantes que sobram com os testes novos são equivalentes (não mudam o comportamento) e estão marcados com `// Stryker disable next-line` em `src/operacoes.js`, com o motivo no próprio comentário. A explicação completa está na seção 5 do relatório.

O `npx stryker init` desta versão (10.0) gera o arquivo `stryker.config.json`, e não `stryker.conf.json` como diz o enunciado.
