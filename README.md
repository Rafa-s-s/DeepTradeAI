# DeepTradeAI
**DeepTradeAI** é um projeto em desenvolvimento que utiliza Inteligência Artificial para criar uma solução automatizada de trading. Ele é projetado para analisar, prever e executar estratégias de trading em múltiplas moedas e plataformas. O projeto combina técnicas avançadas de **Engenharia de Dados**, **Machine Learning** e **Automação de Processos**.

---

## Status do Projeto
🚧 **Em desenvolvimento**: Algumas funcionalidades ainda estão sendo implementadas e otimizadas.

---

## Objetivo
Criar uma IA trader que:
- Analise dados de mercado em tempo real.
- Gere indicadores técnicos detalhados.
- Aprenda padrões complexos por meio de **aprendizado por reforço**.
- Execute decisões de compra e venda automaticamente, otimizando lucros.

---

## Estrutura do Projeto
O projeto está dividido em três partes principais:

### 1. **Coleta de Dados (Engenharia de Dados)**
Para alimentar o modelo de IA, diversos scripts foram desenvolvidos para coletar, processar e armazenar dados de múltiplas fontes:
- **Scripts principais:**
  - `crypto_compare_collector.py`: Coleta dados de OHLC da API CryptoCompare.
  - `coletor_indicadores.py`: Adiciona indicadores técnicos aos dados coletados.
  - `mexc_hourly_data_collector.py`: Coleta dados da MEXC Exchange em intervalos de 1 hora.
  - Outros coletores para fontes como Binance, CoinGecko e CryptoPanic.
- **Exemplo do `coletor_indicadores.py`:**
  Este script processa arquivos CSV com dados históricos e gera indicadores técnicos como RSI e ATR, utilizando bibliotecas especializadas. Ele também organiza os dados em pastas específicas por moeda.
  
![mexc_trade_bot – coletor_indicadores py 26_12_2024 02_18_46](https://github.com/user-attachments/assets/a49fba62-9edd-4370-a971-88089b604b31)
---

### 2. **Montagem de Datasets**
Os dados coletados são organizados em um formato unificado para facilitar o treinamento do modelo:
- **Script principal:** `montar_dataset.py`
- **Descrição:** Combina dados de OHLC e indicadores em um único dataset consolidado para cada moeda.
- **Saída:** Arquivos `.csv` organizados no diretório `Dataset_Final`.
- **Funcionalidade adicional:** Identifica automaticamente o tipo de dado (OHLC ou Indicadores) e faz a união com base na coluna de data.


![mexc_trade_bot – montar_dataset py 26_12_2024 02_25_40](https://github.com/user-attachments/assets/f7759de1-d101-4dd4-b91f-f9abe4cc01f4)
![mexc_trade_bot – historico_axs_dataset csv 26_12_2024 02_32_52](https://github.com/user-attachments/assets/406ac233-d928-4533-9471-ab5d461453a9)
![OHLC_5m_15m_30m_1h_Binance 26_12_2024 02_34_59](https://github.com/user-attachments/assets/da273ab5-a205-42ec-9b6d-9a7aaaa6e6a9)
---


### 3. **Treinamento da IA**
A IA utiliza aprendizado por reforço para otimizar estratégias de trading:
- **Modelo:** Aprendizado por reforço com DQN (Deep Q-Network).
- **Framework utilizado:** TensorTrade.
- **Funcionamento:**
  - Os dados consolidados são transformados em um ambiente de simulação.
  - O agente aprende a tomar decisões de compra/venda otimizadas.
  - Resultados são salvos para futura análise e validação.
- **Destaques do código da IA:**
  - Implementa indicadores técnicos como RSI e ATR no pipeline de dados.
  - Utiliza carteiras simuladas para testar diferentes estratégias.
  - Permite ajustes de comissão e outras variáveis para maior realismo.

---

## Tecnologias Utilizadas
- **Linguagem:** Python
- **Bibliotecas:**
  - Pandas: Manipulação de dados.
  - TensorTrade: Criação de ambientes de negociação simulados.
  - TA-Lib: Geração de indicadores técnicos.
  - TensorFlow: Base para aprendizado por reforço.
  - OS: Automação de manipulação de arquivos.
- **APIs Integradas:**
  - Binance
  - CoinGecko
  - MEXC
  - CryptoCompare

---

## Limitações e Nota Importante
Este projeto está em desenvolvimento, passando por testes e melhorias constantes. Embora as funcionalidades básicas já estejam implementadas, ele ainda não está finalizado e não deve ser utilizado em ambientes reais.

---

## Como Contribuir
Este projeto ainda está em andamento. Se você tiver sugestões ou melhorias, sinta-se à vontade para abrir issues ou enviar pull requests. Toda ajuda é bem-vinda! 

---

## Licença
Este projeto está sob a licença MIT. Consulte o arquivo `LICENSE` para mais detalhes.
