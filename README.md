# 🌍 Simulador Socioeconômico V12

Um simulador macroeconômico, demográfico e geopolítico em Python que modela e compara o desempenho de quatro diferentes matrizes ideológicas e econômicas sob as mesmas leis físicas e produtivas: **Socialismo**, **Social Democracia**, **Conservadorismo** e **Liberalismo**.

O projeto utiliza uma arquitetura modular inspirada em princípios de engenharia de sistemas e dinâmica de sistemas para observar como políticas fiscais, tributárias, de liberdade econômica e de investimento moldam o desenvolvimento de longo prazo de uma sociedade.

---

## 🏛️ Modelos em Competição

1. **Socialismo**: Foco em alta taxação, forte redistribuição estatal via gastos sociais e forte planejamento central.
2. **Social Democracia**: Equilíbrio entre economia de mercado regulada, forte rede de proteção social e investimentos públicos em educação e saúde.
3. **Conservador**: Tributação moderada, foco em estabilidade institucional, fiscalização rigorosa e manutenção de valores tradicionais de mercado.
4. **Liberal**: Baixa tributação, alta liberdade econômica, livre mercado e estímulo máximo ao acúmulo de capital e inovação privada.

---

## ⚙️ Arquitetura Modular (`Python`)

O simulador é dividido em módulos independentes e especializados que operam em ciclos anuais:

- **`main.py`**: Orquestrador principal da simulação, CLI com `argparse` e gerador de relatórios e gráficos analíticos.
- **`demografia.py`**: Modela natalidade, transição etária (crianças, adultos, idosos) e mortalidade baseada em saúde pública e fome.
- **`economia.py`**: Calcula formação de capital, surgimento de empresas, emprego formal/informal, salários, produtividade e inflação.
- **`recursos.py`**: Gerencia a extração, consumo e regeneração de recursos estratégicos (Alimentos, Energia e Minério).
- **`governo.py`**: Controla arrecadação de impostos, gastos sociais, corrupção, burocracia, dívida pública e taxa de juros.
- **`comercio.py`**: Sistema de comércio exterior bilateral com excedentes e socorro alimentar prioritário entre ilhas.
- **`migracao.py`**: Simula o fluxo migratório populacional baseado em qualidade de vida, PIB per capita e felicidade.
- **`eventos.py`**: Injeção de choques estocásticos (secas severas, crises energéticas, booms tecnológicos e agrícolas).
- **`indicadores.py`**: Consolida índices compostos como expectativa de vida, IDH simplificado e índice de felicidade geral.

---

## 🚀 Como Executar

### Pré-requisitos
Certifique-se de ter o Python instalado junto com as bibliotecas necessárias (`pandas` e `matplotlib`):
```bash
pip install pandas matplotlib
