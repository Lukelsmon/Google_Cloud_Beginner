<div align="center">

![Header](https://capsule-render.vercel.app/api?type=waving&color=4285F4,34A853,FBBC05,EA4335&height=200&section=header&text=Google%20Cloud%20Beginner&fontSize=48&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Aprendendo%20Google%20Cloud%20do%20zero%20🚀&descAlignY=60&descSize=18)

<br/>

[![Google Cloud](https://img.shields.io/badge/Google_Cloud-Beginner-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)](https://cloud.google.com/)
[![Status](https://img.shields.io/badge/Status-Em%20Aprendizado-34A853?style=for-the-badge&logo=bookstack&logoColor=white)](#)
[![Idioma](https://img.shields.io/badge/Idioma-Português-FBBC05?style=for-the-badge&logo=googletranslate&logoColor=white)](#)

</div>

---

## 📚 Sobre este Repositório

> Starting learning about Google Cloud in general

Este repositório documenta minha jornada de aprendizado no **Google Cloud Platform (GCP)**, com perguntas, respostas explicadas e conceitos fundamentais que encontro ao longo dos estudos.

---

## 🗂️ Índice

- [📦 Dados — Pergunta 1: Cadeia de Suprimentos](#-pergunta-1-cadeia-de-suprimentos)
- [☁️ Dados — Pergunta 2: Modelos de Implantação em Nuvem](#️-pergunta-2-modelos-de-implantação-em-nuvem)

---

## 🗄️ Dados

### ❓ Pergunta 1: Cadeia de Suprimentos

> Imagine uma empresa que precisa otimizar sua cadeia de suprimentos analisando dados históricos e prevendo padrões futuros de demanda. Eles têm dados em vários formatos de múltiplos sistemas e precisam torná-los acessíveis para analistas de negócios. **Qual abordagem do Google Cloud melhor suportaria seus objetivos de transformação de dados?**

---

### ✅ Resposta Correta

**Arquitetura de Data Lake com Cloud Storage + Dataproc + BigQuery**

```
📥 Dados Brutos  →  ☁️ Cloud Storage  →  ⚙️ Dataproc (ETL)  →  📊 BigQuery (Análise SQL)
```

Esta abordagem fornece uma solução **flexível e escalável** para diversas necessidades de dados da empresa. Veja como cada serviço contribui:

---

#### 🪣 Cloud Storage

Serve como a **base do Data Lake**, armazenando dados brutos em seu **formato nativo** sem exigir transformação na ingestão. Isso:

- ✔️ Preserva as informações originais
- ✔️ Acomoda **vários tipos de dados** de múltiplos sistemas
- ✔️ Escala automaticamente com o volume de dados

---

#### ⚙️ Dataproc

Fornece **clusters gerenciados de Hadoop e Spark** — ambientes computacionais em nuvem pré-configurados que processam grandes volumes de dados (**Big Data**). É responsável por:

- ✔️ Transformar dados brutos **em escala**
- ✔️ Lidar com operações complexas de **ETL**

> 💡 **O que é ETL?**
> **E**xtract, **T**ransform, **L**oad — processo de integração de dados que coleta informações de várias fontes, as padroniza e organiza em um repositório central (banco de dados ou data warehouse) para análise e tomada de decisões.

---

#### 📊 BigQuery

Completa a arquitetura como um **Data Warehouse** *serverless* (sem servidor), onde os dados processados podem ser analisados usando **SQL**, permitindo que analistas de negócios executem consultas complexas **sem gerenciar infraestrutura**.

> 💡 **Data Lake vs. Data Warehouse**
>
> | Característica | 🏞️ Data Lake | 🏢 Data Warehouse |
> |---|---|---|
> | Formato dos dados | Dados brutos, formato nativo | Dados estruturados e processados |
> | Flexibilidade | Alta | Média |
> | Foco | Armazenamento massivo | Análise de negócios (BI) |
> | Exemplo GCP | Cloud Storage | BigQuery |

---

### ❌ Por que as outras opções estavam erradas?

<details>
<summary><b>🔴 Cloud Spanner + Compute Engine</b></summary>

<br/>

**Cloud Spanner** é um banco de dados globalmente distribuído e altamente consistente, projetado para cargas de trabalho **transacionais** que exigem alta disponibilidade e consistência global. Porém:

- ❌ Não é otimizado para **processamento analítico** de dados históricos
- ❌ É **demasiado caro** para esse cenário

**Compute Engine** com scripts de análise personalizados exigiria que a empresa **construísse e mantivesse** sua própria infraestrutura analítica, adicionando uma **sobrecarga operacional** desnecessária.

</details>

<details>
<summary><b>🔴 Cloud SQL + App Engine</b></summary>

<br/>

**Cloud SQL** é um serviço de banco de dados relacional que:

- ❌ Teria dificuldades com a **escala e variedade** de dados de uma operação logística global
- ❌ Foi projetado somente para cargas de trabalho **transacionais**

**App Engine** para construção de um painel de análise personalizado:

- ❌ Exige um grande **esforço de desenvolvimento**
- ❌ Não forneceria a **flexibilidade analítica** que os analistas de negócios precisam para explorar dados e descobrir novos padrões

</details>

---

### ❓ Pergunta 2: Modelos de Implantação em Nuvem

> Uma empresa de serviços financeiros está avaliando modelos de implantação em nuvem para sua iniciativa de transformação digital. Eles precisam manter controle rigoroso sobre certos dados regulamentados enquanto aproveitam as capacidades da nuvem para análises e aplicações voltadas para o cliente. **Qual modelo de implantação em nuvem melhor atende a esses requisitos?**

As opções debatidas foram:

| Opção | Descrição |
|---|---|
| ☁️ Nuvem Pública | Infraestrutura compartilhada gerenciada por um provedor (ex: GCP) |
| 🏢 Nuvem Privada | Infraestrutura dedicada exclusivamente a uma organização |
| 🌐 **Nuvem Híbrida** | **Combinação de nuvem pública + infraestrutura privada** |
| 🏘️ Nuvem Comunitária | Compartilhada por organizações com interesses comuns |

---

### ✅ Resposta Correta

**☁️🔀🏢 Nuvem Híbrida**

A **Nuvem Híbrida** combina serviços de nuvem pública com infraestrutura privada, permitindo que as cargas de trabalho se movam entre os dois ambientes conforme as **necessidades e os custos mudam**.

```
┌─────────────────────────────────────────────────────────┐
│                    NUVEM HÍBRIDA                        │
│                                                         │
│  🏢 Ambiente Privado         ☁️ Nuvem Pública (GCP)     │
│  ┌───────────────────┐      ┌───────────────────────┐   │
│  │ Dados Regulados   │ ←──→ │ IA/ML, Analytics      │   │
│  │ Alta Conformidade │      │ Apps ao Cliente       │   │
│  └───────────────────┘      └───────────────────────┘   │
│              ↑ Gerenciado pelo Anthos ↑                 │
└─────────────────────────────────────────────────────────┘
```

É ideal para **empresas financeiras** pois:

- ✔️ Mantém dados regulamentados sensíveis no **ambiente privado** com controle rigoroso de segurança e conformidade
- ✔️ Aproveita o poder do Google Cloud para **análises e aplicações** voltadas ao cliente
- ✔️ Escala conforme as necessidades mudam

> 🔧 **Google Cloud Anthos**
> Exemplo de solução híbrida do Google Cloud. O **Anthos** fornece uma plataforma e ferramentas consistentes em ambientes, permitindo **portabilidade de aplicações** e **gerenciamento unificado** — seja no local, em outra nuvem ou no GCP.

---

### ❌ Por que a Nuvem Privada estava errada?

<details>
<summary><b>🔴 Nuvem Privada</b></summary>

<br/>

Embora pareça uma boa opção para dados sensíveis, a Nuvem Privada:

- ❌ **Não poderia aproveitar** todas as capacidades do Google Cloud para análises e aplicações voltadas ao cliente
- ❌ **Limitaria a capacidade** da empresa de escalar rapidamente
- ❌ Impede o acesso a serviços avançados como **IA/ML** (Inteligência Artificial / Machine Learning)

> 📝 **Nota:** Dependendo de como cada empresa deseja implantar e contribuir com seus processos, várias utilizam o modelo privado do Google Cloud. Porém, para o cenário descrito — com **requisito duplo** de controle rigoroso e capacidades de nuvem — a solução híbrida é superior.

</details>

---

<div align="center">

![Footer](https://capsule-render.vercel.app/api?type=waving&color=4285F4,34A853,FBBC05,EA4335&height=120&section=footer&animation=fadeIn)

**Feito com ☁️ e muito aprendizado**

[![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=flat-square&logo=google-cloud&logoColor=white)](https://cloud.google.com/)
[![BigQuery](https://img.shields.io/badge/BigQuery-4285F4?style=flat-square&logo=googlebigquery&logoColor=white)](https://cloud.google.com/bigquery)
[![Cloud Storage](https://img.shields.io/badge/Cloud_Storage-FBBC05?style=flat-square&logo=googlecloud&logoColor=white)](https://cloud.google.com/storage)
[![Dataproc](https://img.shields.io/badge/Dataproc-34A853?style=flat-square&logo=googlecloud&logoColor=white)](https://cloud.google.com/dataproc)

</div>
