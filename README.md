# 📊 Simulador de Investimentos em Fundos Imobiliários (FIIs)

Projeto desenvolvido como Desafio de Projeto do bootcamp **"Reclame AQUI - Dados e IA na Prática"**, oferecido pela [Digital Innovation One (DIO)](https://www.dio.me/).

## 🎯 Objetivo

Fundos de Investimento Imobiliário (FIIs) são uma das formas mais populares de investimento em renda variável no Brasil, mas quem está começando costuma ter as mesmas dúvidas: *quanto investir por mês? por quanto tempo? qual retorno esperar?*

Este projeto é uma planilha em Excel que responde a essas perguntas automaticamente, simulando:

- O **patrimônio acumulado** ao final de um investimento mensal recorrente;
- Os **dividendos mensais** estimados a partir desse patrimônio;
- Diferentes **cenários de prazo** (2, 3, 4, 5, 10, 20 e 30 anos);
- Uma **sugestão de alocação da carteira** entre tipos de FII, de acordo com o perfil de risco do investidor (Conservador, Moderado ou Agressivo).

## ⚙️ Como funciona

A planilha é dividida em três blocos principais, todos na aba `SIMULADOR`:

### 1. Configurações gerais
Parâmetros de referência para o planejamento financeiro:
- Salário do investidor;
- Rendimento médio da carteira (% ao mês);
- Sugestão automática de quanto investir por mês (30% do salário).

### 2. Simulação de investimento mensal
A partir de três entradas — **valor do aporte mensal**, **prazo em anos** e **taxa de rendimento mensal** — a planilha calcula:
- O **patrimônio acumulado**, usando a função financeira `VF` (Valor Futuro), que projeta o total investido somado aos juros compostos ao longo do tempo;
- Os **dividendos mensais esperados**, aplicando o percentual de rendimento da carteira sobre o patrimônio acumulado.

Uma tabela de **cenários** replica esse mesmo cálculo para diferentes prazos (2 a 30 anos), permitindo comparar rapidamente o efeito do tempo sobre o patrimônio — o famoso efeito dos juros compostos.

### 3. Alocação por perfil de investidor
O usuário escolhe seu perfil em uma lista suspensa (`Conservador`, `Moderado` ou `Agressivo`). A planilha então:
- Busca, em uma tabela auxiliar (`DADOS DO PERFIL`), o percentual sugerido de alocação em cada tipo de FII (Papel, Tijolo, Híbridos e FOF's) para o perfil escolhido, usando `PROCV` sobre uma chave composta (`Perfil - Tipo de FII`);
- Calcula automaticamente o valor em reais a ser destinado a cada tipo de fundo, com base no aporte mensal definido.

## 🧮 Conceitos e funções aplicadas

- **Função financeira `VF` (Valor Futuro)** — cálculo de juros compostos sobre aportes mensais;
- **`PROCV` com chave composta** — busca de valores cruzando duas dimensões (perfil + tipo de fundo) em uma tabela auxiliar normalizada;
- **Intervalos nomeados** (*named ranges*) — fórmulas legíveis como `=VF(taxa_mensal, qtd_anos*12, aporte*-1)` em vez de referências soltas de célula;
- **Validação de dados (lista suspensa)** — seleção controlada do perfil de investidor;
- **Tabela auxiliar normalizada** — os percentuais de alocação por perfil ficam em uma aba separada (`DADOS DO PERFIL`), facilitando manutenção e expansão.

## 🖼️ Capturas de tela

As imagens ilustram a planilha em uso (ver pasta [`/images`](./images)):
images/alocacao-perfil.png

## 🚀 Como usar

1. Baixe o arquivo `Simulador_Investimento_FIIs.xlsx` deste repositório;
2. Abra no Excel;
3. Preencha os campos em editáveis:
   - `Quanto investir por mês?`
   - `Por quantos anos?`
   - `Taxa de rendimento mensal?`
4. Escolha seu **perfil de investidor** na lista suspensa;
5. Os resultados — patrimônio acumulado, dividendos mensais e sugestão de alocação por tipo de FII — são atualizados automaticamente.

## 🛠️ Tecnologias utilizadas

- Microsoft Excel
- Funções financeiras (`VF`)
- `PROCV`
- Intervalos nomeados
- Validação de dados

## 📚 Aprendizados

Este desafio consolidou conhecimentos sobre:
- Aplicação prática de fórmulas financeiras para simulação de investimentos;
- Organização de dados em tabelas auxiliares normalizadas, facilitando manutenção e escalabilidade da planilha;
- Documentação técnica de um projeto e uso do GitHub para versionamento e compartilhamento.

## 👤 Autor

Desenvolvido por **Bruno**, como parte da trilha **Santander/Reclame AQUI - Dados e IA na Prática** (DIO).

---

Projeto feito com fins educacionais. Os valores e taxas utilizados são exemplos ilustrativos e não constituem recomendação de investimento.
