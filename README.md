# Simulador Socioeconómico Modular

Um simulador macroeconómico e demográfico baseado em Python, projetado para comparar a dinâmica de longo prazo (100 anos) entre quatro modelos políticos e económicos distintos: **Socialismo**, **Social-Democracia**, **Conservador** e **Liberal**.

---

## 🏗️ Arquitetura do Projeto

O projeto adota uma arquitetura estritamente modular, dividindo as responsabilidades de simulação em componentes independentes para facilitar a manutenção, a calibração de parâmetros e a legibilidade do código:

* **`config.py`**: Centraliza os parâmetros globais, taxas fiscais, limites demográficos e variáveis macroeconómicas iniciais.
* **`demografia.py`**: Gere a evolução populacional, natalidade, mortalidade e a distribuição por faixas etárias (*crianças*, *adultos*, *idosos*).
* **`economia.py`**: Modela o mercado de trabalho, o produto interno bruto (PIB), a produção empresarial e o desemprego friccional.
* **`recursos.py`**: Controla a extração, o consumo e a regeneração de recursos naturais essenciais (*alimentos*, *energia*, *minérios*).
* **`governo.py`**: Simula a arrecadação de impostos, gastos públicos, previdência social, dívida pública e a flutuação endógena da taxa de juros.
* **`comercio.py`**: Executa transações comerciais e de compensação de excedentes entre os diferentes modelos.
* **`migracao.py`**: Calcula e processa fluxos migratórios baseados em diferenciais regionais de qualidade de vida e felicidade.
* **`indicadores.py`**: Atualiza índices de desenvolvimento humano (*saúde*, *educação*, *inovação*) em função do investimento social per capita.
* **`eventos.py`**: Introduz choques estocásticos e exógenos (*secas severas*, *booms tecnológicos*, *crises energéticas*).
* **`main.py`**: Orquestra o ciclo temporal da simulação, a consolidação dos dados em estruturas tabulares e a geração de gráficos analíticos.

---

## ⚙️ Pré-requisitos e Dependências

Para executar o simulador com sucesso, certifique-se de ter o Python instalado juntamente com as seguintes bibliotecas:

* `pandas`
* `matplotlib`

Você pode instalar as dependências necessárias executando:

```bash
pip install pandas matplotlib
```

---

## 🚀 Como Executar

O projeto está otimizado para ser executado num ambiente interativo (como o **Jupyter Notebook** ou **Google Colab**) utilizando os comandos mágicos de criação de ficheiros do próprio ambiente.

1. Clone o repositório para a sua máquina ou ambiente de trabalho:
   ```bash
   git clone https://github.com/seu-utilizador/nome-do-repositorio.git
   cd nome-do-repositorio
   ```
2. Abra o ambiente Jupyter e execute as células de código sequencialmente para gerar os módulos locais e iniciar a simulação através do `main.py`.

---

## 📊 Visualização de Resultados

No final de cada execução de 100 anos, o simulador compila automaticamente um histórico detalhado e gera gráficos comparativos que evidenciam:
* A trajetória de crescimento e flutuação do **PIB**.
* A evolução comparativa da **Felicidade Média** e bem-estar social em cada modelo político-económico.

---

## 🤝 Contribuições

Contribuições, melhorias de modelagem económica e sugestões de novos cenários são sempre bem-vindas! Sinta-se à vontade para abrir uma *issue* ou enviar um *pull request*.
