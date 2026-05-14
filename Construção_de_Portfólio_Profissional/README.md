<div align="center">

# 💼 Corporate Budget System

> Sistema robusto de orçamento corporativo com auditoria automática, filtros hierárquicos e conversão cambial em tempo real.

[![Python](https://img.shields.io/badge/Python-3.7+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Status](https://img.shields.io/badge/Status-Ativo-success?style=for-the-badge)](.)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](.)

</div>

---

## 🗂️ Índice

- [Visão Geral](#-visão-geral)
- [Funcionalidades](#-funcionalidades)
- [Estrutura da Empresa](#-estrutura-da-empresa)
- [Como Usar](#-como-usar)
- [Sistema de Auditoria](#-sistema-de-auditoria)
- [API Reference](#-api-reference)
- [Requisitos](#-requisitos)
- [Autor](#-autor)

---

## 🔍 Visão Geral

Sistema desenvolvido em **Python puro** para calcular orçamentos em estruturas hierárquicas de empresas multinacionais. Ideal para cenários com múltiplas filiais, departamentos e subdepartamentos aninhados em qualquer nível de profundidade.

A arquitetura segue o **princípio de separação de responsabilidades**:

- **`_somar_recursivo`** → Lógica de travessia e soma da árvore hierárquica
- **`@auditor`** → Camada de auditoria externa, sem interferir na lógica de negócio

---

## ✨ Funcionalidades

| Feature | Descrição |
|---|---|
| 🔁 **Recursão Inteligente** | Percorre dicionários aninhados em qualquer profundidade |
| 🚫 **Filtro por Departamento** | Ignora setores inteiros via `*args` |
| 💱 **Conversão Cambial** | Converte o total para qualquer moeda via `**kwargs` |
| 🕵️ **Auditoria Automática** | Decorator `@auditor` registra inputs, outputs e tempo de execução |
| ⚡ **Alta Performance** | Processamento em microssegundos |

---

## 🏢 Estrutura da Empresa

```
Empresa
├── 🏛️ Matriz
│   ├── TI               → Infraestrutura · Desenvolvimento         R$ 760.000
│   ├── RH               → Recrutamento · Treinamento · Benefícios  R$ 185.000
│   ├── Financeiro        → Contabilidade · Auditoria · Tesouraria   R$ 335.000
│   └── Marketing         → Mídias Pagas · Conteúdo · Branding       R$ 390.000
│
├── 🏙️ Filial SP
│   ├── Operações         → Logística · Estoque                      R$ 265.000
│   ├── Vendas            → Varejo · Atacado · E-commerce            R$ 930.000
│   └── Suporte           →                                          R$  55.000
│
└── 🌊 Filial RJ
    ├── Operações         → Logística · Estoque                      R$ 210.000
    ├── Vendas            → Varejo · Atacado                         R$ 350.000
    └── Jurídico          → Contratos · Compliance                   R$ 160.000
```

> **💰 Total Geral: R$ 3.640.000,00**

---

## 🚀 Como Usar

### Instalação

```bash
# Nenhuma dependência externa — Python puro!
python orcamento_empresa.py
```

### Cenário 1 — Orçamento Total

```python
total = calcular_orcamento(empresa)
# ✅ R$ 3.640.000,00
```

### Cenário 2 — Com Filtros de Departamento

```python
# Exclui Marketing (Matriz) e Jurídico (Filial RJ)
total = calcular_orcamento(empresa, "Marketing", "Juridico")
# ✅ R$ 3.090.000,00
```

### Cenário 3 — Filtro + Conversão Cambial

```python
# Exclui Filial RJ e converte para USD
total = calcular_orcamento(
    empresa,
    "Filial_RJ",
    moeda_destino="USD",
    taxa_cambio=0.19
)
# ✅ USD 554.800,00
```

---

## 🕵️ Sistema de Auditoria

O decorator `@auditor` envolve automaticamente a função principal, gerando um relatório completo a cada execução:

```
╔══════════════════════════════════════════════════════════════╗
║          SISTEMA DE AUDITORIA — INÍCIO DO CÁLCULO           ║
╠══════════════════════════════════════════════════════════════╣
║  Função auditada          : calcular_orcamento               ║
║  Departamentos ignorados  : ('Marketing', 'Juridico')        ║
║  Parâmetros de conversão  : Nenhum                           ║
╠══════════════════════════════════════════════════════════════╣
║  [IGNORADO] Departamento 'Marketing' excluído da soma.       ║
║  [IGNORADO] Departamento 'Juridico' excluído da soma.        ║
║                                                              ║
║  Orçamento bruto (BRL)    : R$         3,090,000.00          ║
╠══════════════════════════════════════════════════════════════╣
║  Tempo de processamento   : 0.000029 segundos                ║
╚══════════════════════════════════════════════════════════════╝
          SISTEMA DE AUDITORIA — CÁLCULO ENCERRADO
```

---

## 📖 API Reference

### `calcular_orcamento(estrutura, *args, **kwargs)`

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `estrutura` | `dict` | Dicionário aninhado com os orçamentos |
| `*args` | `str` | Nomes dos departamentos a ignorar |
| `moeda_destino` | `str` | Símbolo da moeda — ex: `"USD"`, `"EUR"` |
| `taxa_cambio` | `float` | Fator de conversão (padrão: `1.0`) |

**Retorno:** `float` — total do orçamento, convertido se taxa fornecida.

---

## 🛠️ Requisitos

- Python **3.7+**
- Módulo `time` *(biblioteca padrão — sem instalação necessária)*

---

## 👤 Autor

<div align="center">

****

[![LinkedIn](https://www.linkedin.com/in/jaime-neto-5a57b2219/)
[![Gmail](Email:jaimelneto77@gmail.com)

*Desenvolvido com Python 🐍 e muito café ☕*

</div>
