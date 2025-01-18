# 📚 Agent

## **📌 Definição do Agente de Investimentos Conservador**

Este agente é uma **rede neural inteligente** que opera no **mercado de futuros BTC/USDT** usando técnicas avançadas de **aprendizado de máquina**. Ele aprende a investir de forma **segura e eficiente**, ajustando sua estratégia de acordo com diferentes condições de mercado.

Para estruturar o agente, utilizamos o modelo **PEAS**, que nos ajuda a entender **como ele funciona e quais são seus componentes principais**.

---

# **🧠 PEAS: Estruturando o Agente**

## **1️⃣ Performance (Medida de Desempenho)**  
A **performance** define como medimos o sucesso do agente. Aqui, buscamos um **equilíbrio entre lucratividade e segurança**.

### 🎯 **Objetivos de Performance**
- **Ganhar dinheiro de forma consistente** 📈 → O agente deve manter **lucros positivos** ao longo do tempo.
- **Minimizar perdas** 🚨 → Ele precisa evitar quedas bruscas no portfólio.
- **Ser estável e confiável** ⚖️ → Deve operar com baixa volatilidade e evitar grandes riscos.

### 🔢 **Métricas de Avaliação**
Essas são as **ferramentas matemáticas** que usamos para medir o desempenho do agente:

| **Métrica**           | **O que mede?** | **Como avaliar?** |
|-----------------------|----------------|------------------|
| **Retorno Total (%)** | O lucro final obtido. | Quanto maior, melhor. |
| **Sharpe Ratio** | Relação entre retorno e risco. | Deve ser maior que 1.5 para uma estratégia conservadora. |
| **Sortino Ratio** | Como o agente lida com riscos negativos. | Deve ser superior a 1 para evitar grandes quedas. |
| **Máximo Drawdown (%)** | Maior perda sofrida em um período. | Deve ser **menor que 20%** para evitar perdas grandes. |
| **Taxa de Acerto (%)** | Percentual de operações lucrativas. | Acima de 50% é o ideal. |
| **Profit Factor** | Lucro bruto dividido pelo prejuízo bruto. | Deve ser superior a 1.5 para indicar consistência. |

### 🏆 **Sistema de Premiação do Modelo**
O agente será avaliado com base em seu desempenho. Se ele tiver **bons resultados**, ganha **medalhas**:

- **🥇 Medalha de Ouro** → Alto lucro, drawdown baixo, excelente Sharpe Ratio.
- **🥈 Medalha de Prata** → Lucros consistentes, mas com drawdown um pouco maior.
- **🥉 Medalha de Bronze** → Estratégia conservadora, mas pode melhorar.

---

## **2️⃣ Environment (Ambiente)**
O **ambiente** é onde o agente opera. Ele precisa entender o que acontece no **mercado financeiro** para tomar boas decisões.

### 🌍 **O que o Agente Precisa Considerar?**
1. **Mercado de Futuros BTC/USDT** 🔄  
   - O agente negocia **contratos futuros** (ativos que variam com o preço do Bitcoin).
   - Ele pode **comprar (long)** ou **vender (short)** para lucrar tanto na alta quanto na baixa.

2. **Dados de Mercado** 📊  
   - **Preço do Bitcoin** → Monitorado em tempo real.
   - **Volume de negociação** → Importante para entender tendências.
   - **Volatilidade** → Mede a intensidade das variações de preço.

3. **Condições de Mercado** 🎮  
O agente precisa aprender a lidar com diferentes cenários, como:
   - **Bear Market** 🐻 → Evitar perdas em mercados de queda.
   - **Mercado Lateral** 🔄 → Identificar momentos certos para entrar e sair.
   - **Pump & Dump** 🚀 → Não cair em armadilhas de manipulação.
   - **Notícias Impactantes** 📰 → Ajustar estratégia quando houver eventos inesperados.
   - **Flash Crash** ⚡ → Reagir rapidamente a quedas bruscas.

4. **Fatores Externos** 🏦  
   - **Política monetária** e **taxas de juros** podem afetar os preços dos ativos.
   - **Sentimento do mercado** → Se há medo ou otimismo, isso impacta as decisões.

---

## **3️⃣ Actuators (Atuadores)**
Os **atuadores** são as **ações** que o agente pode tomar no mercado. Ele deve ser capaz de **operar automaticamente** e ajustar sua estratégia.

### 🔧 **O que o Agente pode Fazer?**
1. **📤 Enviar Ordens de Compra/Venda**  
   - Ele pode abrir e fechar posições automaticamente através da **API da corretora Nexo**.

2. **🔄 Ajustar Stop-Loss e Take-Profit**  
   - O agente define pontos automáticos para **fechar uma operação com lucro (take-profit)** ou **limitar perdas (stop-loss)**.

3. **⚠️ Mecanismo de Segurança (Circuit Breaker)**  
   - Se o agente perder várias operações seguidas, ele **pausa automaticamente** para reavaliar a estratégia.

4. **📊 Rebalanceamento da Posição**  
   - Ele pode **aumentar ou reduzir** a exposição ao mercado conforme necessário.

---

## **4️⃣ Sensors (Sensores)**
Os **sensores** são as fontes de informação que o agente utiliza para tomar decisões. Ele precisa "enxergar" o mercado de forma inteligente.

### 📡 **Quais dados o agente coleta?**
1. **Dados de Preço e Volume** 🏦  
   - Cotação do BTC/USDT em tempo real.
   - Volume de negociação nos últimos minutos/horas.

2. **Indicadores Técnicos** 📈  
   - **Médias Móveis (SMA/EMA)** → Para identificar tendências.
   - **Índice de Força Relativa (RSI)** → Mede se um ativo está sobrecomprado ou sobrevendido.
   - **Bandas de Bollinger** → Indica momentos de alta volatilidade.

3. **Análise Fundamentalista** 🏛  
   - Acompanha **notícias e relatórios** que possam influenciar o mercado.
   - Considera **taxas de juros** e **política econômica global**.

4. **Sentimento do Mercado** 📰  
   - Analisa **notícias** e **posts em redes sociais** para identificar o humor do mercado.
   - Se muitas pessoas estão otimistas, pode ser um sinal de alta. Se estão pessimistas, pode indicar queda.

---

## **🚀 Como o Agente Aprende?**
O agente não apenas **toma decisões**, mas também **aprende e melhora** ao longo do tempo.

### 🎓 **Treinamento do Agente**
1. **📊 Coleta de Dados** → O agente analisa preços, volume e outros fatores.  
2. **🔍 Pré-processamento** → Filtra dados irrelevantes e normaliza as informações.  
3. **🤖 Aprendizado Supervisionado** → Treina com dados passados para reconhecer padrões.  
4. **🏆 Aprendizado por Reforço (PPO)** → Simula operações para testar diferentes estratégias.  
5. **🔄 Backtesting** → Avalia como o modelo se sairia em cenários reais.  
6. **📈 Ajustes Contínuos** → O agente melhora ao longo do tempo, adaptando-se às mudanças do mercado.  

A **rede neural** do agente é composta por **três módulos principais**:

### 🧠 Arquitetura da Rede Neural
1. **Módulo de Entrada**: Processa os dados do mercado, incluindo preços, volume e volatilidade.
2. **Módulo de Processamento**: Usa **Transformers** para detectar padrões em séries temporais e redes neurais profundas (**DNN**) para refinar a análise dos dados.
3. **Módulo de Decisão**: Implementa **Aprendizado por Reforço Profundo (PPO - Proximal Policy Optimization)** para ajustar automaticamente a estratégia de trading.

### 🔄 Fluxo de Treinamento
1. **Coleta de dados** 📊: Obtém preços do BTC, volume de negociação e outras informações do mercado.
2. **Pré-processamento** 🔍: Filtra dados e remove informações irrelevantes.
3. **Treinamento supervisionado** 🎓: Aprende padrões de comportamento a partir de dados passados.
4. **Treinamento por Reforço (PPO)** 🏆: Testa diferentes estratégias e aprende quais funcionam melhor.
5. **Backtesting** 🔄: Simula operações para ver como o modelo se sairia em diferentes cenários.
6. **Ajustes contínuos** 📈: O agente melhora ao longo do tempo, adaptando-se ao mercado.

### 📊 Diagrama Detalhado da Rede Neural
```mermaid
flowchart TD
    subgraph Inputs de Mercado
        M1(Preços & Volume em Tempo Real)
        M2(Indicadores Técnicos / Volatilidade)
        M3(Notícias & Sentimento)
    end

    subgraph Rede Neural + RL
        R1(Transformers / LSTM / CNN)
        R2(Camadas Densas - DNN)
        R3(Política PPO - Aprendizado por Reforço)
    end

    subgraph Decisão & Ação
        D1(Calcula Sinal: Comprar, Vender, Manter)
        D2(Ajusta Stop Loss/Take Profit)
    end

    subgraph Circuit Breaker
        CB1(Monitor de Perdas Seguidas / Drawdown)
        CB2(Ativa Bloqueio se Limite Atingido?)
        CB3(Pausa e Reavaliação)
    end

    subgraph Execução
        E1(Envio de Ordem - API Nexo)
        E2(Monitoramento Posição)
        E3(Retorno: Lucro/Perda)
    end

    subgraph Feedback
        F1(Recompensa/Penalidade)
        F2(Atualização da Política PPO)
    end

    M1 --> R1
    M2 --> R1
    M3 --> R1

    R1 --> R2
    R2 --> R3
    R3 --> D1
    R3 --> D2

    D1 --> CB1
    CB1 --> CB2
    CB2 -->|Se ativado| CB3
    CB3 -->|Pausa Operações| D1

    D1 --> E1
    D2 --> E1
    E1 --> E2
    E2 --> E3
    E3 --> F1
    F1 --> F2
    F2 --> R3

```

```mermaid
graph TD;
    A[Entrada: Dados do Mercado] -->|Preços, Volume, Volatilidade| B[Pré-processamento]
    B -->|Normalização de Dados| C[Transformers para Séries Temporais]
    C -->|Padrões Identificados| D[Camadas Neurais Densas DNN]
    D -->|Decisão Inicial| E[Política de Ação PPO]
    E -->|Compra/Venda/Manutenção| F[Execução de Ordem]
    E -->|Ajuste Automático de Stop Loss| G[Ajuste de Risco]
    F -->|Feedback para Aprendizado| H[Recompensa/Penalização]
    H -->|Melhoria Contínua| I[Aprendizado por Reforço]
```

---

# 📈 Training Scenarios for Agente Nexo

## 🏆 Objetivo
Este documento define diferentes **cenários de treinamento** para o agente Nexo, permitindo que ele aprenda a tomar **decisões de investimento** da melhor forma possível em **diferentes condições de mercado**.

O treinamento será dividido em **jogos/simulações**, onde o agente enfrentará desafios e aprenderá **estratégias vencedoras**.

---

## 🎮 Jogos e Cenários de Treinamento

### **1️⃣ Jogo: Mercado de Baixa Extrema (Bear Market)**
🔹 **Objetivo:** Ensinar o agente a **evitar perdas** e identificar pontos de entrada seguros.
🔹 **Cenário:**
   - O mercado cai 10% em um curto período.
   - O agente precisa decidir se **mantém a posição, vende ou espera**.
   - Se ele vender muito cedo, pode perder um possível repique.
   - Se ele segurar muito tempo, pode sofrer grandes perdas.
🔹 **Recompensa:**
   - Se evitar perdas acima de 5% e encontrar um **ponto de entrada lucrativo**, recebe uma **recompensa alta**.
   - Se segurar demais e não conseguir recuperar, recebe **penalização**.

### **2️⃣ Jogo: Mercado Lateral (Consolidação)**
🔹 **Objetivo:** Ensinar o agente a operar em **mercados sem tendência**.
🔹 **Cenário:**
   - O preço oscila entre 40.000 e 42.000 USDT.
   - O agente deve aprender a **comprar na parte inferior e vender na parte superior**.
   - Se ele operar fora dessas faixas, pode sofrer **prejuízos desnecessários**.
🔹 **Recompensa:**
   - Se fizer **entradas e saídas precisas dentro da faixa**, recebe **recompensa alta**.
   - Se comprar ou vender nos momentos errados, recebe **penalização**.

### **3️⃣ Jogo: Pump & Dump (Volatilidade Extrema)**
🔹 **Objetivo:** Ensinar o agente a **evitar armadilhas e capturar movimentos rápidos**.
🔹 **Cenário:**
   - O mercado sobe rapidamente 15% e depois cai 20%.
   - O agente precisa decidir **se entra na alta ou espera uma correção**.
🔹 **Recompensa:**
   - Se identificar corretamente um **ponto de entrada seguro**, recebe **recompensa**.
   - Se entrar muito tarde e sofrer perdas com a correção, recebe **penalização**.

### **4️⃣ Jogo: Notícias Impactantes**
🔹 **Objetivo:** Ensinar o agente a **adaptar-se a eventos inesperados**.
🔹 **Cenário:**
   - Uma **notícia impactante** surge, alterando o sentimento do mercado.
   - O agente deve identificar se a notícia **gera uma nova tendência ou apenas ruído**.
🔹 **Recompensa:**
   - Se ajustar sua estratégia corretamente de acordo com a **notícia**, recebe **recompensa alta**.
   - Se entrar cedo demais ou ignorar o impacto real, recebe **penalização**.

### **5️⃣ Jogo: Flash Crash (Queda Rápida e Recuperação)**
🔹 **Objetivo:** Ensinar o agente a **reagir rapidamente e identificar oportunidades**.
🔹 **Cenário:**
   - O BTC despenca 10% em minutos, mas recupera 8% logo depois.
   - O agente precisa aprender a **não vender no pânico** e procurar oportunidades de compra.
🔹 **Recompensa:**
   - Se conseguir **comprar no momento certo**, recebe **recompensa alta**.
   - Se vender no fundo por medo, recebe **penalização**.

---

┌─────────────────────────────────────────────────────────────────────────┐
│        SISTEMA DE MEDALHAS BASEADO EM LUCRO E MÉTRICAS DE PERFORMANCE  │
└─────────────────────────────────────────────────────────────────────────┘

A ideia é que as **medalhas** sejam concedidas aos indivíduos (modelos) que conseguem se **manter lucrativos** ao longo dos cenários de teste, mas também respeitando métricas adicionais de **risco** e **consistência**. Abaixo, apresento um esquema mais detalhado para integrar **lucro**, **drawdown**, **taxa de acerto** e outras estatísticas.

## 1. Pontuação Geral (Score)

Para que cada indivíduo seja avaliado de forma **objetiva**, podemos criar um **Score Global** que agregue vários indicadores. Por exemplo:

1. **Lucro Acumulado** (Profit Factor)
   - Mede o total de lucro (ou prejuízo) ao final dos cenários de teste.
   - Ex.: Se o modelo terminou com +15% sobre o capital inicial, recebe uma pontuação proporcional.

2. **Stability Score** (Drawdown e Volatilidade)
   - Penaliza modelos que geram picos de perda (max drawdown) ou têm comportamento muito volátil.
   - Ex.: Se o max drawdown for menor que 15%, recebe um bônus na pontuação final.

3. **Consistência de Retornos** (Sharpe ou Sortino Ratio)
   - Avalia se o modelo gera um **retorno estável**, ajustado ao risco.
   - Ex.: Quanto maior o Sharpe/Sortino Ratio, maior a pontuação.

4. **Taxa de Acerto** / **Taxa de Operações Lucrativas**
   - Mede quantos trades terminaram no lucro em relação ao total.
   - Mesmo com bom lucro, se a taxa de acerto for muito baixa, a pontuação final cai.

5. **Performance em Múltiplos Cenários** (Bear, Lateral, Pump & Dump, etc.)
   - Verifica se o indivíduo **não “bamba”** em algum cenário.  
   - Modelos que conseguem manter a **lucratividade** em todos os cenários recebem pontuação adicional.

> **Fórmula genérica**:  
> \[
> \text{Score Global} = w_1 \times \text{Lucro} \;+\; w_2 \times \text{Estabilidade} \;+\; w_3 \times \text{Consistência} \;+\; w_4 \times \text{Taxa de Acerto} \;+\; w_5 \times \text{MultiCenários}
> \]  
> Onde \(w_i\) são pesos que você define para cada indicador, priorizando a “filosofia” do projeto (ex.: conservador → peso maior em estabilidade e drawdown).

---

## 2. Regras Básicas para Ganhar Medalha

- **Regra Geral**: O modelo **deve** terminar os cenários **lucrativo** (lucro >= 0) para ser elegível a qualquer medalha.  
- **Restrições de Segurança**:  
  - Se o drawdown excede 30%, o modelo fica **desclassificado** de premiações altas (apenas recebe “bronze” ou nenhuma).  
  - Se a taxa de acerto for muito baixa (ex.: < 40%), também não passa de “bronze” ou “sem medalha”.  

**Pontuação Final** → **Medalha**:
- **Ouro**: Score Global >= 80 + lucros positivos em todos os cenários.  
- **Prata**: Score Global entre 65 e 79 + não teve drawdown > 25%.  
- **Bronze**: Score Global entre 50 e 64 + não teve drawdown > 30%.  
- **Sem Medalha**: Abaixo de 50 pontos ou lucro negativo.

*(Obs.: Os números acima são exemplos, adapte conforme sua análise e amplitude de valores.)*

---

## 3. Possível Exemplo de Cálculo

**Exemplo** de como pontuar um modelo ao final dos “jogos”:

| Indicador                | Valor Exemplo   | Conversão em Pontos   |
|--------------------------|-----------------|------------------------|
| Lucro Total             | +12%            | +30 pontos            |
| Drawdown Máximo         | 18%             | +20 pontos (pequena penalidade) |
| Sharpe Ratio            | 1.8             | +20 pontos            |
| Taxa de Acerto Geral    | 58%             | +10 pontos            |
| Cenários Sem Perdas     | 4 de 5          | +10 pontos            |

> **Score Global** = 30 + 20 + 20 + 10 + 10 = **90** → **Medalha de Ouro**  
> (Pois foi lucrativo e pontuou acima de 80.)

Outro modelo, com 8% de lucro, 25% drawdown e Sharpe 1.2, pode ter:
- Lucro +25 pontos  
- Drawdown 25% +10 pontos  
- Sharpe 1.2 +15 pontos  
- Acerto 50% +5 pontos  
- Cenários sem perdas 3/5 +5 pontos  
**Score = 25+10+15+5+5= 60** → **Medalha de Bronze** (exemplo de corte).

---

## 4. Gamificação com Medalhas Especiais

Além das medalhas principais (Ouro/Prata/Bronze), você pode ter **conquistas extras** relacionadas especificamente ao **lucro** em cada cenário, por exemplo:

1. **“Investidor de Aço”**  
   - Quando o modelo mantém **lucro positivo** mesmo em Bear Market severo, sem drawdown acima de 20%.

2. **“Sniper de Volatilidade”**  
   - Quando captura lucros acima de x% em cenários de **Pump & Dump**, entrando e saindo “no ponto”.

3. **“Blindado contra Flash Crash”**  
   - Zero posições liquidadas durante um flash crash, mantendo-se ainda no verde (lucro >= 0).

Essas medalhas especiais **incentivam** a excelência em aspectos específicos do mercado.

---

## 5. Resumo e Conclusão

Com esse **sistema de medalhas** orientado a **lucratividade e métricas de risco**, você:

1. **Garante** que apenas indivíduos efetivamente lucrativos recebam medalhas.  
2. **Premia** a consistência e estabilidade, alinhada ao foco conservador.  
3. **Adota** um Score Global que equilibra múltiplos indicadores (lucro, drawdown, Sharpe, taxa de acerto).  
4. **Gamifica** o aprendizado, criando um ranking onde cada modelo (indivíduo) busca pontuar o máximo possível nos cenários de simulação.

---

## 🧠 Como o Agente Aprende a Melhor Estratégia?

1. **Simulações Massivas**
   - O agente é testado **milhares de vezes** em cada cenário.
   - Cada simulação ajusta os pesos da rede neural para **evitar erros futuros**.

2. **Recompensa por Decisões Certas**
   - O modelo de aprendizado por reforço **recompensa boas decisões** e **penaliza erros**.
   - Cada jogo reforça **padrões de comportamento eficiente**.

3. **Ajustes Contínuos**
   - Após o treinamento inicial, o agente continua aprendendo **com o mercado ao vivo**.
   - Se um novo padrão de mercado surgir, o agente pode **se adaptar automaticamente**.

---

# **🎯 Conclusão**
Agora, o agente está bem definido! Ele:
✅ **Analisa o mercado** utilizando dados históricos e em tempo real.  
✅ **Toma decisões** baseadas em aprendizado de máquina.  
✅ **Opera automaticamente** comprando e vendendo ativos.  
✅ **Aprende e se adapta** para melhorar sua performance ao longo do tempo.  

Esse modelo **equilibra segurança e lucratividade**, garantindo um investimento conservador e eficiente.  
