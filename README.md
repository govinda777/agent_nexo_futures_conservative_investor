# 🏦 Agente Nexo - Investimento Conservador

Este é um programa automático que ajuda a investir em Bitcoin (BTC) na plataforma **Nexo**. Ele segue estratégias **seguras** e **conservadoras**, ajustando os limites de perda (**stop loss**) e ganho (**take profit**) a cada minuto. Além disso, ele envia **notificações pelo Telegram** para que você acompanhe tudo em tempo real. 📩

---

## Passos

---

# **Estrutura Avançada para Implementação do Projeto**

## **Capítulo 1: Visão Geral do Projeto**

### **1.1. O Desafio da Previsão de Preços no Mercado Financeiro**
A volatilidade do mercado financeiro é um dos maiores desafios para investidores, especialmente para aqueles que buscam estratégias conservadoras. A imprevisibilidade de eventos macroeconômicos, oscilações nas taxas de juros e mudanças na política monetária tornam essencial o uso de modelos avançados de previsão.

Modelos tradicionais, como médias móveis e ARIMA, apresentam limitações significativas ao tentar capturar padrões complexos de séries temporais. Essas abordagens muitas vezes falham em antecipar mudanças abruptas e não conseguem lidar adequadamente com a dependência de longo prazo presente nos dados financeiros.

**Exemplo:** Um investidor que utiliza médias móveis pode não captar rapidamente um rompimento de resistência ou suporte devido ao atraso inerente dessa abordagem. Com um modelo baseado em redes neurais, padrões emergentes podem ser detectados mais cedo, permitindo decisões mais ágeis.

**Diagrama:**
```mermaid
graph TD;
    A[Dados Históricos] -->|Entrada| B[Modelo ARIMA];
    B -->|Saída| C[Previsão Simples];
    A -->|Ruído do Mercado| D[Ajuste Manual];
    D -->|Saída| E[Falha na Previsão];
```

### **1.2. Revolução das Redes Neurais LSTM e Outras Arquiteturas para Previsão de Preços**
As Redes Neurais Recorrentes (RNNs) revolucionaram a modelagem de séries temporais ao permitir a retenção de informações passadas. No entanto, as RNNs tradicionais apresentam o problema do desvanecimento do gradiente, o que limita sua capacidade de capturar dependências de longo prazo.

As redes **Long Short-Term Memory (LSTM)** foram projetadas para resolver esse problema. Elas utilizam células de memória que permitem a manutenção de informações relevantes por períodos prolongados, sendo altamente eficazes na previsão de preços no mercado financeiro.

Além das LSTM, outras arquiteturas também são aplicadas:
- **CNNs (Redes Neurais Convolucionais):** Muito utilizadas para reconhecimento de padrões gráficos nos preços.
- **Transformers:** Modelos modernos que podem lidar com dependências de longo prazo de forma eficiente.
- **Redes Recorrentes Simples:** Menos eficazes devido à perda de informações ao longo do tempo.

**Exemplo:** Um modelo LSTM pode ser treinado com dados históricos de um ativo, aprendendo padrões de alta e baixa para fornecer previsões mais precisas.

**Diagrama Comparativo:**
```mermaid
graph TD;
    A[Entrada (Preços)] -->|Processamento| B[RNN Simples];
    B -->|Saída| C[Previsão Ruim];
    A -->|Processamento| D[LSTM];
    D -->|Saída| E[Previsão Melhor];
```

**Diagrama de Funcionamento do LSTM:**
```mermaid
graph TD;
    A[Entrada de Dados] -->|Passo Temporal| B[Célula LSTM];
    B -->|Processamento| C[Memória de Longo Prazo];
    C -->|Saída| D[Previsão];
    B -->|Feedback| B;
```

### 📊 **Diagrama Detalhado da Rede Neural**
```mermaid
graph LR;
    subgraph Entrada
        A1(Preço Atual)
        A2(Volume de Negociação)
        A3(Volatilidade)
        A4(Média Móvel)
        A5(Sentimento de Mercado)
    end
    
    subgraph Camada Oculta
        B1(Transformer Layer 1)
        B2(Transformer Layer 2)
        B3(DNN Neurônio 1)
        B4(DNN Neurônio 2)
        B5(DNN Neurônio 3)
    end
    
    subgraph Decisão e Execução
        C1(Política de Ação PPO)
        C2(Ajuste de Stop Loss/Take Profit)
        C3(Execução de Ordem)
    end
    
    A1 -->|Peso| B1
    A2 -->|Peso| B1
    A3 -->|Peso| B2
    A4 -->|Peso| B2
    A5 -->|Peso| B3
    B1 -->|Ativação| B3
    B2 -->|Ativação| B4
    B3 -->|Ativação| C1
    B4 -->|Ativação| C1
    B5 -->|Ativação| C2
    C1 -->|Decisão| C3
    C2 -->|Ajuste de Risco| C3
```

🚀 **Essa arquitetura melhora a capacidade do agente de aprender padrões do mercado e tomar decisões mais assertivas!**

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

##

### **1.2. Revolução das Redes Neurais LSTM e Outras Arquiteturas para Previsão de Preços**

#### **Por que as LSTM são superiores para séries temporais?**

As **Long Short-Term Memory (LSTM)** são um tipo avançado de Redes Neurais Recorrentes (RNNs) que resolvem o problema do **desvanecimento do gradiente**. Elas mantêm informações relevantes ao longo de várias etapas temporais, utilizando **células de memória** e **portas de controle**, tornando-as ideais para prever preços de ativos financeiros.

**Arquitetura das LSTM:**

1. **Camada de Entrada:** Recebe a sequência temporal de entrada, como preços históricos de ativos.
2. **Célula LSTM:** Contém três portas principais:
   - **Porta de Entrada:** Determina quais novas informações serão armazenadas.
   - **Porta de Esquecimento:** Decide quais informações antigas devem ser descartadas.
   - **Porta de Saída:** Define quais informações processadas serão utilizadas na próxima etapa.
3. **Camada de Saída:** Retorna a previsão do próximo valor da série temporal.

Benefícios das LSTM:
- **Captura de dependências de longo prazo** em séries temporais.
- **Resistência ao desvanecimento do gradiente**, garantindo previsões mais estáveis.
- **Capacidade de aprendizado sequencial**, permitindo identificar padrões temporais ocultos.

**Exemplo Prático:** Imagine que queremos prever o preço de uma ação com base nos últimos 30 dias. A rede LSTM analisará os preços passados e, utilizando suas células de memória, identificará tendências, removendo dados irrelevantes e focando nos padrões mais relevantes para gerar uma previsão precisa.

```mermaid
graph TD;
    A[Entrada de Dados] -->|Passo Temporal| B[Célula LSTM];
    B -->|Processamento| C[Memória de Longo Prazo];
    C -->|Saída| D[Previsão];
    B -->|Feedback| B;
```

#### **Exemplos de Redes LSTM**

##### **1. LSTM Simples para Previsão de Preço**
**Explicação:** Essa é uma rede básica composta por duas camadas LSTM empilhadas, seguida por uma camada densa que gera a previsão final. Ideal para previsões de séries temporais simples, como preços de ações.
```mermaid
graph TD;
    A[Preços Históricos] --> B[LSTM Camada 1];
    B --> C[LSTM Camada 2];
    C --> D[Camada Densa];
    D --> E[Saída: Previsão de Preço];
```

##### **2. LSTM com Múltiplas Entradas**
**Explicação:** Aqui, a rede recebe não apenas preços históricos, mas também outros fatores como volume de negociação e sentimento de mercado. Esses dados são combinados para aumentar a precisão da previsão.
```mermaid
graph TD;
    A[Preços] --> B[LSTM];
    X[Volume] --> B;
    Y[Sentimento de Mercado] --> B;
    B --> C[Concatenação de Features];
    C --> D[Camada Densa];
    D --> E[Saída: Previsão];
```

##### **3. Arquitetura Híbrida: CNN + LSTM**
**Explicação:** Essa arquitetura combina CNNs para extrair padrões espaciais dos dados e LSTMs para capturar a dependência temporal. Essa abordagem é útil quando há padrões complexos que exigem análise tanto espacial quanto sequencial.
```mermaid
graph TD;
    A[Preços] --> B[Camada CNN];
    B --> C[Camada MaxPooling];
    C --> D[LSTM Camada 1];
    D --> E[LSTM Camada 2];
    E --> F[Camada Densa];
    F --> G[Saída: Previsão de Preço];
```

##### **4. LSTM com Mecanismo de Atenção**
**Explicação:** O mecanismo de atenção permite que a rede LSTM se concentre mais em partes importantes da sequência de entrada, melhorando a precisão das previsões ao dar mais peso a eventos significativos.
```mermaid
graph TD;
    A[Entrada] --> B[LSTM];
    B --> C[Mecanismo de Atenção];
    C --> D[Concatenação];
    D --> E[Camada Densa];
    E --> F[Saída: Previsão];
```

🚀 **A incorporação das LSTM em estratégias de investimento pode proporcionar uma vantagem competitiva significativa para traders e investidores institucionais!**

---
### 1.3. Objetivos Ambiciosos do Projeto

#### 🧠 **Diagrama do Neurônio do Projeto**
```mermaid
graph TD;
    A[Entradas: Preço, Volume, Notícias, Indicadores] -->|Pré-processamento| B[Normalização de Dados]
    B -->|Sequenciamento Temporal| C[Camada LSTM]
    C -->|Extração de Padrões| D[Camada Densa]
    D -->|Ativação ReLU| E[Neurônios de Decisão]
    E -->|Classificação| F[Saída: Comprar, Vender, Manter]
    E -->|Ajuste Dinâmico| G[Stop Loss/Take Profit Adaptativo]
```

O projeto **Agente Nexo - Investimento Conservador** tem como meta criar um sistema de investimento seguro e eficiente para operar no mercado de futuros BTC/USDT. A ideia principal é permitir que qualquer investidor possa operar de forma automatizada, sem precisar monitorar o mercado o tempo todo.

#### **Principais Objetivos do Projeto:**

1. **Criar um modelo inteligente para prever tendências de preços:**
   - O agente usará um modelo chamado **LSTM**, que aprende com o histórico de preços para prever os próximos movimentos do mercado.
   - **Exemplo:** Se o Bitcoin estiver subindo há vários dias seguidos, o modelo pode sugerir uma venda antecipada antes de uma possível queda.

2. **Automatizar a análise de dados do mercado:**
   - O sistema coletará e analisará os preços de forma contínua, sem precisar de intervenção humana.
   - **Exemplo:** A cada minuto, o agente verifica as informações do mercado e identifica padrões que podem indicar alta ou baixa nos preços.

3. **Ajustar automaticamente as estratégias de compra e venda:**
   - O modelo ajustará **stop loss** (limite de perda) e **take profit** (lucro esperado) conforme o comportamento do mercado.
   - **Exemplo:** Se o preço do Bitcoin começar a cair rapidamente, o agente pode vender antes que a perda seja grande demais.

4. **Reduzir riscos para os investidores:**
   - O sistema evitará operações arriscadas e usará apenas estratégias seguras.
   - **Exemplo:** Se o mercado estiver muito volátil, o agente pode decidir não operar até encontrar uma oportunidade mais estável.

5. **Integrar notícias e sentimento do mercado na análise:**
   - O agente levará em conta notícias e postagens em redes sociais para identificar momentos de otimismo ou pessimismo no mercado.
   - **Exemplo:** Se grandes sites de finanças começarem a relatar más notícias sobre criptomoedas, o agente pode reduzir as compras para evitar perdas.

6. **Executar ordens automaticamente na corretora Nexo:**
   - O agente se conectará à API da corretora para executar operações sem intervenção humana.
   - **Exemplo:** Quando o modelo detectar um sinal de compra forte, ele fará a operação automaticamente na Nexo.

7. **Enviar alertas via Telegram para manter o investidor informado:**
   - O agente notificará o usuário sempre que uma operação importante for realizada.
   - **Exemplo:** O investidor recebe uma mensagem quando o agente compra ou vende Bitcoin, ou quando o mercado muda drasticamente.

8. **Testar estratégias antes de operar no mercado real:**
   - O sistema será testado com dados passados para garantir que a estratégia funciona.
   - **Exemplo:** Se a estratégia for aplicada a dados históricos e mostrar que teria gerado lucro nos últimos meses, ela será validada para uso real.

9. **Melhorar continuamente o desempenho do agente:**
   - O modelo aprenderá com novas informações e se ajustará conforme o mercado evolui.
   - **Exemplo:** Se um novo padrão surgir no mercado, o agente poderá aprender com ele e adaptar suas decisões futuras.

10. **Criar um sistema flexível e escalável:**
    - O agente poderá ser expandido para operar com outros ativos no futuro.
    - **Exemplo:** Se o investidor quiser operar também com Ethereum, o sistema poderá ser ajustado para incluir essa criptomoeda.

---

### **Conclusão**

O **Agente Nexo - Investimento Conservador** busca criar uma ferramenta automatizada e segura para investidores que querem operar no mercado de futuros BTC/USDT sem precisar de monitoramento constante. Através do uso de inteligência artificial, gerenciamento de risco avançado e automação, o agente ajudará investidores a tomar decisões estratégicas e minimizar riscos, tornando o investimento mais seguro e eficiente.

---

## **1.4. Estrutura Completa do Documento** - **Arquitetura do Projeto**

Para dar maior clareza sobre **como** o projeto se integra de ponta a ponta, apresentamos abaixo um **diagrama de arquitetura** que agrupa todas as etapas do **Agente Nexo - Investimento Conservador**: coleta de dados, processamento, treinamento, execução, controle de risco e notificações.

```mermaid
flowchart LR
    subgraph A[Coleta e Pré-Processamento]
        A1(Dados Históricos de Preço - Nexo/Exchanges)
        A2(Volumes, Indicadores)
        A3(Notícias, Sentimento de Mercado)
        A4(Pré-processamento e Limpeza)
    end

    subgraph B[Camada de Modelagem e Treinamento]
        B1(Arquitetura da Rede Neural)
        B2(LSTM / Transformers / DNN)
        B3(Treinamento Supervisionado)
        B4(Aprendizado por Reforço - PPO)
        B5(Salvando Modelos em models/)
    end

    subgraph C[Sistema de Execução e Monitoramento]
        C1(Recebe Sinais de Entrada da Rede Neural)
        C2(Ajuste de Stop Loss/Take Profit)
        C3(Orquestrador de Ordens - API Nexo)
        C4(Registro de Log e Métricas)
        C5(Notificações via Telegram)
    end

    subgraph D[Banco de Dados e Armazenamento]
        D1(Armazenamento de Históricos)
        D2(Logs e Resultados de Treinamento)
        D3(Checkpoints da Rede Neural)
    end

    A1 --> A4
    A2 --> A4
    A3 --> A4
    A4 --> B1
    B1 --> B2
    B2 --> B3
    B3 --> B4
    B4 --> B5

    B5 -->|Modelo Treinado| C1
    C1 -->|Decisão: Compra/Venda| C3
    C1 -->|Configura Stop Loss/Take Profit| C2

    C3 -->|Envia Execução para Nexo| D1
    C2 -->|Atualiza Posições| D1

    C4 --> D2
    C3 -->|Resultado das Ordens| C4
    C4 --> C5
    B4 --> D2
    B5 --> D3
    A4 --> D1
```

### **Explicação do Fluxo**

1. **Coleta e Pré-Processamento (Bloco A)**  
   - Os dados de preços, volumes, indicadores técnicos e até sentimentos de mercado (notícias/tweets) passam por um processo de limpeza e formatação. Em seguida, são armazenados para uso posterior no treinamento.

2. **Camada de Modelagem e Treinamento (Bloco B)**  
   - Aqui temos a **arquitetura de rede neural** (p. ex. LSTM, Transformers, DNN) e as técnicas de **Aprendizado por Reforço** (PPO) para refinar a estratégia de trading.
   - Os modelos treinados são salvos em `models/`, ficando prontos para uso na tomada de decisão.

3. **Sistema de Execução e Monitoramento (Bloco C)**  
   - Recebe **sinais de compra/venda** do modelo treinado e faz os ajustes automáticos de **stop loss** e **take profit**.
   - Conecta-se à **API da Nexo** para abrir, fechar ou atualizar posições de forma automática e segura.
   - Gera logs de cada operação, registra métricas de desempenho e envia alertas via **Telegram**.

4. **Banco de Dados e Armazenamento (Bloco D)**  
   - **Armazena** todo o histórico de preços coletado, as métricas de treinamento (logs) e **checkpoints** dos modelos.
   - Facilita **backtesting** e auditoria do sistema, além de servir de base para o aprimoramento contínuo.

---

### **Onde cada capítulo do Documento se encaixa nessa Arquitetura**

- **Capítulo 1 (Visão Geral):** Contextualiza o desafio do mercado financeiro, a relevância das LSTM/Transformers e define os objetivos de um sistema de investimento conservador.  
- **Capítulo 2 (Fundamentos Teóricos):** Apresenta os diferentes tipos de redes neurais e métodos estatísticos que embasam o bloco B (Modelagem/Aprendizado).  
- **Capítulo 3 (Engenharia de Dados):** Refere-se diretamente ao bloco A, descrevendo as fontes de dados, como limpá-los e tratá-los para alimentação do modelo.  
- **Capítulo 4 (Arquitetura da Rede LSTM):** Desdobra a parte crucial do bloco B, mostrando a criação das camadas LSTM, CNN ou Transformers, bem como as escolhas de hiperparâmetros.  
- **Capítulo 5 (Predição e Validação):** Foca nas etapas de teste rigoroso e backtesting do sistema (ainda dentro do bloco B, mas também registrando no bloco D).  
- **Capítulo 6 (Integração com Trading):** Conecta o bloco B ao bloco C (Execução), detalhando como as previsões viram ordens automáticas, gerando logs e alertas.  
- **Capítulo 7 (Considerações Finais):** Avalia resultados, mostra as conquistas e expande possibilidades para melhorar a arquitetura (ex.: novas features, mais fontes de dados).  
- **Capítulo 8 (Recursos Avançados):** Indica bibliotecas, frameworks e leituras que podem complementar tanto a camada de dados quanto a de modelagem, além de redes de apoio na comunidade.

---

#### **Com esse diagrama e explicação, a "arquitetura do projeto" se torna visível** dentro do item **"1.4. Estrutura Completa do Documento"**, dando sustentação prática a cada capítulo e seção apresentados.

---

## **Capítulo 2: Fundamentos Teóricos Profundos**

### **2.1. Redes Neurais Recorrentes vs. LSTM: Um Combate Técnico**
- **RNN (Redes Neurais Recorrentes Tradicionais):** Capacidade de processar sequências, mas sofre com o problema do desaparecimento do gradiente.
- **LSTM (Long Short-Term Memory):** Introduz mecanismos de memória mais eficientes, permitindo aprendizado de dependências longas.
- **GRU (Gated Recurrent Units):** Variante simplificada da LSTM, menos computacionalmente custosa.

### **2.2. Outras Arquiteturas de Redes Neurais para Previsão de Preços**
- **Redes Neurais Convolucionais (CNNs)**
  - Excelentes para detectar padrões em dados estruturados.
  - Aplicáveis a séries temporais quando combinadas com LSTM.
  - Extração automática de características úteis dos preços históricos.
  
- **Transformers**
  - Utilizados em modelos como BERT e GPT, podem processar longas sequências sem perder contexto.
  - Aplicação crescente em finanças, porém mais custoso em termos computacionais.

- **Modelos Híbridos**
  - Integração de CNNs para feature extraction, LSTM para sequência temporal e Transformers para análise contextual avançada.
  - Pode oferecer previsões mais robustas ao combinar as vantagens de cada abordagem.

- **Por que escolhemos LSTM?**
  - Maior capacidade de captura de padrões temporais em dados financeiros.
  - Menor custo computacional em relação a Transformers.
  - Melhor interpretabilidade do modelo em comparação com redes puramente convolucionais.

### **2.3. Inteligência Financeira Aplicada**
- Como o mercado reage a diferentes eventos?

### **Impacto de Notícias e Análise de Sentimento**
- **Como notícias afetam o mercado financeiro?**
  - Eventos políticos e econômicos podem causar grandes variações nos preços de ativos.
  - Notícias inesperadas, como falências ou aquisições, impactam diretamente o comportamento dos investidores.

- **Medição do Sentimento do Mercado**
  - Uso de processamento de linguagem natural (NLP) para extrair sentimentos de manchetes e redes sociais.
  - Indicadores como Índice de Medo e Ganância (Fear and Greed Index) podem ajudar a interpretar emoções coletivas dos investidores.

- **Fontes de Dados para Análise de Sentimento**
  - Coleta de dados via APIs como Twitter, Google Trends e notícias financeiras.
  - Métodos de análise textual para determinar polaridade e emoção das informações.

- **Implementação da Análise de Sentimento em Modelos de Previsão**
  - Integração de variáveis de sentimento com dados de séries temporais.
  - Teste da correlação entre sentimento público e movimentação dos preços.
  - Ajuste do modelo para reagir de forma mais eficiente a mudanças abruptas de sentimento.

---

### **2.4. Estatísticas e Métodos para Melhorar as Previsões**

Para fazer previsões mais precisas, é essencial entender alguns conceitos estatísticos e técnicas que ajudam a interpretar os dados corretamente. Aqui estão algumas das principais abordagens utilizadas:

#### **Analisando Tendências e Padrões no Tempo**
- O objetivo principal de prever preços é identificar padrões no comportamento passado dos ativos e projetá-los para o futuro.
- Algumas técnicas comuns incluem **médias móveis** (que suavizam as variações diárias para identificar tendências) e **suavização exponencial** (que dá mais peso aos valores recentes, tornando a previsão mais responsiva às mudanças).

#### **Medição da Qualidade das Previsões**
- Para saber se um modelo está funcionando bem, precisamos medir o quão próximas estão as previsões dos valores reais.
- Algumas formas de avaliar isso incluem:
  - **Erro Quadrático Médio (MSE)**: Mede o tamanho médio do erro, dando mais peso aos erros maiores.
  - **Erro Médio Absoluto (MAE)**: Indica, em média, o quão distante a previsão está do valor real.
  - **Coeficiente de Determinação (R²)**: Indica o quão bem o modelo consegue explicar a variação dos preços.

Aqui está uma versão mais simples e intuitiva desse trecho:  

---

### **Entendendo Relações entre os Dados**  

Os preços dos ativos não se movimentam de forma completamente aleatória. Muitas vezes, eles seguem certos padrões que podem se repetir ao longo do tempo.  

- Por exemplo, um ativo pode subir toda vez que há um aumento na demanda ou cair em períodos de incerteza no mercado.  
- Para descobrir esses padrões, analisamos se os preços passados influenciam os preços futuros.  
- Muitas vezes, os preços de ativos seguem ciclos ou padrões sazonais.
  Ferramentas como
  **ACF (Autocorrelation Function)** 
  **PACF (Partial Autocorrelation Function)**
  ajudam a entender se há relações entre preços passados e futuros.

---

#### **ACF e PACF: Como Entender a Relação Entre os Preços Passados e Futuros**  

Quando tentamos prever os preços de um ativo, precisamos entender como os valores anteriores influenciam os próximos. Para isso, usamos dois métodos importantes:  

##### **1. ACF (Função de Autocorrelação)**  
- A ACF mede o quanto os preços passados estão relacionados com os preços futuros.  
- Por exemplo, se o preço de uma ação hoje for muito parecido com o de ontem e de anteontem, há uma forte autocorrelação.  
- Isso significa que o comportamento recente pode ser útil para prever os próximos valores.  

💡 **Exemplo prático:** Se o preço do ouro sobe por três dias seguidos, pode ser que ele tenha uma tendência de continuar subindo, e a ACF ajudaria a medir essa relação.  

##### **2. PACF (Função de Autocorrelação Parcial)**  
- A PACF é parecida com a ACF, mas ela mede apenas a relação direta entre um preço e um dia específico no passado, ignorando influências intermediárias.  
- Isso ajuda a descobrir quais períodos passados realmente influenciam os preços futuros, sem que a análise seja distorcida por efeitos acumulados.  

💡 **Exemplo prático:** Se o preço de uma ação hoje está fortemente ligado ao preço de três dias atrás, mas não é afetado pelos preços intermediários, a PACF mostrará essa relação direta.  

---

#### **Por que isso é importante?**  
- ACF e PACF ajudam a identificar quais períodos passados são realmente importantes para prever os próximos preços.  
- Essas informações são essenciais para escolher o melhor modelo de previsão e evitar erros ao tentar encontrar padrões que não existem.  

---

- Isso permite ajustar o modelo para capturar melhor essas tendências.

#### **Testando a Confiabilidade dos Dados**
- Antes de aplicar um modelo, é importante verificar se os dados são adequados para previsão. Dois testes estatísticos úteis são:
  - **Teste de Dickey-Fuller Aumentado (ADF)**: Verifica se os preços têm uma tendência persistente ou se são mais aleatórios.
  - **Teste de Ljung-Box**: Avalia se há padrões previsíveis nos erros do modelo.

#### **Preparando os Dados para Melhor Desempenho**
- Modelos de inteligência artificial funcionam melhor quando os dados estão bem organizados. Duas formas comuns de preparar os dados são:
  - **Normalização (MinMax Scaling)**: Ajusta os valores para um intervalo fixo, como 0 a 1, facilitando a aprendizagem da rede neural.
  - **Padronização (Z-score normalization)**: Transforma os dados para que tenham média zero e desvio padrão 1, ajudando modelos que dependem da distribuição dos valores.

---

## **Capítulo 3: Engenharia de Dados Avançada**
### **3.1. Fontes de Dados de Alta Qualidade**
- APIs para dados financeiros (Alpha Vantage, Yahoo Finance, Binance).
- Extração e manipulação de grandes volumes de dados.

### **3.2. Pré-processamento Estratégico**
- Criação de features derivadas para melhor desempenho.
- Filtragem de ruído e detecção de anomalias.

### **3.3. Construção de um Dataset Aprimorado**
- Técnicas avançadas de normalização e transformação.
- Amostragem inteligente para treinamento equilibrado.

---

## **Capítulo 4: Arquitetura Otimizada da Rede LSTM**
### **4.1. Design da Arquitetura Neural**
- Stack de múltiplas camadas LSTM.
- Regularização com Dropout e Batch Normalization.
- Comparação com outras abordagens arquitetônicas.

### **4.2. Implementação Profissional**
- Estrutura modular em Python.
- Código limpo e escalável.

### **4.3. Aprimoramento Contínuo**
- Treinamento dinâmico com técnicas de Transfer Learning.
- Monitoramento do desempenho e ajustes automáticos.

---

## **Capítulo 5: Predição e Validação de Resultados**
### **5.1. Testes Rigorosos com Dados Reais**
- Estratégia de validação cruzada.
- Simulações em cenários distintos do mercado.

### **5.2. Visualizações Impressionantes**
- Gráficos interativos para insights estratégicos.
- Comparação de previsões vs. preços reais.

### **5.3. Otimização Baseada em Feedback Contínuo**
- Ajustes automáticos conforme o mercado evolui.

---

## **Capítulo 6: Integração com Estratégias de Trading**
### **6.1. Transformando Previsões em Lucros**
- Como usar previsões para operações automatizadas.
- Modelos de risco e recompensa.

### **6.2. Backtesting e Testes de Robustez**
- Avaliação de performance em condições adversas.

### **6.3. Implementação de Algoritmos de Execução**
- Conectando o modelo a corretoras e APIs de trading.

---

## **Capítulo 7: Considerações Finais e Futuro do Projeto**
### **7.1. O que foi alcançado?**
### **7.2. Novos Caminhos para Expansão**
- Testes com Transformers e modelos híbridos.
- Aplicação em diferentes classes de ativos.

### **7.3. Como Contribuir e Evoluir o Projeto**

---

## **Capítulo 8: Recursos Avançados**
### **8.1. Leituras Recomendadas**
- Artigos acadêmicos e papers sobre LSTM, CNNs e Transformers para mercado financeiro.

### **8.2. Ferramentas e Tecnologias de Ponta**
- Bibliotecas, frameworks e ambientes de desenvolvimento.

### **8.3. Comunidade e Fóruns para Networking**
- Como aprender e trocar conhecimento com especialistas.

---

```bash
# =======================================================================
# AGENTE NEXO - INVESTIMENTO CONSERVADOR
# =======================================================================
# Modo CLI Ativado: Apresentando Resposta em Markdown + Estilo de Linha de Comando
# =======================================================================

Bem-vindo! A seguir, apresento um resumo rápido (macro) e depois um detalhamento interno (micro) do projeto **Agente Nexo - Investimento Conservador**, conforme solicitado.

[Digite "enter" para continuar...]
```

## :telescope: **Visão Macro do Projeto**

O diagrama macro exibe **todo o fluxo**: desde a coleta e pré-processamento dos dados, passando pelo treinamento de modelos, até a execução das operações na Nexo e notificação via Telegram.

```mermaid
flowchart LR
    subgraph Coleta e Pré-Processamento
        A1((Dados de Mercado))
        A2((Notícias e Sentimento))
        A3((Indicadores Técnicos))
        A4(Pré-processamento / Limpeza)
        A1 --> A4
        A2 --> A4
        A3 --> A4
    end

    subgraph Modelagem e Treinamento
        B1(Arquitetura NN - LSTM / Transformers)
        B2(Treinamento Supervisionado)
        B3(Aprendizado por Reforço - PPO)
    end
    
    subgraph Execução e Monitoramento
        C1(Decisão de Compra/Venda)
        C2(Ajuste de Stop Loss e Take Profit)
        C3(API Nexo)
        C4(Notificações Telegram)
    end

    subgraph Banco de Dados
        D1(Históricos de Preços)
        D2(Modelos Treinados)
        D3(Logs e Métricas)
    end

    A4 --> B1
    B1 --> B2
    B2 --> B3
    B3 -->|Modelo Treinado| C1
    
    C1 -->|Decisão: Compra/Venda| C3
    C1 -->|Define SL/TP| C2
    C2 -->|Ajusta Posições| C3
    C3 --> C4
    C3 -->|Executa Ordens| D1

    B3 -->|Checkpoints| D2
    C1 -->|Operações| D3
    B2 -->|Logs Treinamento| D3
```

### **Explicação Rápida (Macro)**

1. **Coleta de Dados**: O sistema busca preços, volumes, indicadores e notícias do mercado.  
2. **Pré-processamento**: Os dados são limpos, normalizados e transformados.  
3. **Modelagem / Treinamento**:  
   - **Rede Neural (LSTM/Transformers)** aprende padrões.  
   - **Aprendizado por Reforço (PPO)** refina a estratégia de trading.  
4. **Execução**: O modelo envia **ordens de compra/venda** para a plataforma Nexo, com ajuste automático de **Stop Loss** e **Take Profit**.  
5. **Notificação**: Todas as ações são enviadas por Telegram para manter o investidor informado.  
6. **Banco de Dados**: Todos os históricos, logs de treinamento e modelos treinados são armazenados para consultas futuras.

```bash
# Pressione ENTER para ver o Desenho Micro
```

## :microscope: **Visão Micro do Projeto**

Agora, observamos um **detalhamento interno** de como o **Agente** toma suas decisões minuto a minuto, usando módulos de rede neural, aprendizado por reforço e gerenciamento de risco.

```mermaid
flowchart TD
    subgraph Input de Mercado
        M1(Preços & Volume)
        M2(Volatilidade & Indicadores)
        M3(Sentimento / Notícias)
    end
    
    subgraph Rede Neural
        R1[Transformers / LSTM]
        R2[DNN Hidden Layers]
        R3[PPO Policy]
    end

    subgraph Decisão Final
        D1(Ação: Comprar, Vender, Manter)
        D2(Ajuste Dinâmico de SL/TP)
    end

    subgraph Execução e Feedback
        E1(Envio de Ordem - API Nexo)
        E2(Monitoramento da Posição)
        E3(Feedback: Recompensa/Penalização)
    end

    M1 --> R1
    M2 --> R1
    M3 --> R1
    R1 --> R2
    R2 --> R3
    R3 --> D1
    R3 --> D2
    D1 --> E1
    D2 --> E1
    E1 --> E2
    E2 --> E3
    E3 --> R3
```

### **Explicação Rápida (Micro)**

1. **Input de Mercado**: Preços, volume, volatilidade e dados de sentimento são capturados continuamente.  
2. **Rede Neural**:  
   - Módulo **Transformers ou LSTM** detecta padrões temporais complexos.  
   - Camadas densas (**DNN**) refinam a análise, combinando múltiplas variáveis.  
   - **PPO (Aprendizado por Reforço)** recebe feedback (recompensa/penalização) e ajusta a política de ação.  
3. **Decisão Final**:  
   - **Comprar, Vender ou Manter** a posição.  
   - **Ajustar Stop Loss e Take Profit** dinamicamente, conforme risco e volatilidade.  
4. **Execução**: As ordens são enviadas para a Nexo, e o agente **monitora** em tempo real.  
5. **Feedback**: O resultado (lucro, prejuízo ou neutralidade) retorna para o PPO, melhorando as futuras decisões.

---

## Treinamento

```bash
┌─────────────────────────────────────────────────────────────────────────┐
│              AGENTE NEXO - SESSÃO DE TREINAMENTO DA REDE NEURAL        │
└─────────────────────────────────────────────────────────────────────────┘

Bem-vindo à sessão focada no **treinamento da rede neural** do Agente Nexo e na definição dos “jogos” (cenários) para aprimorar nosso modelo de investimento conservador.

Por favor, selecione uma das opções abaixo para navegar no sistema:

1. [Definição dos Cenários de Treinamento ("Jogos")]
2. [Método de Seleção dos Melhores Indivíduos (Modelos)]
3. [Retornar ao Menu Principal]

Digite o número desejado e pressione ENTER:
```

### **1) Definição dos Cenários de Treinamento ("Jogos")  

```bash
$ opçao_selecionada = 1
> Carregando cenários de treinamento ...
```
A ideia é submeter o Agente Nexo a diferentes **jogos** ou **cenários de mercado**, permitindo que ele aprenda a tomar decisões assertivas em condições variadas. Cada jogo gera recompensas (positivas) e penalizações (negativas), ajustando o comportamento do agente via **Aprendizado por Reforço**.

**Jogos Principais:**

1. **Mercado de Baixa Extrema (Bear Market)**
   - **Cenário:** O mercado cai ~10% em curto período.  
   - **Objetivo:** Ensinar o agente a **evitar perdas** excessivas e encontrar um ponto de entrada seguro.  
   - **Recompensa:** Protege o capital e identifica recuperação.  

2. **Mercado Lateral (Consolidação)**
   - **Cenário:** Preço oscila em uma faixa estreita, sem tendência definida.  
   - **Objetivo:** Explorar **comprar no fundo e vender no topo** dentro da faixa, evitando overtrading.  
   - **Recompensa:** Precisão nas entradas e saídas dentro do canal.  

3. **Pump & Dump (Volatilidade Extrema)**
   - **Cenário:** O preço do BTC/USDT dispara rapidamente (+15%), mas despenca em seguida (-20%).  
   - **Objetivo:** Ensinar o agente a **entrar no momento certo** ou **evitar o topo** para não ser pego na queda.  
   - **Recompensa:** Capturar parte do pump e sair antes do dump.  

4. **Notícias Impactantes**
   - **Cenário:** Surge uma notícia que afeta o sentimento do mercado (positivo ou negativo).  
   - **Objetivo:** Reagir de forma rápida ao novo fluxo de informação, evitando **armadilhas** quando o movimento for apenas “ruído” ou aproveitando uma **mudança real de tendência**.  
   - **Recompensa:** Ajustar posições conforme a notícia; se a ação for coerente, o agente recebe alta pontuação.  

5. **Flash Crash (Queda Rápida e Recuperação)**
   - **Cenário:** O BTC cai muito rápido (10%) e retoma a maior parte da queda (8%) em seguida.  
   - **Objetivo:** Não “despejar tudo” no pânico e aproveitar preços descontados.  
   - **Recompensa:** Se o agente conseguir **comprar no fundo** e lucrar com a recuperação, ganha pontuação elevada.  

Esses cenários simulam situações críticas e testam a **robustez da rede neural**. É por meio desses “jogos” que o Agente Nexo aprende **estratégias vencedoras** e aptas a se adaptar ao mundo real.

---

### **2) Método de Seleção dos Melhores Indivíduos (Modelos)**  

```bash
$ opçao_selecionada = 2
> Carregando critérios de seleção ...
```
Após rodar as simulações nos diversos jogos, teremos **vários agentes/indivíduos** treinados, cada qual com parâmetros e políticas de ação distintas. Para escolher o(s) melhor(es) modelo(s), adotamos métricas de performance e estabilidade:

1. **Métrica de Retorno vs. Risco**  
   - **Sharpe Ratio**: Mede a relação entre retorno e volatilidade das operações.  
   - **Sortino Ratio**: Foca no risco de queda (drawdown), punindo operações muito arriscadas.

2. **Drawdown Máximo (Max Drawdown)**  
   - Verifica a maior perda durante o período de simulação.  
   - Modelos com drawdown muito alto podem ser excluídos, pois **não são conservadores**.  

3. **Estabilidade de Lucro ao Longo do Tempo**  
   - Avalia se o agente mantém desempenho consistente em diversos cenários ou se só foi bem em um cenário específico.

4. **Precisão e Taxa de Acerto**  
   - Verifica a quantidade de operações bem-sucedidas vs. total de trades.  
   - **Importante**: Uma alta taxa de acerto sozinha não basta; é necessário equilibrar **risco x retorno**.  

5. **Critério de Consistência em Múltiplos Jogos**  
   - O agente é posto à prova nos 5 cenários acima.  
   - **Pontos Extras** para quem mantiver bom desempenho em todos os cenários, evitando ser muito “especialista” em apenas um tipo de mercado.  

> **Observação**: Ao final de cada fase de treinamento, apenas os indivíduos/melhores checkpoints que **atendem aos critérios de risco e retorno** são preservados no repositório. Isso garante a evolução contínua do Agente Nexo rumo a estratégias cada vez mais **estáveis e conservadoras**.

---

### **3) Retornar ao Menu Principal**  

```bash
$ opçao_selecionada = 3
> Encerrando a sessão de treinamento da rede neural. Retornando ao menu...
```

**Sessão Finalizada.**  
Use este guia para conduzir seus experimentos de treinamento, definir cenários de teste (“jogos”) e selecionar os melhores indivíduos (modelos) com base em métricas de **risco** e **retorno**. Assim, garantimos uma estratégia conservadora e robusta para o Agente Nexo.

```bash
# =======================================================================
# AGENTE NEXO - INVESTIMENTO CONSERVADOR
# =======================================================================
# SEÇÃO: CIRCUIT BREAKER
# =======================================================================
# Modo CLI Ativado: Resposta em Markdown + Estilo de Linha de Comando
# =======================================================================
```

# ⚠️ **Circuit Breaker: Gerenciamento de Perdas e Pausa de Ação**
Esta seção detalha o **mecanismo de Circuit Breaker** dentro do **Agente Nexo - Investimento Conservador**, que tem como objetivo **gerenciar perdas** e **pausar** automaticamente as operações quando a estratégia sofre perdas consecutivas ou atinge níveis de drawdown pré-definidos.

---
## 1. **Conceito Geral**
O **Circuit Breaker** atua como um sistema de **proteção** para evitar que o Agente continue operando de forma **descontrolada** quando o mercado está desfavorável ou a estratégia começa a falhar repetidamente. Assim como nos mercados tradicionais, onde uma “parada” de negociação pode ser acionada, este módulo **interrompe** temporariamente as operações do agente até que uma nova confirmação de retomada positiva seja identificada.

### **Benefícios**:
1. **Limitar Perdas**: Impedir que o capital seja erodido por uma sequência de operações negativas.
2. **Análise Pós-Perda**: Dar tempo ao modelo/usuário para avaliar o que pode estar causando as perdas.
3. **Retomada Segura**: Voltar a operar somente quando houver sinais de que o mercado ou a estratégia se estabilizou.

---

## 2. **Como Funciona**

```mermaid
flowchart LR
    A[Monitor de Perdas] --> B[Controle de Limite de Perdas Consecutivas]
    B -->|N Perdas Seguidas?| C[Aciona Circuit Breaker]
    C -->|Pausa Operações| D[Timer/Reavaliação]
    D -->|Verifica Condições de Retomada| E[Retorno Gradual ao Mercado]
```

1. **Monitor de Perdas (Loss Tracker)**  
   - O Agente Nexo possui um contador de perdas e um cálculo de drawdown.
   - Cada vez que ocorre uma perda, esse contador é incrementado.

2. **Controle de Limite (N Perdas Seguidas)**  
   - O usuário (ou o config.yaml) define um número limite de **perdas consecutivas** (exemplo: `max_loses_in_row = 3`) ou um **limite de drawdown** (exemplo: `max_drawdown = 10%`).
   - Ao atingir esse limite, o módulo **acende o sinal de alerta**.

3. **Acionamento do Circuit Breaker**  
   - Assim que o limite é excedido (quantidade de perdas ou drawdown acumulado), o agente **para de enviar novas ordens** à corretora.
   - O sistema pode enviar notificação via **Telegram**:  
     - **Exemplo de Alerta**: “Circuit Breaker ativado: perdas sucessivas detectadas. Operações pausadas.”

4. **Pausa Operacional (Sleep Mode)**  
   - Define-se um período de **pausa** (por exemplo, 30 minutos, 1 hora ou até 1 dia) no qual o agente não executa nenhuma nova operação.
   - Durante esse intervalo, **pode-se rodar uma revalidação do modelo** ou simplesmente aguardar.

5. **Condições de Retomada**  
   - Passado o tempo de pausa, o agente verifica **condições técnicas de retomada**:  
     - Redução de volatilidade?  
     - Confirmação de tendência de reversão?  
     - Sinais de menor risco no mercado?  
   - Se as condições forem satisfatórias, o Circuit Breaker é **desativado** e o agente retoma operações de forma gradual.

---

## 3. **Configurando o Circuit Breaker**

### **Exemplo de Parâmetros no `config.yaml`:**
```yaml
circuit_breaker:
  enabled: true
  max_consecutive_losses: 3        # Máximo de perdas seguidas permitidas
  max_drawdown_percent: 10         # % de drawdown que aciona o Circuit Breaker
  cooldown_period_minutes: 60       # Tempo de pausa (em minutos) após acionado
  resume_condition: 'volatility'    # Ou 'tempo', 'manual', etc.
  notify_telegram: true
```

- **enabled**: Habilita ou desabilita todo o recurso do Circuit Breaker.  
- **max_consecutive_losses**: Número de trades perdedores consecutivos antes da parada.  
- **max_drawdown_percent**: Limite de drawdown (em %) sobre o capital.  
- **cooldown_period_minutes**: Quantos minutos o agente permanecerá em pausa.  
- **resume_condition**: Pode ser baseada em tempo, volatilidade, manual (o usuário precisa reativar), etc.  
- **notify_telegram**: Envio de alerta quando o CB é disparado e quando a retomada ocorre.

---

## 4. **Implementação Resumida em Python**

```python
# src/circuit_breaker.py

import time
import logging

class CircuitBreaker:
    def __init__(self, max_loses_in_row, max_drawdown_percent, cooldown, notify_callback=None):
        self.max_loses_in_row = max_loses_in_row
        self.max_drawdown_percent = max_drawdown_percent
        self.cooldown = cooldown
        self.notify_callback = notify_callback

        self.loss_count = 0
        self.drawdown_percent = 0
        self.active = False

    def register_loss(self, loss_percent):
        self.loss_count += 1
        self.drawdown_percent += loss_percent  # Exemplo simplificado
        self.check_trigger()

    def check_trigger(self):
        if (self.loss_count >= self.max_loses_in_row) or (self.drawdown_percent >= self.max_drawdown_percent):
            self.trigger()

    def trigger(self):
        self.active = True
        logging.warning("Circuit Breaker ATIVADO! Pausando operações.")
        if self.notify_callback:
            self.notify_callback("Circuit Breaker ATIVADO! Perdas sucessivas detectadas.")

    def cooldown_period(self):
        logging.info(f"Pausa de {self.cooldown} minutos iniciada.")
        time.sleep(self.cooldown * 60)
        self.reset()

    def reset(self):
        self.loss_count = 0
        self.drawdown_percent = 0
        self.active = False
        logging.info("Circuit Breaker DESATIVADO. Retomando operações.")
        if self.notify_callback:
            self.notify_callback("Circuit Breaker DESATIVADO. Operações retomadas.")

    def can_trade(self):
        # Se o Circuit Breaker estiver ativo, retorna False
        return not self.active
```

### **Uso no Agente Principal**:
```python
# src/agent.py

from circuit_breaker import CircuitBreaker

# Criar instância do Circuit Breaker com os parâmetros definidos
cb = CircuitBreaker(
    max_loses_in_row=3,
    max_drawdown_percent=10,
    cooldown=60,
    notify_callback=send_telegram_message  # Exemplo
)

def run_agent_step():
    # Verificar se o Circuit Breaker permite operar
    if not cb.can_trade():
        print("Circuit Breaker ativo. Aguardando cooldown...")
        return

    # Executar lógica de trading...
    # Se ocorrer perda na operação:
    cb.register_loss(loss_percent=2)

    # Se o Circuit Breaker for acionado, entrar em cooldown:
    if cb.active:
        cb.cooldown_period()
        return
```

---

## 5. **Integração com Telegram**

Quando o **Circuit Breaker** é acionado, o sistema pode enviar mensagens de alerta ao usuário:

```python
# src/utils_telegram.py
import telepot

def send_telegram_message(msg):
    bot = telepot.Bot("TELEGRAM_BOT_TOKEN")
    chat_id = "SEU_CHAT_ID"
    bot.sendMessage(chat_id, msg)
```

- **Exemplos de Alertas**:
  - **“Circuit Breaker ATIVADO: 3 perdas consecutivas. Operações pausadas por 60min.”**
  - **“Circuit Breaker DESATIVADO: retomando operações.”**

---

## 6. **Recomendações de Uso e Teste**

1. **Definir Limites Coerentes**  
   - Ajustar o `max_consecutive_losses` e `max_drawdown_percent` de acordo com a **tolerância ao risco** do projeto.  
2. **Backtest**  
   - Simular cenários (Bear Market, Flash Crash, etc.) para validar o comportamento do Circuit Breaker.  
3. **Log Detalhado**  
   - Manter um log com data/hora das ativações para análise futura.  
4. **Possível Intervenção Manual**  
   - Permitir que o usuário possa **manualmente** desativar ou ativar o Circuit Breaker conforme necessidade.

---

## 7. **Diagrama de Integração com o Agente**

```mermaid
flowchart LR
    A(Dados do Mercado) --> B[Análise do Agente (RL/NN)]
    B --> C[Decisão de Buy/Sell]
    C -->|Resultado do Trade| D[Registro de Lucro/Perda]

    D --> E(Circuit Breaker)
    E -->|Se atingiu limite de perdas| F[Operações Pausadas]
    F -->|Cooldown + Reavaliação| G[Retomada ou Manutenção de Pausa]
    G -->|Se OK| B
```

1. **O Agente** realiza a decisão de negociação.  
2. **Registro de Perda/Lucro** atualiza o **Circuit Breaker**.  
3. Ao exceder o **limite**, o sistema **pausa** as operações.  
4. Após o **cooldown**, o agente **reavalia** se pode voltar ou se deve continuar pausado.

---

### **Conclusão**
O **Circuit Breaker** adiciona **robustez e segurança** ao sistema de trading, protegendo contra sequências de perdas que podem comprometer seriamente o capital. Essa abordagem é **fundamental** em estratégias conservadoras, pois limita a exposição em momentos de **alta volatilidade** ou **ineficiência temporária** do modelo.

\> **Agora, o Agente Nexo está equipado com um componente adicional de proteção: o Circuit Breaker.**  

```bash
# Comando de Encerramento
echo "Circuit Breaker configurado com sucesso! Operações protegidas contra múltiplas perdas."
```
