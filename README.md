# 🌍 Simulador Socioeconômico V12

Um laboratório de simulação macroeconômica, demográfica e geopolítica em Python que modela e compara o desempenho de quatro matrizes ideológicas e econômicas sob exatamente as mesmas leis físicas, climáticas e produtivas: **Socialismo**, **Social Democracia**, **Conservadorismo** e **Liberalismo**.

Desenvolvido com arquitetura modular baseada em dinâmica de sistemas, o simulador permite observar como diferentes escolhas de política fiscal, carga tributária, gasto social e liberdade de mercado moldam a prosperidade, a resiliência a crises e o bem-estar de uma população ao longo de décadas ou séculos.

---

## 📑 Índice
1. [Visão Geral e Princípios](#-visão-geral-e-princípios)
2. [Arquitetura Modular](#-arquitetura-modular)
3. [Manual de Instalação e Execução](#-manual-de-instalação-e-execução)
4. [Manual de Parâmetros dos Modelos](#-manual-de-parâmetros-dos-modelos)
5. [Manual de Eventos Estocásticos](#-manual-de-eventos-estocásticos)
6. [Dicionário de Indicadores (Saída)](#-dicionário-de-indicadores-saída)
7. [Como Personalizar e Expandir](#-como-personalizar-e-expandir)

---

## 🎯 Visão Geral e Princípios

* **Imparcialidade Estrutural:** Todas as ilhas iniciam com a mesma população (`10.000` habitantes), os mesmos recursos naturais iniciais e obedecem às mesmas equações de produtividade agrícola, industrial e demográfica. Nenhuma ideologia recebe bônus ocultos no código.
* **Emergência Orgânica:** Fenômenos como fuga de cérebros/migração, acúmulo de dívida pública, inflação de juros, superávit comercial e escassez alimentar surgem naturalmente da interação entre os módulos a cada ciclo anual.
* **Resiliência a Choques:** Eventos climáticos e tecnológicos aleatórios testam a capacidade de cada modelo absorver crises sem colapsar.

---

## ⚙️ Arquitetura Modular

O sistema é dividido em **9 módulos Python independentes**, executados sequencialmente a cada ano simulado:

```text
simulador-socioeconomico/
├── main.py          # Orquestrador, CLI (argparse), loop temporal e gráficos
├── demografia.py    # Natalidade, mortalidade e transição etária (crianças/adultos/idosos)
├── economia.py      # Capital, empresas, emprego formal/informal, salários e produtividade
├── recursos.py      # Produção, consumo e regeneração de Alimentos, Energia e Minério
├── governo.py       # Impostos, gastos sociais, corrupção, fiscalização, juros e dívida
├── comercio.py      # Comércio exterior bilateral e socorro alimentar entre ilhas
├── migracao.py      # Fluxo migratório baseado em PIB per capita, emprego e felicidade
├── eventos.py       # Choques estocásticos (secas, crises energéticas, booms)
└── indicadores.py   # Consolidação de expectativa de vida e índice de felicidade
```

---

## 🚀 Manual de Instalação e Execução

### 1. Pré-requisitos e Instalação
Certifique-se de ter o **Python 3.10+** instalado. Clone o repositório e instale as dependências (`pandas` e `matplotlib`):

```bash
git clone https://github.com/seu-usuario/simulador-socioeconomico.git
cd simulador-socioeconomico
pip install pandas matplotlib
```

### 2. Modos de Execução via Terminal (CLI)

O simulador oferece três formas de inicialização através do `main.py`:

#### A. Modo Interativo (Com Temporizador)
Inicia o prompt solicitando a duração da simulação. Caso você não digite nada em **30 segundos**, o sistema inicia automaticamente com o padrão de **100 anos**:
```bash
python main.py
```

#### B. Modo Automático por Duração Específica (`-t` ou `--anos`)
Ideal para testes rápidos, scripts automatizados ou ambientes como Google Colab e Jupyter Notebook. Pula o prompt e executa imediatamente:
```bash
# Simula 50 anos
python main.py -t 50

# Simula 500 anos (teste de estresse de longo prazo)
python main.py --anos 500
```

#### C. Modo Automático Padrão (`-p` ou `--pronto`)
Executa instantaneamente o ciclo padrão de **100 anos** sem nenhuma interação:
```bash
python main.py -p
```

---

## 🏛️ Manual de Parâmetros dos Modelos

As quatro ilhas são instanciadas no `main.py` com as seguintes configurações políticas iniciais:

| Modelo | Liberdade Econômica | Carga Tributária (`imposto`) | Gasto Social (`gasto_social`) | Perfil Estratégico |
| :--- | :---: | :---: | :---: | :--- |
| **Socialismo** | `30` | `45%` | `55%` | Forte intervenção estatal, alta redistribuição e menor dinamismo privado. |
| **Social Democracia** | `65` | `35%` | `40%` | Economia de mercado regulada combinada com estado de bem-estar social. |
| **Conservador** | `55` | `20%` | `20%` | Estado enxuto, baixa tributação, estabilidade institucional e fiscalização. |
| **Liberal** | `90` | `12%` | `10%` | Livre mercado máximo, impostos mínimos e forte estímulo ao capital privado. |

---

## ⚡ Manual de Eventos Estocásticos

A cada ano simulado, o módulo `eventos.py` avalia uma probabilidade de **25%** de ocorrência de um choque continental. Os eventos críticos são registrados no console a cada década:

* **⚠️ Seca Severa:** Reduz imediatamente os estoques de alimentos de todas as ilhas em **25%**, testando a segurança alimentar e o comércio exterior.
* **⚡ Crise Energética:** Reduz as reservas de energia do continente em **20%**, impactando o fator de produção industrial.
* **🚀 Boom Tecnológico:** Seleciona aleatoriamente uma ilha e impulsiona sua inovação (`+15`) e produtividade (`+10%`).
* **🌾 Boom Agrícola:** Condições climáticas excepcionais geram `+5.000` toneladas extras de alimentos para todas as ilhas.

---

## 📊 Dicionário de Indicadores (Saída)

Ao final da simulação, o console exibe uma tabela consolidada com **34 métricas**. Veja como interpretar as principais colunas:

### Macroeconomia & Trabalho
* **`PIB` / `PIB_per_capita`**: Riqueza total gerada pela soma dos setores agro, indústria e serviços, e sua divisão por habitante.
* **`Capital` / `Empresas`**: Estoque de capital acumulado e número de unidades produtivas ativas.
* **`Desemprego_%`**: Percentual da força de trabalho sem ocupação formal ou informal.
* **`Produtividade`**: Eficiência média por trabalhador, influenciada por educação, inovação e liberdade econômica.

### Demografia & Migração
* **`Nascimentos` / `Mortes`**: Fluxo vegetativo acumulado ao longo de toda a simulação.
* **`Saldo_Migratorio`**: Diferença entre `Imigrantes` atraídos e `Emigrantes` perdidos. Ilhas com maior felicidade e PIB per capita atraem população das ilhas vizinhas.
* **`Expectativa_Vida`**: Longevidade média calculada a partir do investimento em saúde e ausência de fome.

### Recursos & Comércio Exterior
* **`Alimentos` / `Energia` / `Minerio`**: Estoques físicos remanescentes ao fim do período.
* **`Fome_Grave_%` / `Pessoas_em_Fome`**: Percentual e total absoluto da população em situação de déficit calórico severo.
* **`Exportacoes` / `Importacoes` / `Saldo_Comercial`**: Volume de alimentos e minérios negociados bilateralmente entre ilhas superavitárias e deficitárias.

### Governo & Bem-Estar
* **`Corrupcao_%` / `Perda_Corrupcao`**: Nível de desvio de recursos públicos, mitigado por `Transparencia` e `Fiscalizacao`.
* **`Divida` / `Juros_%`**: Endividamento acumulado pelo governo quando os gastos superam a arrecadação, e a taxa de juros resultante do risco fiscal.
* **`Felicidade`**: Índice sintético final (`0` a `100`) que pondera renda, emprego, saúde, educação, segurança alimentar e liberdade.

---

## 🛠️ Como Personalizar e Expandir

Você pode criar novos cenários editando diretamente o arquivo `main.py` na lista `ilhas`:

```python
ilhas = [
    Ilha("Socialismo", liberdade=30, imposto=0.45, gasto_social=0.55),
    Ilha("Social Democracia", liberdade=65, imposto=0.35, gasto_social=0.40),
    Ilha("Conservador", liberdade=55, imposto=0.20, gasto_social=0.20),
    Ilha("Liberal", liberdade=90, imposto=0.12, gasto_social=0.10),
    # Exemplo: Adicione um quinto modelo customizado
    Ilha("Anarcocapitalismo", liberdade=100, imposto=0.02, gasto_social=0.00)
]
```

---

## 💻 Tecnologias Utilizadas
* **Python 3.10+**
* **Pandas** — Tabulação e análise de indicadores macroeconômicos
* **Matplotlib** — Visualização gráfica comparativa
* **Argparse & Select** — Interface CLI com suporte a execução *headless* e temporizador assíncrono
