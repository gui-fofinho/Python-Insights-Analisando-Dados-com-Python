# Python Insights - Analisando Dados com Python

O **Python Insights** é um projeto em Python voltado para análise de dados, permitindo identificar padrões e insights importantes. Neste exemplo, o programa analisa os cancelamentos de assinaturas de uma empresa, identifica os motivos e sugere soluções para reduzir a taxa de cancelamento.

---

## Funcionalidades

- **Análise de Cancelamentos:** Conta quantas assinaturas foram canceladas em determinado período.
- **Identificação de Motivos:** Analisa os principais motivos pelos quais clientes cancelaram suas assinaturas.
- **Sugestão de Soluções:** Baseado nos motivos, o sistema sugere ações que podem reduzir futuros cancelamentos.

---

## Tecnologias Utilizadas

- **Python** – Linguagem principal do projeto.
- **Pandas** – Para leitura e manipulação da base de dados.
- **Matplotlib / Seaborn** – Para visualização gráfica dos dados (opcional).

---

## Como Funciona

1. O usuário fornece uma base de dados com informações sobre assinaturas e cancelamentos.
2. O script lê os dados e realiza a análise estatística.
3. O programa gera gráficos e relatórios indicando os motivos de cancelamento e possíveis soluções.

---

## Exemplo de Código

```python
import pandas as pd

# Leitura da base de dados
dados = pd.read_csv("cancelamentos.csv")

# Contagem de cancelamentos por motivo
cancelamentos_motivo = dados['motivo_cancelamento'].value_counts()
print("Cancelamentos por motivo:")
print(cancelamentos_motivo)

# Sugestão de soluções (exemplo simples)
for motivo in cancelamentos_motivo.index:
    if motivo.lower() == "preço":
        print(f"Sugestão para {motivo}: Avaliar promoções ou planos mais acessíveis")
    elif motivo.lower() == "atendimento":
        print(f"Sugestão para {motivo}: Melhorar suporte e comunicação com clientes")
    else:
        print(f"Sugestão para {motivo}: Investigar mais a fundo")
