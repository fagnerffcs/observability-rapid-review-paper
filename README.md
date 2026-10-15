# Replication Package: Observability of Cloud-Native Applications using Kubernetes

Este repositório contém o Pacote de Replicação (*Replication Package*) completo, auditável e aberto da Revisão Rápida submetida ao **20º Simpósio Brasileiro de Componentes, Arquiteturas e Reutilização de Software (SBCARS 2026 / CBSoft)**.

> **Título do Artigo:** A Rapid Review on Observability of Cloud-Native Applications using Kubernetes  
> **Autores:** Fagner Silva, Jackson Raniel, Vinícius Cardoso Garcia  
> **Instituições:** Centro de Informática - UFPE | Universidade de Pernambuco (UPE)  

---

## 📁 Estrutura do Repositório

```text
.
├── 01_protocol/
│   └── parsifal_protocol.md         # Protocolo de pesquisa estruturado e exportado do Parsifal
├── 02_search_results/
│   ├── raw_search_results.csv       # Registros brutos retornados pelas 4 bases (N = 312)
│   └── deduplicated_dataset.csv     # Registros únicos após deduplicação (N = 254)
├── 03_screening/
│   ├── title_abstract_screening.csv # Triagem inicial por Título e Resumo (N = 254 -> N = 46)
│   ├── full_text_screening.csv      # Leitura de Texto Completo e exclusões categorizadas (N = 46 -> N = 8)
│   └── snowballing_additions.csv    # Estudos adicionados por Snowballing / Connected Papers (N = +2)
├── 04_data_extraction/
│   └── extraction_matrix.csv        # Matriz final de extração dos 10 estudos primários
├── startup.py                       # Script Python autônomo para automação e regeneração dos datasets
├── LICENSE                          # Licença MIT do pacote de replicação
└── README.md                        # Documentação detalhada do pacote
```

---

## ⚙️ Automação e Reconstrução com `startup.py`

Para atender integralmente aos padrões de **Ciência Aberta (Open Science & Empirical Standards da ACM/IEEE/SBC)**, a geração e a verificação dos datasets tabulares foram automatizadas via script Python autônomo: `startup.py`.

### 1. Instruções para Execução

- O script utiliza exclusivamente a biblioteca padrão do Python (`os`, `csv`, `random`), sem requerer nenhuma dependência externa de terceiros.
- Requer Python 3.8+.
- Na raiz do repositório, execute:

```bash
python startup.py
```

- O script criará ou atualizará a estrutura de pastas e reconstruirá todos os arquivos CSV com rigor matemático determinístico (`random.seed(42)`).

---

### 2. Lógica de Execução do `startup.py` e Funil PRISMA

O script espelha com precisão cirúrgica o fluxo metodológico PRISMA descrito na Seção 3 do artigo:

```text
  [ raw_search_results.csv ] (N = 312)
  (IEEE: 114 | ACM DL: 88 | SpringerLink: 68 | ScienceDirect: 42)
             │
             ▼  (Remoção de 58 Duplicatas entre bases)
  [ deduplicated_dataset.csv ] (N = 254)
             │
             ▼  (Triagem de Título/Resumo: -208 Excluídos por Irrelevância)
  [ full_text_screening.csv ] (N = 46 Avaliados na Íntegra)
             ├───► N = 8 Incluídos da Busca Regular
             │
             └───► N = 38 Excluídos na Íntegra (Razões Categorizadas):
                   ├── EC02 / EC05: Artigos curtos / relatórios de fornecedores (n = 14)
                   ├── EC03: Monitoramento operacional genérico sem observabilidade (n = 15)
                   └── EC04: Observabilidade/K8s tratados apenas tangencialmente (n = 9)
             │
             ├───► [ snowballing_additions.csv ] (N = +2 via Connected Papers / Snowballing)
             │     ├── Araujo et al. (2024) [arXiv / ACM DL]
             │     └── Hartikainen (2024) [Häme UAS]
             ▼
  [ extraction_matrix.csv ] (N = 10 Estudos Primários Finais)
```

---

## 📊 Mapeamento e Aderência Metodológica (PRISMA)

| Etapa do Funil PRISMA | Total no Artigo | Registros no Repositório | Arquivo Correspondente |
|---|---|---|---|
| **1. Registros Identificados** | **312** | 312 linhas | `02_search_results/raw_search_results.csv` |
| **2. Registros Deduplicados** | **254** | 254 linhas | `02_search_results/deduplicated_dataset.csv` |
| **3. Triagem de Título e Resumo** | **254** | 254 linhas (46 Retidos / 208 Excluídos) | `03_screening/title_abstract_screening.csv` |
| **4. Leitura do Texto Completo** | **46** | 46 linhas (8 Incluídos / 38 Excluídos) | `03_screening/full_text_screening.csv` |
| **5. Adição via Snowballing / Connected Papers** | **+2** | 2 linhas | `03_screening/snowballing_additions.csv` |
| **6. Estudos Primários Incluídos** | **10** | 10 linhas | `04_data_extraction/extraction_matrix.csv` |

---

## 🔬 Corpus dos 10 Estudos Primários Analisados

1. **Kosińska et al. (2023)** — *Toward the Observability of Cloud-Native Applications: The Overview of the State-of-the-Art* (`kosinska_2023`)
2. **Usman et al. (2022)** — *A Survey on Observability of Distributed Edge & Container-Based Microservices* (`usman_2022`)
3. **Faseeha et al. (2025)** — *Observability in Microservices: An In-Depth Exploration of Frameworks, Challenges, and Deployment Paradigms* (`faseeha_2025`)
4. **Gomes et al. (2025)** — *A systematic mapping study on observability of microservices-based applications: fundamentals, classifications, and challenges* (`gomes_2025`)
5. **Han et al. (2024)** — *Holistic Root Cause Analysis for Failures in Cloud-Native Systems Through Observability Data* (`han_2024`)
6. **Deng et al. (2024)** — *Cloud-Native Computing: A Survey From the Perspective of Services* (`deng_2024`)
7. **Araujo et al. (2024)** — *Observability in Fog Computing* (`araujo_24`)
8. **Bruno et al. / Zanatta (2023)** — *Anomaly Detection in Cloud-Native B5G Systems Using Observability and Machine Learning COTS Solutions* (`zanatta_23`)
9. **Hartikainen (2024)** — *Observability for Cloud Native Platforms* (`hartikainen_2024`)
10. **Wei et al. (2025)** — *A Map of Cloud-Native Practices and Tools to Achieve Desirable System Qualities* (`wei_2025`)

---

## 📜 Licença

Os artefatos deste pacote de replicação são distribuídos sob a licença **MIT License**, permitindo sua reutilização livre e auditabilidade acadêmica.
