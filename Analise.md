# Conhecimento em LLMs, Arquiteturas de IA, Ciência e Engenharia de Dados — Portfólio Científico

Base de conhecimento verificável sobre como sistemas de IA devem **adquirir, representar, atualizar, recuperar, combinar e usar conhecimento** sem perder confiabilidade, generalização, eficiência e rastreabilidade.

Consolidação realiza por Jean Michael Estevez Alvarez.

**Versão:** v0 · **Data de consulta das fontes:** 10/10/2026 · **Trabalhos catalogados:** 265 (todos com identificador conferido na fonte oficial)

---

## Sumário

1. [Estado das fases](#estado-das-fases)
2. [Como os dados foram verificados](#como-os-dados-foram-verificados)
3. [Artigos-semente](#artigos-semente)
4. [Principais conclusões](#principais-conclusões)
5. [Estrutura do repositório](#estrutura-do-repositório)
6. [Como atualizar](#como-atualizar)
7. [Catálogo bibliográfico comentado](#catalogo)

---

## Estado das fases

| Fase | Situação | O que foi feito | O que falta |
|---|---|---|---|
| 1. Delimitação | ✅ Concluída (v0) | 7 perguntas de pesquisa, taxonomia, critérios de inclusão/exclusão e de qualidade — [protocolo](portfolio/00_protocolo.md) | Pré-registro |
| 2. Mapeamento | 🟡 Parcial | Curadoria por eixo + backward snowballing dos semente + **forward snowballing** (652 citantes analisados) | Busca booleana reproduzível em Scopus, IEEE Xplore, ACM DL e OpenAlex |
| 3. Seleção | 🟡 Parcial | 265 trabalhos incluídos, duplicatas removidas, classificação por eixo, tipo e status editorial | Segundo revisor; avaliação de qualidade 1–3 para todos |
| 4. Análise crítica | 🟡 Parcial | **2 fichas completas** (leitura integral); 263 fichas curtas (resumo e resultado) | Fichas completas para os ~20 trabalhos centrais |
| 5. Síntese | 🟡 v0 | [5 matrizes comparativas](portfolio/02_matrizes.md), [mapa de evolução, 10 controvérsias e respostas às 10 perguntas](portfolio/03_sintese_evolucao_controversias.md) | Revisão após as novas fichas |
| 6. Aplicação | 🟡 v0 | [Guia de decisões com 10 padrões e 9 cenários](portfolio/04_guia_arquitetural.md); [6 experimentos planejados](portfolio/05_laboratorio.md) | Executar os experimentos |
| 7. Atualização | ✅ Protocolo definido | [Periodicidade, passos, regra de revisão e histórico](portfolio/06_agenda_e_atualizacao.md) | Primeira rodada trimestral |

## Como os dados foram verificados

Nenhuma referência foi transcrita de memória. Cada entrada do catálogo foi conferida por API na fonte oficial em 10/10/2026:

| Tipo de trabalho | Fonte de verificação | Campos |
|---|---|---|
| 226 com arXiv | [arXiv API](https://info.arxiv.org/help/api/index.html) | Título, autores, data da v1, data e número da última versão, resumo, comentário dos autores |
| Venue e DOI dos anteriores | [Semantic Scholar API](https://api.semanticscholar.org/) + comentário/journal_ref do arXiv + conferência manual quando divergentes | Veículo, DOI, contagem de citações |
| 30 sem arXiv (e os DOIs dos 2 semente) | [Crossref API](https://api.crossref.org/) | Título, autores, data, veículo, DOI |
| 9 clássicos sem DOI nem arXiv | Semantic Scholar (busca por título) + [DBLP](https://dblp.org/) | Título, autores, ano, veículo |

**Limites que o leitor deve conhecer**

- **Resumo** e **Resultado** de cada entrada são **sínteses próprias em português**, escritas a partir do resumo oficial e dos metadados; os resumos originais não são reproduzidos. Apenas os dois artigos-semente foram lidos na íntegra. Números citados nas fichas curtas são os informados pelos próprios autores.
- **Status editorial:** *Revisado por pares* (conferência ou periódico), *Workshop* ou *Preprint*. Preprints não têm o mesmo peso de evidência e estão sinalizados.
- Dois veículos (Kafka 2011, DiskANN 2019) não puderam ser confirmados automaticamente e estão marcados.
- A contagem de citações (no CSV) é contexto, não critério de qualidade.
- Links de código aparecem quando os autores os informam no resumo ou no comentário do arXiv; ausência de link não significa que o código não exista.

## Artigos-semente

### Fine-Tuning or Retrieval? Comparing Knowledge Injection in LLMs
**Oded Ovadia, Meni (Menachem) Brief, Moshik Mishaeli, Oren Elisha** — Microsoft Israel
EMNLP 2024 (main), pp. 237–250 · arXiv v1: 10/12/2023, v3: 30/01/2024 · [arXiv:2312.05934](https://arxiv.org/abs/2312.05934) · [DOI 10.18653/v1/2024.emnlp-main.15](https://doi.org/10.18653/v1/2024.emnlp-main.15) · [PDF local](RAG_ou_Fine_2024.emnlp-main.15.pdf) · [ficha completa](portfolio/fichamentos/F01_ovadia_2024_finetuning_ou_retrieval.md)

- **Resumo:** compara fine-tuning não supervisionado e RAG em três modelos de 7B (Llama2, Mistral, Orca2), em cinco tarefas de conhecimento do MMLU e em 910 perguntas novas sobre eventos de ago–nov/2023, posteriores ao corte de treino.
- **Resultado:** RAG venceu em conhecimento já visto e novo. Em eventos atuais, o Mistral foi de 0,481 (base) para 0,875 com RAG e 0,504 com FT; FT com 10 paráfrases por trecho chegou a 0,588. FT + RAG não superou RAG de forma consistente.
- **Cautelas:** só FT não supervisionado; perguntas geradas a partir dos mesmos trechos indexados (favorece RAG); sem testes estatísticos; código e dados não publicados.

### Does Fine-Tuning LLMs on New Knowledge Encourage Hallucinations?
**Zorik Gekhman, Gal Yona, Roee Aharoni, Matan Eyal, Amir Feder, Roi Reichart, Jonathan Herzig** — Technion e Google Research
EMNLP 2024 (main), pp. 7765–7784 · arXiv v1: 09/05/2024, v3: 01/10/2024 · [arXiv:2405.05904](https://arxiv.org/abs/2405.05904) · [DOI 10.18653/v1/2024.emnlp-main.444](https://doi.org/10.18653/v1/2024.emnlp-main.444) · [PDF local](Alucinacao_FineTunning2024.emnlp-main.444.pdf) · [ficha completa](portfolio/fichamentos/F02_gekhman_2024_finetuning_e_alucinacao.md)

- **Resumo:** estudo controlado em QA fechado (PaLM 2-S, EntityQuestions) que varia a fração de exemplos de SFT com fatos desconhecidos pelo modelo, classificados pelo método SliCK.
- **Resultado:** exemplos desconhecidos são aprendidos bem mais devagar; quando ajustados, a acurácia cai linearmente (β_unk = −8,3, R² = 0,86; fora da distribuição R² = 0,95). Early stopping ou filtragem evita a perda; treinar com exemplos *MaybeKnown* deu o melhor resultado (43,6).
- **Cautelas:** um único modelo, fechado; respostas curtas; queda de acurácia como proxy de alucinação; confirmado depois com Llama-2 e Mistral por outros grupos.

## Principais conclusões

Detalhes, níveis de evidência e referências em [síntese](portfolio/03_sintese_evolucao_controversias.md) e [matrizes](portfolio/02_matrizes.md).

| Conclusão | Evidência |
|---|---|
| Memória paramétrica é fraca para fatos raros e para fatos novos introduzidos por fine-tuning simples | Consolidada |
| Fatos desconhecidos no SFT aumentam erros sobre o conhecimento prévio (em QA curto) | Consolidada |
| RAG é o padrão mais seguro para fatos novos e voláteis; fine-tuning com dados bem desenhados (QA, paráfrases, sintéticos) compete | Controversa |
| Editar pesos não propaga consequências lógicas dos fatos | Consolidada |
| BM25 continua baseline forte fora do domínio; reranking melhora o topo; nenhum embedding vence em todas as tarefas | Consolidada |
| Sistemas multiagentes não mostram vantagem robusta sobre agente único quando custo e baselines são controlados | Controversa |
| Contexto longo supera RAG em média com recursos suficientes, mas custa muito mais | Limitada |

**Recomendação de engenharia (não é conclusão científica):** manter fatos voláteis e auditáveis em recuperação versionada; usar treino para formato, tarefa e uso do contexto; exigir baseline simples, intervalos de confiança e custo antes de adotar arquiteturas mais complexas.

## Estrutura do repositório

```
Artigos/
├── README.md                      ← lista resumida «Papers & Codes» (gerada)
├── Analise.md                     ← este arquivo: análise e catálogo comentado (gerado)
├── *.pdf                          ← artigos-semente (ACL Anthology)
├── portfolio/
│   ├── 00_protocolo.md            ← Fase 1: perguntas, taxonomia, critérios, registro da busca
│   ├── fichamentos/               ← Fase 4: fichas completas
│   ├── 02_matrizes.md             ← Fase 5: matrizes comparativas
│   ├── 03_sintese_evolucao_controversias.md
│   ├── 04_guia_arquitetural.md    ← Fase 6: padrões e cenários
│   ├── 05_laboratorio.md          ← experimentos planejados
│   └── 06_agenda_e_atualizacao.md ← agenda, roadmap, Fase 7 e histórico
├── dados/
│   ├── catalogo.csv / catalogo.json   ← catálogo estruturado (autores completos, citações)
│   └── cache/                         ← respostas brutas das APIs usadas na verificação
└── ferramentas/
    ├── arxiv_ids.txt, dois.txt    ← lista curada com eixo de cada trabalho
    ├── fetch.py, s2.py, crossref.py, s2match.py, citations.py
    ├── sumarios_a.py, _b.py, _c.py ← sínteses próprias por eixo
    ├── gerar_catalogo.py          ← gera CSV, JSON e o catálogo desta análise
    └── gerar_readme.py            ← gera o README.md a partir do catálogo
```

## Como atualizar

A partir da pasta `Artigos/`:

```bash
python -I ferramentas/fetch.py ferramentas/arxiv_ids.txt dados/cache/arxiv.json
```

```bash
python -I ferramentas/s2.py dados/cache/arxiv.json dados/cache/s2.json
```

```bash
python -I ferramentas/crossref.py ferramentas/dois.txt dados/cache/crossref.json
```

```bash
python -I ferramentas/gerar_catalogo.py
```

```bash
python -I ferramentas/gerar_readme.py
```

`fetch.py` aponta qualquer ID cujo título não bate com o esperado. Para incluir um trabalho: acrescente `id|fragmento do título|eixo` ao arquivo de IDs e a síntese em `sumarios_*.py`.

---

<a id="catalogo"></a>

## Catálogo bibliográfico comentado

Cada entrada traz: título, ano, tipo, autores (até 6; lista completa no CSV), datas, status editorial e veículo, links (arXiv, DOI, código quando informado), resumo e resultado principal. Dentro de cada eixo, os artigos-semente vêm primeiro e os demais em ordem cronológica.

<!-- CATALOGO:INICIO -->
Total: **265 trabalhos**, metadados conferidos em 2026-10-10.

| Eixo | Revisados por pares | Workshop | Preprint | Venue não confirmado | Total |
|---|---:|---:|---:|---:|---:|
| [Aquisição, atualização e representação de conhecimento](#a) | 51 | 1 | 11 | 0 | 63 |
| [Confiabilidade, alucinações e avaliação](#b) | 37 | 1 | 5 | 0 | 43 |
| [Arquiteturas modernas de sistemas de IA](#c) | 20 | 0 | 8 | 0 | 28 |
| [Recuperação de informação e bases de conhecimento](#d) | 29 | 1 | 5 | 1 | 36 |
| [Ciência de Dados, experimentação e otimização](#e) | 44 | 0 | 5 | 0 | 49 |
| [Engenharia de Dados para sistemas de IA](#f) | 17 | 0 | 1 | 1 | 19 |
| [MLOps, LLMOps e operação em produção](#g) | 25 | 1 | 1 | 0 | 27 |

<a id="a"></a>

### Eixo A — Aquisição, atualização e representação de conhecimento

- **Fine-Tuning or Retrieval? Comparing Knowledge Injection in LLMs** (2023) — *Artigo-semente*  
  Oded Ovadia, Menachem Brief, Moshik Mishaeli, Oren Elisha  
  arXiv v1: 2023-12-10 · última versão (v3): 2024-01-30 · **Revisado por pares**: EMNLP 2024 (main), pp. 237–250 · [arXiv:2312.05934](https://arxiv.org/abs/2312.05934) · [DOI 10.18653/v1/2024.emnlp-main.15](https://doi.org/10.18653/v1/2024.emnlp-main.15)  
  **Resumo:** Compara fine-tuning não supervisionado (continued pretraining) e RAG para injetar conhecimento em LLMs de 7B (Llama2, Mistral, Orca2), em tarefas de conhecimento do MMLU e num conjunto novo de 910 perguntas sobre eventos dos EUA de ago–nov/2023, posteriores ao corte de treino.  
  **Resultado:** RAG superou o fine-tuning tanto para conhecimento já visto quanto para conhecimento novo (eventos atuais: Mistral 0,481 base → 0,875 com RAG vs 0,504 com FT). Combinar FT+RAG não foi consistentemente melhor que RAG. Repetir o fato em várias paráfrases melhorou o FT de forma monotônica.

- **Does Fine-Tuning LLMs on New Knowledge Encourage Hallucinations?** (2024) — *Artigo-semente*  
  Zorik Gekhman, Gal Yona, Roee Aharoni, Matan Eyal, Amir Feder, Roi Reichart et al. (7 autores)  
  arXiv v1: 2024-05-09 · última versão (v3): 2024-10-01 · **Revisado por pares**: EMNLP 2024 (main), pp. 7765–7784 · [arXiv:2405.05904](https://arxiv.org/abs/2405.05904) · [DOI 10.18653/v1/2024.emnlp-main.444](https://doi.org/10.18653/v1/2024.emnlp-main.444)  
  **Resumo:** Estudo controlado em QA fechado (EntityQuestions, PaLM 2-S) que varia a proporção de exemplos de fine-tuning com fatos desconhecidos pelo modelo, classificados pelo método SliCK (HighlyKnown, MaybeKnown, WeaklyKnown, Unknown).  
  **Resultado:** Exemplos Unknown são aprendidos bem mais devagar; quando finalmente ajustados, a acurácia de teste cai linearmente (regressão com R² = 0,86; 0,95 fora da distribuição). Early stopping ou filtrar Unknown evita a perda; reetiquetar Unknown como «não sei» manteve 61,8% de acurácia nas perguntas respondidas.

- **Distilling the Knowledge in a Neural Network** (2015) — *Fundacional*  
  Geoffrey Hinton, Oriol Vinyals, Jeff Dean  
  arXiv v1: 2015-03-09 · **Workshop**: NIPS 2014 Deep Learning Workshop · [arXiv:1503.02531](https://arxiv.org/abs/1503.02531)  
  **Resumo:** Destilação de conhecimento: treina um modelo menor para imitar as probabilidades suavizadas de um ensemble maior.  
  **Resultado:** Resultados fortes em MNIST e num sistema acústico comercial; base de toda a destilação moderna. Publicado em workshop.

- **Overcoming catastrophic forgetting in neural networks** (2016) — *Fundacional*  
  James Kirkpatrick, Razvan Pascanu, Neil Rabinowitz, Joel Veness, Guillaume Desjardins, Andrei A. Rusu et al. (14 autores)  
  arXiv v1: 2016-12-02 · última versão (v2): 2017-01-25 · **Revisado por pares**: Proceedings of the National Academy of Sciences of the United States of America · [arXiv:1612.00796](https://arxiv.org/abs/1612.00796) · [DOI 10.1073/pnas.1611835114](https://doi.org/10.1073/pnas.1611835114)  
  **Resumo:** Elastic Weight Consolidation (EWC): desacelera o aprendizado nos pesos importantes para tarefas anteriores.  
  **Resultado:** Permite aprender tarefas sequenciais (MNIST, jogos de Atari) sem esquecimento catastrófico.

- **REALM: Retrieval-Augmented Language Model Pre-Training** (2020) — *Fundacional*  
  Kelvin Guu, Kenton Lee, Zora Tung, Panupong Pasupat, Ming-Wei Chang  
  arXiv v1: 2020-02-10 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2002.08909](https://arxiv.org/abs/2002.08909)  
  **Resumo:** REALM integra um recuperador latente ao pré-treino de linguagem mascarada, aprendido sem supervisão por retropropagação através da etapa de recuperação sobre milhões de documentos.  
  **Resultado:** Em três benchmarks de QA aberto, superou métodos anteriores por 4 a 16 pontos absolutos de acurácia, com ganhos de modularidade e interpretabilidade.

- **Don't Stop Pretraining: Adapt Language Models to Domains and Tasks** (2020) — *Fundacional*  
  Suchin Gururangan, Ana Marasović, Swabha Swayamdipta, Kyle Lo, Iz Beltagy, Doug Downey et al. (7 autores)  
  arXiv v1: 2020-04-23 · última versão (v3): 2020-05-05 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2004.10964](https://arxiv.org/abs/2004.10964) · [DOI 10.18653/v1/2020.acl-main.740](https://doi.org/10.18653/v1/2020.acl-main.740)  
  **Resumo:** Avalia pré-treino adaptativo ao domínio (DAPT) e à tarefa (TAPT) em quatro domínios e oito tarefas de classificação.  
  **Resultado:** Uma segunda fase de pré-treino no domínio traz ganhos em cenários com muitos e poucos recursos, e TAPT soma ganhos mesmo após DAPT.

- **Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks** (2020) — *Fundacional*  
  Patrick Lewis, Ethan Perez, Aleksandra Piktus, Fabio Petroni, Vladimir Karpukhin, Naman Goyal et al. (12 autores)  
  arXiv v1: 2020-05-22 · última versão (v4): 2021-04-12 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2005.11401](https://arxiv.org/abs/2005.11401)  
  **Resumo:** Define RAG: um gerador seq2seq pré-treinado (memória paramétrica) combinado a um índice denso da Wikipédia acessado por um recuperador neural (memória não paramétrica), treinados de ponta a ponta, em duas variantes (mesmos trechos para toda a sequência ou por token).  
  **Resultado:** Estado da arte em três tarefas de QA de domínio aberto na época; gerações mais específicas, diversas e factuais que um baseline apenas paramétrico. Introduz a ideia de atualizar conhecimento trocando o índice.

- **Leveraging Passage Retrieval with Generative Models for Open Domain Question Answering** (2020) — *Fundacional*  
  Gautier Izacard, Edouard Grave  
  arXiv v1: 2020-07-02 · última versão (v2): 2021-02-03 · **Revisado por pares**: Conference of the European Chapter of the Association for Computational Linguistics · [arXiv:2007.01282](https://arxiv.org/abs/2007.01282) · [DOI 10.18653/v1/2021.eacl-main.74](https://doi.org/10.18653/v1/2021.eacl-main.74)  
  **Resumo:** Fusion-in-Decoder (FiD): um modelo generativo que recebe vários trechos recuperados, codificados separadamente e combinados no decodificador.  
  **Resultado:** Estado da arte em Natural Questions e TriviaQA; o desempenho cresce com o número de trechos recuperados, indicando boa agregação de evidências.

- **LoRA: Low-Rank Adaptation of Large Language Models** (2021) — *Fundacional*  
  Edward J. Hu, Yelong Shen, Phillip Wallis, Zeyuan Allen-Zhu, Yuanzhi Li, Shean Wang et al. (8 autores)  
  arXiv v1: 2021-06-17 · última versão (v2): 2021-10-16 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2106.09685](https://arxiv.org/abs/2106.09685) · [código](https://github.com/microsoft/LoRA)  
  **Resumo:** LoRA congela os pesos e treina matrizes de decomposição de baixo posto em cada camada do Transformer.  
  **Resultado:** Reduz parâmetros treináveis em até 10.000 vezes e memória de GPU em 3 vezes em relação ao FT completo do GPT-3 175B, com qualidade igual ou superior e sem latência extra na inferência.

- **Improving language models by retrieving from trillions of tokens** (2021) — *Fundacional*  
  Sebastian Borgeaud, Arthur Mensch, Jordan Hoffmann, Trevor Cai, Eliza Rutherford, Katie Millican et al. (28 autores)  
  arXiv v1: 2021-12-08 · última versão (v3): 2022-02-07 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2112.04426](https://arxiv.org/abs/2112.04426)  
  **Resumo:** RETRO condiciona um modelo autorregressivo em trechos recuperados de um banco de 2 trilhões de tokens via atenção cruzada em blocos e recuperador BERT congelado.  
  **Resultado:** Desempenho comparável a GPT-3 e Jurassic-1 no Pile com 25 vezes menos parâmetros; mostra que memória explícita escala como alternativa a mais parâmetros.

- **Locating and Editing Factual Associations in GPT** (2022) — *Fundacional*  
  Kevin Meng, David Bau, Alex Andonian, Yonatan Belinkov  
  arXiv v1: 2022-02-10 · última versão (v5): 2023-01-13 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2202.05262](https://arxiv.org/abs/2202.05262) · [DOI 10.52202/068431-1262](https://doi.org/10.52202/068431-1262)  
  **Resumo:** Localiza associações factuais em módulos feed-forward de camadas intermediárias por intervenção causal e propõe ROME (edição de posto um).  
  **Resultado:** Edição eficaz no zsRE e, num novo conjunto de afirmações contrafactuais, mantém especificidade e generalização ao mesmo tempo, ao contrário de métodos anteriores.

- **Model soups: averaging weights of multiple fine-tuned models improves accuracy without increasing inference time** (2022) — *Fundacional*  
  Mitchell Wortsman, Gabriel Ilharco, Samir Yitzhak Gadre, Rebecca Roelofs, Raphael Gontijo-Lopes, Ari S. Morcos et al. (11 autores)  
  arXiv v1: 2022-03-10 · última versão (v3): 2022-07-01 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2203.05482](https://arxiv.org/abs/2203.05482) · [código](https://github.com/mlfoundations/model-soups)  
  **Resumo:** Model soups: média dos pesos de vários modelos ajustados com hiperparâmetros diferentes.  
  **Resultado:** Melhora acurácia e robustez sem custo de inferência adicional; ViT-G atingiu 90,94% top-1 no ImageNet.

- **Atlas: Few-shot Learning with Retrieval Augmented Language Models** (2022) — *Fundacional*  
  Gautier Izacard, Patrick Lewis, Maria Lomeli, Lucas Hosseini, Fabio Petroni, Timo Schick et al. (10 autores)  
  arXiv v1: 2022-08-05 · última versão (v3): 2022-11-16 · **Revisado por pares**: Journal of machine learning research · [arXiv:2208.03299](https://arxiv.org/abs/2208.03299)  
  **Resumo:** Atlas: modelo de linguagem com recuperação, pré-treinado de forma conjunta, avaliado em regime de poucos exemplos (MMLU, KILT, NaturalQuestions), com estudo do conteúdo e da atualização do índice.  
  **Resultado:** Mais de 42% em Natural Questions com 64 exemplos, superando um modelo de 540B por 3 pontos com 50 vezes menos parâmetros; o índice pode ser atualizado sem retreino.

- **Mass-Editing Memory in a Transformer** (2022) — *Método*  
  Kevin Meng, Arnab Sen Sharma, Alex Andonian, Yonatan Belinkov, David Bau  
  arXiv v1: 2022-10-13 · última versão (v2): 2023-08-01 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2210.07229](https://arxiv.org/abs/2210.07229)  
  **Resumo:** MEMIT estende a edição direta de pesos para milhares de associações simultâneas.  
  **Resultado:** Escala a milhares de edições em GPT-J (6B) e GPT-NeoX (20B), ordens de grandeza acima de trabalhos anteriores.

- **Large Language Models Struggle to Learn Long-Tail Knowledge** (2022) — *Estudo empírico*  
  Nikhil Kandpal, Haikang Deng, Adam Roberts, Eric Wallace, Colin Raffel  
  arXiv v1: 2022-11-15 · última versão (v2): 2023-07-27 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2211.08411](https://arxiv.org/abs/2211.08411)  
  **Resumo:** Relaciona a capacidade de responder perguntas factuais ao número de documentos de pré-treino ligados às entidades da pergunta.  
  **Resultado:** Relação correlacional e causal forte entre acurácia e contagem de documentos; modelos precisariam crescer ordens de grandeza para cobrir a cauda longa, e recuperação reduz essa dependência.

- **Editing Models with Task Arithmetic** (2022) — *Fundacional*  
  Gabriel Ilharco, Marco Tulio Ribeiro, Mitchell Wortsman, Suchin Gururangan, Ludwig Schmidt, Hannaneh Hajishirzi et al. (7 autores)  
  arXiv v1: 2022-12-08 · última versão (v3): 2023-03-31 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2212.04089](https://arxiv.org/abs/2212.04089)  
  **Resumo:** Task arithmetic: vetores de tarefa (diferença entre pesos ajustados e pré-treinados) podem ser somados ou negados para controlar o comportamento do modelo.  
  **Resultado:** Negar um vetor reduz a tarefa-alvo com pouca mudança nas demais; somar melhora várias tarefas; analogias entre tarefas funcionam sem dados da tarefa-alvo.

- **When Not to Trust Language Models: Investigating Effectiveness of Parametric and Non-Parametric Memories** (2022) — *Estudo empírico*  
  Alex Mallen, Akari Asai, Victor Zhong, Rajarshi Das, Daniel Khashabi, Hannaneh Hajishirzi  
  arXiv v1: 2022-12-20 · última versão (v4): 2023-07-02 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2212.10511](https://arxiv.org/abs/2212.10511) · [DOI 10.18653/v1/2023.acl-long.546](https://doi.org/10.18653/v1/2023.acl-long.546) · [código](https://github.com/AlexTMallen/adaptive-retrieval)  
  **Resumo:** Sondagem em larga escala de 10 modelos e 4 métodos de aumento no PopQA (14 mil perguntas, novo dataset), comparando memória paramétrica e não paramétrica por popularidade da entidade.  
  **Resultado:** LMs falham em fatos pouco populares e escalar não resolve a cauda longa; LMs com recuperação superam modelos ordens de grandeza maiores. Recuperação adaptativa (só quando necessário) melhora desempenho e reduz custo.

- **REPLUG: Retrieval-Augmented Black-Box Language Models** (2023) — *Método*  
  Weijia Shi, Sewon Min, Michihiro Yasunaga, Minjoon Seo, Rich James, Mike Lewis et al. (8 autores)  
  arXiv v1: 2023-01-30 · última versão (v4): 2023-05-24 · **Revisado por pares**: North American Chapter of the Association for Computational Linguistics · [arXiv:2301.12652](https://arxiv.org/abs/2301.12652)  
  **Resumo:** REPLUG trata o LM como caixa-preta e treina apenas o recuperador, usando o próprio LM como sinal de supervisão.  
  **Resultado:** Melhorou GPT-3 (175B) em modelagem de linguagem em 6,3% e Codex no MMLU 5-shot em 5,1%.

- **In-Context Retrieval-Augmented Language Models** (2023) — *Método*  
  Ori Ram, Yoav Levine, Itay Dalmedigos, Dor Muhlgay, Amnon Shashua, Kevin Leyton-Brown et al. (7 autores)  
  arXiv v1: 2023-01-31 · última versão (v3): 2023-08-01 · **Revisado por pares**: Transactions of the Association for Computational Linguistics · [arXiv:2302.00083](https://arxiv.org/abs/2302.00083) · [DOI 10.1162/tacl_a_00605](https://doi.org/10.1162/tacl_a_00605)  
  **Resumo:** In-Context RALM: em vez de mudar a arquitetura, apenas antepõe documentos recuperados à entrada de um LM congelado, usando recuperadores prontos.  
  **Resultado:** Ganhos grandes de modelagem de linguagem em vários tamanhos de modelo e corpora; especializar o reranking para o LM aumenta o ganho. Torna RAG viável com modelos acessados só por API.

- **LIMA: Less Is More for Alignment** (2023) — *Estudo empírico*  
  Chunting Zhou, Pengfei Liu, Puxin Xu, Srini Iyer, Jiao Sun, Yuning Mao et al. (15 autores)  
  arXiv v1: 2023-05-18 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2305.11206](https://arxiv.org/abs/2305.11206) · [DOI 10.52202/075280-2400](https://doi.org/10.52202/075280-2400)  
  **Resumo:** LIMA: LLaMa 65B ajustado com apenas mil exemplos curados, sem RLHF, para medir a importância relativa de pré-treino e alinhamento.  
  **Resultado:** Respostas equivalentes ou preferidas a GPT-4 em 43% dos casos em avaliação humana; sustenta a «hipótese do alinhamento superficial» — quase todo o conhecimento vem do pré-treino.

- **Editing Large Language Models: Problems, Methods, and Opportunities** (2023) — *Survey/revisão*  
  Yunzhi Yao, Peng Wang, Bozhong Tian, Siyuan Cheng, Zhoubo Li, Shumin Deng et al. (8 autores)  
  arXiv v1: 2023-05-22 · última versão (v3): 2023-11-30 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2305.13172](https://arxiv.org/abs/2305.13172) · [código](https://github.com/zjunlp/EasyEdit)  
  **Resumo:** Revisão e análise empírica de métodos de edição de LLMs, com novo benchmark para avaliação mais robusta.  
  **Resultado:** Aponta problemas persistentes (generalização, localidade, robustez) e fornece a ferramenta EasyEdit.

- **QLoRA: Efficient Finetuning of Quantized LLMs** (2023) — *Método*  
  Tim Dettmers, Artidoro Pagnoni, Ari Holtzman, Luke Zettlemoyer  
  arXiv v1: 2023-05-23 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2305.14314](https://arxiv.org/abs/2305.14314)  
  **Resumo:** QLoRA treina adaptadores LoRA sobre um modelo quantizado em 4 bits (NF4, dupla quantização, otimizadores paginados).  
  **Resultado:** Permite ajustar um modelo de 65B numa GPU de 48 GB preservando o desempenho do FT em 16 bits; o modelo Guanaco atingiu 99,3% do ChatGPT no benchmark Vicuna com 24 h de treino. Alerta que benchmarks de chatbot não são confiáveis.

- **MQuAKE: Assessing Knowledge Editing in Language Models via Multi-Hop Questions** (2023) — *Benchmark/dataset*  
  Zexuan Zhong, Zhengxuan Wu, Christopher D. Manning, Christopher Potts, Danqi Chen  
  arXiv v1: 2023-05-24 · última versão (v3): 2024-09-09 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2305.14795](https://arxiv.org/abs/2305.14795) · [código](https://github.com/princeton-nlp/MQuAKE)  
  **Resumo:** MQuAKE: benchmark de perguntas multi-hop que testa se uma edição propaga suas consequências lógicas.  
  **Resultado:** Editores recuperam o fato editado mas falham catastroficamente nas perguntas multi-hop; MeLLo, que guarda as edições em memória externa e usa prompting, supera os editores por larga margem.

- **TIES-Merging: Resolving Interference When Merging Models** (2023) — *Método*  
  Prateek Yadav, Derek Tam, Leshem Choshen, Colin Raffel, Mohit Bansal  
  arXiv v1: 2023-06-02 · última versão (v2): 2023-10-27 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2306.01708](https://arxiv.org/abs/2306.01708) · [DOI 10.52202/075280-0310](https://doi.org/10.52202/075280-0310) · [código](https://github.com/prateeky2806/ties-merging)  
  **Resumo:** TIES-Merging resolve interferências ao fundir modelos: zera mudanças pequenas, resolve conflitos de sinal e funde só parâmetros alinhados.  
  **Resultado:** Supera métodos de fusão anteriores em várias modalidades, domínios, números de tarefas e tamanhos de modelo.

- **Evaluating the Ripple Effects of Knowledge Editing in Language Models** (2023) — *Benchmark/dataset*  
  Roi Cohen, Eden Biran, Ori Yoran, Amir Globerson, Mor Geva  
  arXiv v1: 2023-07-24 · última versão (v2): 2023-12-20 · **Revisado por pares**: Transactions of the Association for Computational Linguistics · [arXiv:2307.12976](https://arxiv.org/abs/2307.12976) · [DOI 10.1162/tacl_a_00644](https://doi.org/10.1162/tacl_a_00644)  
  **Resumo:** RippleEdits: 5 mil edições factuais com critérios que avaliam efeitos colaterais (ripple effects) sobre fatos relacionados.  
  **Resultado:** Métodos de edição não produzem mudanças consistentes; um baseline simples de edição em contexto obteve os melhores resultados. Evidência a favor de memória externa sobre edição de pesos.

- **An Empirical Study of Catastrophic Forgetting in Large Language Models During Continual Fine-tuning** (2023) — *Estudo empírico*  
  Yun Luo, Zhen Yang, Fandong Meng, Yafu Li, Jie Zhou, Yue Zhang  
  arXiv v1: 2023-08-17 · última versão (v5): 2025-01-05 · **Revisado por pares**: IEEE Transactions on Audio, Speech, and Language Processing · [arXiv:2308.08747](https://arxiv.org/abs/2308.08747) · [DOI 10.1109/TASLPRO.2025.3606231](https://doi.org/10.1109/TASLPRO.2025.3606231)  
  **Resumo:** Mede esquecimento catastrófico em LLMs de 1B a 7B durante instruction tuning contínuo, em conhecimento de domínio, raciocínio e leitura.  
  **Resultado:** O esquecimento aparece de forma geral e, nessa faixa, aumenta com o tamanho do modelo; instruction tuning geral prévio ajuda a mitigá-lo.

- **The Reversal Curse: LLMs trained on "A is B" fail to learn "B is A"** (2023) — *Resultado negativo/crítica*  
  Lukas Berglund, Meg Tong, Max Kaufmann, Mikita Balesni, Asa Cooper Stickland, Tomasz Korbak et al. (7 autores)  
  arXiv v1: 2023-09-21 · última versão (v4): 2024-05-26 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2309.12288](https://arxiv.org/abs/2309.12288) · [código](https://github.com/lukasberglund/reversal_curse)  
  **Resumo:** Mostra que modelos treinados em «A é B» não generalizam para «B é A» (Reversal Curse), com fine-tuning em afirmações fictícias no GPT-3 e Llama-1.  
  **Resultado:** A falha é robusta a tamanho e família de modelo e não é resolvida por aumento de dados; GPT-4 acerta 79% na direção direta e 33% na inversa para celebridades reais. Limite importante da injeção de fatos nos pesos.

- **Physics of Language Models: Part 3.1, Knowledge Storage and Extraction** (2023) — *Estudo empírico*  
  Zeyuan Allen-Zhu, Yuanzhi Li  
  arXiv v1: 2023-09-25 · última versão (v3): 2024-07-16 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2309.14316](https://arxiv.org/abs/2309.14316)  
  **Resumo:** Estudo controlado com biografias sintéticas sobre como LMs armazenam e extraem conhecimento, com sondagem quase linear das representações internas.  
  **Resultado:** Sem aumento de dados (paráfrases, embaralhamento) no pré-treino, o conhecimento pode ser memorizado mas não extraído, com 0% de acurácia mesmo após instruction tuning. Recomenda reescrever dados de pré-treino para aumentar a diversidade.

- **Retrieval-Augmented Generation for Large Language Models: A Survey** (2023) — *Survey/revisão*  
  Yunfan Gao, Yun Xiong, Xinyu Gao, Kangxiang Jia, Jinliu Pan, Yuxi Bi et al. (10 autores)  
  arXiv v1: 2023-12-18 · última versão (v5): 2024-03-27 · **Preprint (arXiv)** · [arXiv:2312.10997](https://arxiv.org/abs/2312.10997)  
  **Resumo:** Survey amplo de RAG que organiza o campo em RAG ingênuo, avançado e modular, cobrindo recuperação, geração, aumento e avaliação.  
  **Resultado:** Não apresenta experimento próprio; útil como mapa de técnicas e benchmarks. Preprint em atualização contínua.

- **A Comprehensive Study of Knowledge Editing for Large Language Models** (2024) — *Survey/revisão*  
  Ningyu Zhang, Yunzhi Yao, Bozhong Tian, Peng Wang, Shumin Deng, Mengru Wang et al. (22 autores)  
  arXiv v1: 2024-01-02 · última versão (v5): 2024-11-17 · **Preprint (arXiv)** · [arXiv:2401.01286](https://arxiv.org/abs/2401.01286)  
  **Resumo:** Estudo abrangente de edição de conhecimento, com taxonomia (conhecimento externo, fusão no modelo, edição intrínseca) e o benchmark KnowEdit.  
  **Resultado:** Avaliação empírica comparativa e análise de localização do conhecimento.

- **RAG vs Fine-tuning: Pipelines, Tradeoffs, and a Case Study on Agriculture** (2024) — *Estudo empírico*  
  Angels Balaguer, Vinamra Benara, Renato Luiz de Freitas Cunha, Roberto de M. Estevão Filho, Todd Hendry, Daniel Holstein et al. (16 autores)  
  arXiv v1: 2024-01-16 · última versão (v3): 2024-01-30 · **Preprint (arXiv)** · [arXiv:2401.08406](https://arxiv.org/abs/2401.08406)  
  **Resumo:** Propõe pipeline de RAG e fine-tuning (extração de PDFs, geração de perguntas e respostas, FT, avaliação por GPT-4) e o aplica a um estudo de caso de agricultura com Llama2-13B, GPT-3.5 e GPT-4.  
  **Resultado:** Fine-tuning aumentou a acurácia em mais de 6 p.p. e RAG somou mais 5 p.p. de forma cumulativa. Evidência de complementaridade, mas com avaliação feita por LLM e um único domínio.

- **Continual Learning for Large Language Models: A Survey** (2024) — *Survey/revisão*  
  Tongtong Wu, Linhao Luo, Yuan-Fang Li, Shirui Pan, Thuy-Trang Vu, Gholamreza Haffari  
  arXiv v1: 2024-02-02 · última versão (v2): 2024-02-07 · **Preprint (arXiv)** · [arXiv:2402.01364](https://arxiv.org/abs/2402.01364)  
  **Resumo:** Survey de aprendizado contínuo para LLMs organizado em pré-treino contínuo, instruction tuning e alinhamento, contrastando com RAG e edição.  
  **Resultado:** Sem experimento próprio; identifica desafios de avaliação e esquecimento.

- **Instruction-tuned Language Models are Better Knowledge Learners** (2024) — *Método*  
  Zhengbao Jiang, Zhiqing Sun, Weijia Shi, Pedro Rodriguez, Chunting Zhou, Graham Neubig et al. (9 autores)  
  arXiv v1: 2024-02-20 · última versão (v2): 2024-05-26 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2402.12847](https://arxiv.org/abs/2402.12847) · [código](https://github.com/Edward-Sun/PIT)  
  **Resumo:** Propõe pre-instruction-tuning (PIT): expor o modelo a pares de pergunta e resposta antes do pré-treino contínuo em documentos novos.  
  **Resultado:** LLMs treinados na receita padrão minimizam a perplexidade mas respondem mal; PIT supera o instruction tuning padrão em 17,8% na absorção de conhecimento de documentos novos.

- **Learning or Self-aligning? Rethinking Instruction Fine-tuning** (2024) — *Estudo empírico*  
  Mengjie Ren, Boxi Cao, Hongyu Lin, Cao Liu, Xianpei Han, Ke Zeng et al. (9 autores)  
  arXiv v1: 2024-02-28 · última versão (v3): 2024-08-11 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2402.18243](https://arxiv.org/abs/2402.18243)  
  **Resumo:** Desacopla os fatores do instruction fine-tuning com um arcabouço de intervenção de conhecimento.  
  **Resultado:** Tentar ensinar conhecimento novo via IFT raramente ajuda e pode prejudicar muito; manter a consistência do conhecimento interno antes e depois do IFT é o fator crítico. Converge com Gekhman et al.

- **Fine Tuning vs. Retrieval Augmented Generation for Less Popular Knowledge** (2024) — *Estudo empírico*  
  Heydar Soudani, Evangelos Kanoulas, Faegheh Hasibi  
  arXiv v1: 2024-03-03 · última versão (v5): 2024-12-02 · **Revisado por pares**: SIGIR-AP · [arXiv:2403.01432](https://arxiv.org/abs/2403.01432) · [DOI 10.1145/3673791.3698415](https://doi.org/10.1145/3673791.3698415) · [código](https://github.com/informagi/RAGvsFT)  
  **Resumo:** Compara RAG e fine-tuning sobre dados sintéticos para entidades pouco populares, em 12 LMs de tamanhos e tipos diferentes, variando recuperadores e técnicas de aumento de dados.  
  **Resultado:** FT melhora todas as faixas de popularidade, mas RAG o supera por larga margem nas entidades menos populares; melhorar recuperação e aumento de dados amplifica ambos. Propõe Stimulus RAG, que dispensa o FT.

- **Reliable, Adaptable, and Attributable Language Models with Retrieval** (2024) — *Posição*  
  Akari Asai, Zexuan Zhong, Danqi Chen, Pang Wei Koh, Luke Zettlemoyer, Hannaneh Hajishirzi et al. (7 autores)  
  arXiv v1: 2024-03-05 · **Preprint (arXiv)** · [arXiv:2403.03187](https://arxiv.org/abs/2403.03187)  
  **Resumo:** Artigo de posição que defende LMs aumentados por recuperação como próxima geração, por serem mais confiáveis, adaptáveis e atribuíveis.  
  **Resultado:** Propõe agenda: repensar datastores e recuperadores, maior interação recuperador–LM e infraestrutura de escala. Sem experimento novo.

- **RAFT: Adapting Language Model to Domain Specific RAG** (2024) — *Método*  
  Tianjun Zhang, Shishir G. Patil, Naman Jain, Sheng Shen, Matei Zaharia, Ion Stoica et al. (7 autores)  
  arXiv v1: 2024-03-15 · última versão (v2): 2024-06-05 · **Preprint (arXiv)** · [arXiv:2403.10131](https://arxiv.org/abs/2403.10131) · [código](https://github.com/ShishirPatil/gorilla)  
  **Resumo:** RAFT treina o modelo para responder em regime de livro aberto dentro de um domínio, aprendendo a ignorar documentos distratores e a citar o trecho relevante com raciocínio passo a passo.  
  **Resultado:** Melhora consistente em RAG de domínio específico em PubMed, HotpotQA e Gorilla; mostra que fine-tuning e RAG podem ser complementares quando o FT ensina a usar o contexto, não fatos.

- **Injecting New Knowledge into Large Language Models via Supervised Fine-Tuning** (2024) — *Estudo empírico*  
  Nick Mecklenburg, Yiyou Lin, Xiaoxiao Li, Daniel Holstein, Leonardo Nunes, Sara Malvar et al. (12 autores)  
  arXiv v1: 2024-03-30 · última versão (v2): 2024-04-02 · **Preprint (arXiv)** · [arXiv:2404.00213](https://arxiv.org/abs/2404.00213)  
  **Resumo:** Avalia SFT como forma de injetar conhecimento sobre eventos esportivos recentes no GPT-4, comparando geração de dados por escala de tokens e por escala de fatos.  
  **Resultado:** A geração baseada em fatos cobre o conhecimento de forma mais uniforme e trouxe ganhos expressivos em QA fora do domínio. Contraponto parcial a Ovadia et al.: SFT bem desenhado pode injetar fatos. Preprint.

- **FLAME: Factuality-Aware Alignment for Large Language Models** (2024) — *Método*  
  Sheng-Chieh Lin, Luyu Gao, Barlas Oguz, Wenhan Xiong, Jimmy Lin, Wen-tau Yih et al. (7 autores)  
  arXiv v1: 2024-05-02 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2405.01525](https://arxiv.org/abs/2405.01525)  
  **Resumo:** FLAME identifica fatores de alucinação em SFT e RL e propõe alinhamento consciente de factualidade (SFT e DPO orientados a factualidade).  
  **Resultado:** Treinar com conhecimento novo ou textos não familiares incentiva alucinação, e recompensas de RL favorecem respostas longas; o método aumenta a factualidade mantendo a capacidade de seguir instruções.

- **LoRA Learns Less and Forgets Less** (2024) — *Estudo empírico*  
  Dan Biderman, Jacob Portes, Jose Javier Gonzalez Ortiz, Mansheej Paul, Philip Greengard, Connor Jennings et al. (12 autores)  
  arXiv v1: 2024-05-15 · última versão (v2): 2024-09-20 · **Revisado por pares**: Trans. Mach. Learn. Res. · [arXiv:2405.09673](https://arxiv.org/abs/2405.09673)  
  **Resumo:** Compara LoRA e fine-tuning completo em programação e matemática, nos regimes de instruction tuning (~100 mil pares) e pré-treino contínuo (20 bilhões de tokens).  
  **Resultado:** LoRA aprende substancialmente menos que o FT completo, mas preserva melhor o desempenho fora do domínio; o FT completo aprende perturbações de posto 10–100 vezes maior que as configurações típicas de LoRA.

- **WISE: Rethinking the Knowledge Memory for Lifelong Model Editing of Large Language Models** (2024) — *Método*  
  Peng Wang, Zexi Li, Ningyu Zhang, Ziwen Xu, Yunzhi Yao, Yong Jiang et al. (9 autores)  
  arXiv v1: 2024-05-23 · última versão (v3): 2024-12-19 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2405.14768](https://arxiv.org/abs/2405.14768) · [código](https://github.com/zjunlp/EasyEdit)  
  **Resumo:** WISE argumenta que editar memória de longo prazo (pesos) ou de trabalho (recuperação) gera um «triângulo impossível» entre confiabilidade, generalização e localidade, e propõe memória paramétrica lateral com roteador.  
  **Resultado:** Supera editores anteriores em edição contínua (lifelong) em GPT, LLaMA e Mistral.

- **Self-Tuning: Instructing LLMs to Effectively Acquire New Knowledge through Self-Teaching** (2024) — *Método*  
  Xiaoying Zhang, Baolin Peng, Ye Tian, Jingyan Zhou, Yipeng Zhang, Haitao Mi et al. (7 autores)  
  arXiv v1: 2024-06-10 · última versão (v5): 2025-05-16 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2406.06326](https://arxiv.org/abs/2406.06326)  
  **Resumo:** Self-Tuning: o modelo gera tarefas de memorização, compreensão e auto-reflexão a partir dos próprios documentos novos (inspirado na técnica de Feynman).  
  **Resultado:** Desempenho superior em aquisição de conhecimento e melhor preservação do conhecimento anterior em Llama2-7B e outros.

- **How Do Large Language Models Acquire Factual Knowledge During Pretraining?** (2024) — *Estudo empírico*  
  Hoyeon Chang, Jinho Park, Seonghyeon Ye, Sohee Yang, Youngkyung Seo, Du-Seong Chang et al. (7 autores)  
  arXiv v1: 2024-06-17 · última versão (v3): 2024-11-12 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2406.11813](https://arxiv.org/abs/2406.11813)  
  **Resumo:** Analisa a dinâmica de aquisição de conhecimento factual durante o pré-treino injetando fatos e acompanhando checkpoints.  
  **Resultado:** Mais dados de pré-treino não melhoraram significativamente a aquisição; o esquecimento segue lei de potência e é mais rápido com dados duplicados; lotes maiores aumentam a robustez ao esquecimento.

- **Understanding Finetuning for Factual Knowledge Extraction** (2024) — *Estudo empírico*  
  Gaurav Ghosal, Tatsunori Hashimoto, Aditi Raghunathan  
  arXiv v1: 2024-06-20 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2406.14785](https://arxiv.org/abs/2406.14785)  
  **Resumo:** Estuda como a escolha dos dados de QA no fine-tuning afeta a factualidade, com prova teórica e experimentos em PopQA, EntityQuestions e MMLU (Llama-2-7B, Mistral-7B).  
  **Resultado:** Ajustar com fatos menos conhecidos (embora vistos no pré-treino) piora a factualidade em 5–10%; ajustar só com fatos conhecidos iguala ou supera usar todo o conjunto. Replica e estende Gekhman et al. em outra família de modelos.

- **Scaling Laws for Fact Memorization of Large Language Models** (2024) — *Estudo empírico*  
  Xingyu Lu, Xiaonan Li, Qinyuan Cheng, Kai Ding, Xuanjing Huang, Xipeng Qiu  
  arXiv v1: 2024-06-22 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2406.15720](https://arxiv.org/abs/2406.15720)  
  **Resumo:** Estima leis de escala para memorização de fatos em LLMs.  
  **Resultado:** A capacidade de fatos cresce linearmente com o tamanho e de forma exponencial negativa com as épocas; memorizar todo o Wikidata exigiria ~1000B de parâmetros por 100 épocas — memorizar todos os fatos públicos é implausível.

- **Learning Dynamics of LLM Finetuning** (2024) — *Teórico*  
  Yi Ren, Danica J. Sutherland  
  arXiv v1: 2024-07-15 · última versão (v4): 2025-06-29 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2407.10490](https://arxiv.org/abs/2407.10490)  
  **Resumo:** Arcabouço de learning dynamics que decompõe como cada passo de fine-tuning altera as previsões em outros exemplos, para instruction tuning e DPO.  
  **Resultado:** Explica por que certas alucinações aumentam após o FT (usar fatos de uma pergunta para responder outra) e o «squeezing effect» do DPO prolongado.

- **Knowledge Mechanisms in Large Language Models: A Survey and Perspective** (2024) — *Survey/revisão*  
  Mengru Wang, Yunzhi Yao, Ziwen Xu, Shuofei Qiao, Shumin Deng, Peng Wang et al. (13 autores)  
  arXiv v1: 2024-07-22 · última versão (v4): 2024-12-04 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2407.15017](https://arxiv.org/abs/2407.15017)  
  **Resumo:** Survey de mecanismos de conhecimento em LLMs (memorização, compreensão, aplicação, evolução) e fragilidade do conhecimento paramétrico.  
  **Resultado:** Sem experimento próprio; consolida hipóteses sobre onde e como o conhecimento é armazenado.

- **Synthetic continued pretraining** (2024) — *Método*  
  Zitong Yang, Neil Band, Shuangping Li, Emmanuel Candès, Tatsunori Hashimoto  
  arXiv v1: 2024-09-11 · última versão (v2): 2024-10-03 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2409.07431](https://arxiv.org/abs/2409.07431)  
  **Resumo:** Synthetic continued pretraining: a partir de um corpus pequeno, o EntiGraph extrai entidades e gera textos diversos relacionando-as, e o modelo é pré-treinado continuamente nesse corpus sintético.  
  **Resultado:** O modelo passa a responder sobre os documentos sem acesso a eles, e o conhecimento adquirido se soma ao RAG quando os documentos estão disponíveis. Apoia a hipótese de que diversidade de representação é o gargalo.

- **Revisiting the Superficial Alignment Hypothesis** (2024) — *Resultado negativo/crítica*  
  Mohit Raghavendra, Vaskar Nath, Sean Hendryx  
  arXiv v1: 2024-09-27 · **Preprint (arXiv)** · [arXiv:2410.03717](https://arxiv.org/abs/2410.03717)  
  **Resumo:** Reexamina a hipótese do alinhamento superficial medindo o escalonamento do pós-treino com benchmarks objetivos (Llama-3, Mistral, Llama-2).  
  **Resultado:** O desempenho do pós-treino segue lei de potência no número de exemplos; com pós-treino adequado, a integração de conhecimento novo melhora em QA multi-hop. A hipótese é, no máximo, uma simplificação. Preprint.

- **SimRAG: Self-Improving Retrieval-Augmented Generation for Adapting Large Language Models to Specialized Domains** (2024) — *Método*  
  Ran Xu, Hui Liu, Sreyashi Nag, Zhenwei Dai, Yaochen Xie, Xianfeng Tang et al. (11 autores)  
  arXiv v1: 2024-10-23 · última versão (v2): 2025-01-24 · **Revisado por pares**: NAACL 2025 · [arXiv:2410.17952](https://arxiv.org/abs/2410.17952)  
  **Resumo:** SimRAG: auto-treino em que o LLM aprende a responder e a gerar perguntas, criando dados sintéticos de domínio a partir de corpora não rotulados para adaptar RAG.  
  **Resultado:** Ganhos de 1,2% a 8,6% sobre baselines em 11 datasets de três domínios.

- **Fictitious Synthetic Data Can Improve LLM Factuality via Prerequisite Learning** (2024) — *Método*  
  Yujian Liu, Shiyu Chang, Tommi Jaakkola, Yang Zhang  
  arXiv v1: 2024-10-25 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2410.19290](https://arxiv.org/abs/2410.19290) · [código](https://github.com/UCSB-NLP-Chang/Prereq_tune.git)  
  **Resumo:** Prereq-Tune separa o aprendizado de habilidades e de conhecimento: uma etapa prévia ensina o conhecimento necessário e o SFT foca só na habilidade; pode usar dados sintéticos fictícios.  
  **Resultado:** Supera baselines em factualidade em QA curto e geração longa. Resposta direta ao problema descrito por Gekhman et al.

- **FineTuneBench: How well do commercial fine-tuning APIs infuse knowledge into LLMs?** (2024) — *Benchmark/dataset*  
  Eric Wu, Kevin Wu, James Zou  
  arXiv v1: 2024-11-07 · última versão (v2): 2024-11-11 · **Preprint (arXiv)** · [arXiv:2411.05059](https://arxiv.org/abs/2411.05059) · [código](https://github.com/kevinwu23/StanfordFineTuneBench)  
  **Resumo:** FineTuneBench avalia APIs comerciais de fine-tuning (GPT-4o, Gemini 1.5 etc.) na ingestão de informação nova e na atualização de conhecimento existente.  
  **Resultado:** Generalização média de 37% para informação nova e 19% para atualizações (ex.: diretrizes médicas); as APIs do Gemini 1.5 não aprenderam. Preprint.

- **Efficient Knowledge Injection in LLMs via Self-Distillation** (2024) — *Método*  
  Kalle Kujanpää, Pekka Marttinen, Harri Valpola, Alexander Ilin  
  arXiv v1: 2024-12-19 · última versão (v2): 2025-08-07 · **Revisado por pares**: Trans. Mach. Learn. Res. · [arXiv:2412.14964](https://arxiv.org/abs/2412.14964)  
  **Resumo:** Usa prompt distillation (auto-destilação) para internalizar fatos de documentos livres, sem modelo professor maior nem formato estruturado.  
  **Resultado:** Supera o SFT padrão e, em alguns casos, o RAG, em vários tamanhos e famílias de modelo. Contraponto recente à superioridade geral do RAG.

- **Upweighting Easy Samples in Fine-Tuning Mitigates Forgetting** (2025) — *Método*  
  Sunny Sanyal, Hayden Prairie, Rudrajit Das, Ali Kavis, Sujay Sanghavi  
  arXiv v1: 2025-02-05 · última versão (v2): 2025-06-12 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2502.02797](https://arxiv.org/abs/2502.02797) · [código](https://github.com/sanyalsunny111/FLOW_finetuning)  
  **Resumo:** Pondera os exemplos de fine-tuning pela perda do modelo pré-treinado, dando mais peso aos fáceis, para limitar a deriva.  
  **Resultado:** No Gemma 2 2B ajustado em MetaMathQA, perdeu só 0,8% no GSM8K e preservou 5,4% a mais nos dados de pré-treino, comparado ao FT padrão.

- **How Do LLMs Acquire New Knowledge? A Knowledge Circuits Perspective on Continual Pre-Training** (2025) — *Estudo empírico*  
  Yixin Ou, Yunzhi Yao, Ningyu Zhang, Hui Jin, Jiacheng Sun, Shumin Deng et al. (8 autores)  
  arXiv v1: 2025-02-16 · última versão (v2): 2025-06-01 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2502.11196](https://arxiv.org/abs/2502.11196) · [código](https://github.com/zjunlp/DynamicKnowledgeCircuits)  
  **Resumo:** Analisa a evolução de «circuitos de conhecimento» durante o pré-treino contínuo.  
  **Resultado:** A aquisição de conhecimento novo depende de sua relação com o conhecimento existente; os circuitos passam de formação a otimização e evoluem das camadas profundas para as rasas.

- **From Style to Facts: Mapping the Boundaries of Knowledge Injection with Finetuning** (2025) — *Estudo empírico*  
  Eric Zhao, Pranjal Awasthi, Nika Haghtalab  
  arXiv v1: 2025-03-07 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2503.05919](https://arxiv.org/abs/2503.05919)  
  **Resumo:** Estudo em larga escala com a família Gemini v1.5 sobre os fatores que tornam o fine-tuning eficaz para injetar conhecimento.  
  **Resultado:** Formato pergunta-resposta generaliza muito melhor que texto em formato de artigo; números são mais difíceis de reter que categorias; o modelo tem dificuldade de usar o fato ajustado em raciocínio multi-passo.

- **How do language models learn facts? Dynamics, curricula and hallucinations** (2025) — *Estudo empírico*  
  Nicolas Zucchet, Jörg Bornschein, Stephanie Chan, Andrew Lampinen, Razvan Pascanu, Soham De  
  arXiv v1: 2025-03-27 · última versão (v2): 2025-07-24 · **Revisado por pares**: Conference on Language Modeling (2025) · [arXiv:2503.21676](https://arxiv.org/abs/2503.21676)  
  **Resumo:** Estuda a dinâmica de aprendizado de fatos numa tarefa sintética de recuperação factual.  
  **Resultado:** O aprendizado tem três fases com um platô; alucinações surgem junto com o conhecimento, e integrar fatos novos por fine-tuning corrompe rapidamente memórias existentes. Preprint.

- **Memorization vs. Reasoning: Updating LLMs with New Knowledge** (2025) — *Benchmark/dataset*  
  Aochong Oliver Li, Tanya Goyal  
  arXiv v1: 2025-04-16 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2504.12523](https://arxiv.org/abs/2504.12523)  
  **Resumo:** KUP: pipeline que simula atualizações realistas de conhecimento, com sondas diretas (memorização) e indiretas (raciocínio); propõe memory conditioned training (MCT).  
  **Resultado:** Melhores modelos de pré-treino contínuo ficam abaixo de 2% nas sondas de raciocínio; MCT melhora a memorização em até 25,4%.

- **On the generalization of language models from in-context learning and finetuning: a controlled study** (2025) — *Estudo empírico*  
  Andrew K. Lampinen, Arslan Chaudhry, Stephanie C. Y. Chan, Cody Wild, Diane Wan, Alex Ku et al. (10 autores)  
  arXiv v1: 2025-05-01 · última versão (v3): 2025-11-10 · **Preprint (arXiv)** · [arXiv:2505.00661](https://arxiv.org/abs/2505.00661)  
  **Resumo:** Compara a generalização de informação nova aprendida via in-context learning e via fine-tuning, com datasets que isolam o conhecimento do pré-treino.  
  **Resultado:** Com dados equiparados, ICL generaliza vários tipos de inferência de forma mais flexível que FT; adicionar traços de raciocínio em contexto aos dados de FT melhora a generalização. Preprint.

- **Data Doping or True Intelligence? Evaluating the Transferability of Injected Knowledge in LLMs** (2025) — *Estudo empírico*  
  Essa Jan, Moiz Ali, Muhammad Saram Hassan, Fareed Zaffar, Yasir Zaki  
  arXiv v1: 2025-05-22 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2505.17140](https://arxiv.org/abs/2505.17140)  
  **Resumo:** Avalia retenção de conhecimento injetado conforme o tipo de tarefa de fine-tuning.  
  **Resultado:** Tarefas de compreensão (QA, lacunas) retêm 48% contra 17% (tradução) e 20% (texto→JSON) com o mesmo conteúdo factual; todos os modelos caem ao aplicar o conhecimento em contextos mais amplos.

- **Comparing Knowledge Injection Methods for LLMs in a Low-Resource Regime** (2025) — *Estudo empírico*  
  Hugo Abonizio, Thales Almeida, Roberto Lotufo, Rodrigo Nogueira  
  arXiv v1: 2025-08-08 · **Revisado por pares**: Anais do XXII Encontro Nacional de Inteligência Artificial e Computacional (ENIAC 2025) · [arXiv:2508.06178](https://arxiv.org/abs/2508.06178) · [código](https://github.com/hugoabonizio/knowledge-injection-methods)  
  **Resumo:** Investiga injeção de pequenos volumes de informação (notícias recentes) via pré-treino contínuo com aumento de dados sintéticos e sua relação com esquecimento.  
  **Resultado:** Pré-treino contínuo puro dá ganhos modestos; variações textuais diversas melhoram muito o aprendizado; abordagens com RAG degradaram mais os conjuntos de controle. Trabalho brasileiro (anais de evento nacional).

- **Fine-Tuning vs. RAG for Multi-Hop Question Answering with Novel Knowledge** (2026) — *Estudo empírico*  
  Zhuoyi Yang, Yurun Song, Iftekhar Ahmed, Ian Harris  
  arXiv v1: 2026-01-11 · **Revisado por pares**: IEEE Games Entertainment Media Conference · [arXiv:2601.07054](https://arxiv.org/abs/2601.07054)  
  **Resumo:** Compara continued pretraining, SFT e RAG para QA multi-hop com conhecimento temporalmente novo (QASC e um novo conjunto de 10 mil perguntas sobre eventos de 2024), em três LLMs de 7B.  
  **Resultado:** Pré-treino contínuo traz ganho limitado; RAG traz ganhos grandes e consistentes para fatos novos; SFT obteve a maior acurácia geral. Resultado de 2026, de venue de menor visibilidade — confirma e matiza Ovadia et al.

- **SPA: A Simple but Tough-to-Beat Baseline for Knowledge Injection** (2026) — *Método*  
  Kexian Tang, Jiani Wang, Shaowen Wang, Kaifeng Lyu  
  arXiv v1: 2026-03-23 · última versão (v2): 2026-08-09 · **Preprint (arXiv)** · [arXiv:2603.22213](https://arxiv.org/abs/2603.22213) · [código](https://github.com/Tangkexian/SPA)  
  **Resumo:** SPA: baseline simples que gera grandes volumes de dados sintéticos com poucos prompts bem desenhados para injeção de conhecimento.  
  **Resultado:** Supera baselines fortes; métodos com RL sofrem colapso de diversidade em escala e vantagens de prompting multi-etapa desaparecem após ajuste cuidadoso de prompts. Preprint de 2026.

<a id="b"></a>

### Eixo B — Confiabilidade, alucinações e avaliação

- **Selective Classification for Deep Neural Networks** (2017) — *Fundacional*  
  Yonatan Geifman, Ran El-Yaniv  
  arXiv v1: 2017-05-23 · última versão (v2): 2017-06-01 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:1705.08500](https://arxiv.org/abs/1705.08500)  
  **Resumo:** Classificação seletiva (opção de rejeição) para redes profundas com risco-alvo garantido.  
  **Resultado:** Garante 2% de erro top-5 no ImageNet com probabilidade de 99,9% e quase 60% de cobertura.

- **On Calibration of Modern Neural Networks** (2017) — *Fundacional*  
  Chuan Guo, Geoff Pleiss, Yu Sun, Kilian Q. Weinberger  
  arXiv v1: 2017-06-14 · última versão (v2): 2017-08-03 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:1706.04599](https://arxiv.org/abs/1706.04599)  
  **Resumo:** Mostra que redes neurais modernas são mal calibradas e avalia métodos de pós-calibração.  
  **Resultado:** Temperature scaling (um único parâmetro) é surpreendentemente eficaz na maioria dos datasets.

- **Mind the Gap: Assessing Temporal Generalization in Neural Language Models** (2021) — *Estudo empírico*  
  Angeliki Lazaridou, Adhiguna Kuncoro, Elena Gribovskaya, Devang Agrawal, Adam Liska, Tayfun Terzi et al. (14 autores)  
  arXiv v1: 2021-02-03 · última versão (v2): 2021-10-26 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2102.01951](https://arxiv.org/abs/2102.01951)  
  **Resumo:** Avalia LMs (Transformer-XL) prevendo textos posteriores ao período de treino.  
  **Resultado:** O desempenho piora com o tempo e aumentar o modelo não resolve; atualização contínua com dados novos mitiga a degradação. Publica benchmarks de streaming (WMT, arXiv).

- **A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification** (2021) — *Survey/revisão*  
  Anastasios N. Angelopoulos, Stephen Bates  
  arXiv v1: 2021-07-15 · última versão (v6): 2022-12-07 · **Preprint (arXiv)** · [arXiv:2107.07511](https://arxiv.org/abs/2107.07511) · [código](https://github.com/aangelopoulos/conformal-prediction)  
  **Resumo:** Introdução prática a predição conformal e quantificação de incerteza livre de distribuição, com código.  
  **Resultado:** Tutorial; base metodológica para garantias de cobertura em qualquer modelo pré-treinado.

- **TruthfulQA: Measuring How Models Mimic Human Falsehoods** (2021) — *Benchmark/dataset*  
  Stephanie Lin, Jacob Hilton, Owain Evans  
  arXiv v1: 2021-09-08 · última versão (v2): 2022-05-08 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2109.07958](https://arxiv.org/abs/2109.07958) · [DOI 10.18653/v1/2022.acl-long.229](https://doi.org/10.18653/v1/2022.acl-long.229) · [código](https://github.com/sylinrl/TruthfulQA)  
  **Resumo:** TruthfulQA: 817 perguntas em 38 categorias elaboradas para induzir respostas falsas baseadas em equívocos comuns.  
  **Resultado:** O melhor modelo foi verdadeiro em 58% contra 94% dos humanos; os maiores modelos foram os menos verdadeiros (escala inversa).

- **Entity-Based Knowledge Conflicts in Question Answering** (2021) — *Estudo empírico*  
  Shayne Longpre, Kartik Perisetla, Anthony Chen, Nikhil Ramesh, Chris DuBois, Sameer Singh  
  arXiv v1: 2021-09-10 · última versão (v2): 2022-01-12 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2109.05052](https://arxiv.org/abs/2109.05052) · [DOI 10.18653/v1/2021.emnlp-main.565](https://doi.org/10.18653/v1/2021.emnlp-main.565)  
  **Resumo:** Formaliza conflitos de conhecimento baseados em entidades em QA e mede a dependência excessiva de memória paramétrica.  
  **Resultado:** Mitigação simples reduz alucinação e melhora a generalização fora da distribuição em 4–7%, incluindo perguntas dependentes do tempo.

- **Measuring Attribution in Natural Language Generation Models** (2021) — *Fundacional*  
  Hannah Rashkin, Vitaly Nikolaev, Matthew Lamm, Lora Aroyo, Michael Collins, Dipanjan Das et al. (10 autores)  
  arXiv v1: 2021-12-23 · última versão (v2): 2022-08-02 · **Revisado por pares**: Computational Linguistics · [arXiv:2112.12870](https://arxiv.org/abs/2112.12870) · [DOI 10.1162/coli_a_00486](https://doi.org/10.1162/coli_a_00486)  
  **Resumo:** Define AIS (Attributable to Identified Sources), protocolo de anotação para medir se uma saída é sustentada por fontes.  
  **Resultado:** Validado em QA conversacional, sumarização e tabela-para-texto; base conceitual para avaliação de atribuição.

- **Survey of Hallucination in Natural Language Generation** (2022) — *Survey/revisão*  
  Ziwei Ji, Nayeon Lee, Rita Frieske, Tiezheng Yu, Dan Su, Yan Xu et al. (13 autores)  
  arXiv v1: 2022-02-08 · última versão (v7): 2024-07-14 · **Revisado por pares**: ACM Computing Surveys (2022) · [arXiv:2202.03629](https://arxiv.org/abs/2202.03629) · [DOI 10.1145/3571730](https://doi.org/10.1145/3571730)  
  **Resumo:** Primeira revisão ampla de alucinação em geração de linguagem natural, com métricas, mitigação e análise por tarefa.  
  **Resultado:** Define a distinção intrínseca/extrínseca usada em trabalhos posteriores.

- **Language Models (Mostly) Know What They Know** (2022) — *Estudo empírico*  
  Saurav Kadavath, Tom Conerly, Amanda Askell, Tom Henighan, Dawn Drain, Ethan Perez et al. (36 autores)  
  arXiv v1: 2022-07-11 · última versão (v4): 2022-11-21 · **Preprint (arXiv)** · [arXiv:2207.05221](https://arxiv.org/abs/2207.05221)  
  **Resumo:** Avalia se modelos conseguem estimar a correção das próprias respostas (P(True)) e se sabem que sabem (P(IK)).  
  **Resultado:** Modelos grandes são bem calibrados em múltipla escolha no formato certo; P(True) funciona e melhora com várias amostras; P(IK) generaliza parcialmente, mas com calibração fraca em tarefas novas. Preprint.

- **RealTime QA: What's the Answer Right Now?** (2022) — *Benchmark/dataset*  
  Jungo Kasai, Keisuke Sakaguchi, Yoichi Takahashi, Ronan Le Bras, Akari Asai, Xinyan Yu et al. (10 autores)  
  arXiv v1: 2022-07-27 · última versão (v2): 2024-02-28 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2207.13332](https://arxiv.org/abs/2207.13332)  
  **Resumo:** RealTime QA: plataforma que publica perguntas semanais sobre o mundo atual.  
  **Resultado:** GPT-3 atualiza respostas com documentos recém-recuperados, mas tende a responder com informação desatualizada quando a recuperação é insuficiente — motiva detecção de perguntas sem resposta.

- **Holistic Evaluation of Language Models** (2022) — *Benchmark/dataset*  
  Percy Liang, Rishi Bommasani, Tony Lee, Dimitris Tsipras, Dilara Soylu, Michihiro Yasunaga et al. (50 autores)  
  arXiv v1: 2022-11-16 · última versão (v2): 2023-10-01 · **Revisado por pares**: Transactions on Machine Learning Research (TMLR) · [arXiv:2211.09110](https://arxiv.org/abs/2211.09110)  
  **Resumo:** HELM: avaliação holística com 7 métricas (acurácia, calibração, robustez, justiça, viés, toxicidade, eficiência) em 42 cenários e 30 modelos.  
  **Resultado:** Cobertura padronizada dos cenários centrais passou de 17,9% para 96,0%; 25 achados de alto nível; dados brutos públicos.

- **Semantic Uncertainty: Linguistic Invariances for Uncertainty Estimation in Natural Language Generation** (2023) — *Método*  
  Lorenz Kuhn, Yarin Gal, Sebastian Farquhar  
  arXiv v1: 2023-02-19 · última versão (v3): 2023-04-15 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2302.09664](https://arxiv.org/abs/2302.09664)  
  **Resumo:** Entropia semântica: mede incerteza agrupando respostas equivalentes em significado antes de calcular a entropia.  
  **Resultado:** Prediz a acurácia em QA melhor que baselines comparáveis, sem modificar o modelo nem exigir supervisão.

- **Not what you've signed up for: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection** (2023) — *Estudo empírico*  
  Kai Greshake, Sahar Abdelnabi, Shailesh Mishra, Christoph Endres, Thorsten Holz, Mario Fritz  
  arXiv v1: 2023-02-23 · última versão (v2): 2023-05-05 · **Workshop**: AISec@CCS 2023 (workshop) · [arXiv:2302.12173](https://arxiv.org/abs/2302.12173) · [DOI 10.1145/3605764.3623985](https://doi.org/10.1145/3605764.3623985)  
  **Resumo:** Introduz prompt injection indireta: instruções maliciosas plantadas em dados que a aplicação recupera.  
  **Resultado:** Ataques práticos contra o Bing Chat com GPT-4 e aplicações sintéticas, incluindo roubo de dados e controle de APIs; mitigações eficazes faltavam. Crítico para qualquer RAG.

- **SelfCheckGPT: Zero-Resource Black-Box Hallucination Detection for Generative Large Language Models** (2023) — *Método*  
  Potsawee Manakul, Adian Liusie, Mark J. F. Gales  
  arXiv v1: 2023-03-15 · última versão (v3): 2023-10-11 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2303.08896](https://arxiv.org/abs/2303.08896)  
  **Resumo:** SelfCheckGPT detecta alucinação em modelos caixa-preta comparando a consistência entre várias amostras, sem base externa.  
  **Resultado:** AUC-PR maior que métodos caixa-cinza na detecção por sentença em biografias do WikiBio anotadas manualmente.

- **Adaptive Chameleon or Stubborn Sloth: Revealing the Behavior of Large Language Models in Knowledge Conflicts** (2023) — *Estudo empírico*  
  Jian Xie, Kai Zhang, Jiangjie Chen, Renze Lou, Yu Su  
  arXiv v1: 2023-05-22 · última versão (v4): 2024-02-27 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2305.13300](https://arxiv.org/abs/2305.13300) · [código](https://github.com/OSU-NLP-Group/LLM-Knowledge-Conflict)  
  **Resumo:** Investigação controlada de como LLMs reagem a evidências externas que contradizem sua memória paramétrica.  
  **Resultado:** LLMs aceitam evidência externa coerente e convincente mesmo contra a memória, mas mostram viés de confirmação quando há evidência parcialmente consistente com a memória. Implica riscos para RAG com documentos conflitantes.

- **FActScore: Fine-grained Atomic Evaluation of Factual Precision in Long Form Text Generation** (2023) — *Benchmark/dataset*  
  Sewon Min, Kalpesh Krishna, Xinxi Lyu, Mike Lewis, Wen-tau Yih, Pang Wei Koh et al. (9 autores)  
  arXiv v1: 2023-05-23 · última versão (v2): 2023-10-11 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2305.14251](https://arxiv.org/abs/2305.14251) · [código](https://github.com/shmsw25/FActScore)  
  **Resumo:** FActScore divide gerações longas em fatos atômicos e mede a fração apoiada por uma fonte confiável, com avaliação humana e estimador automático.  
  **Resultado:** ChatGPT obteve apenas 58% em biografias; o estimador automático tem erro abaixo de 2%; avaliou 6.500 gerações de 13 LMs.

- **Enabling Large Language Models to Generate Text with Citations** (2023) — *Benchmark/dataset*  
  Tianyu Gao, Howard Yen, Jiatong Yu, Danqi Chen  
  arXiv v1: 2023-05-24 · última versão (v2): 2023-10-31 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2305.14627](https://arxiv.org/abs/2305.14627) · [código](https://github.com/princeton-nlp/ALCE)  
  **Resumo:** ALCE: primeiro benchmark para avaliar automaticamente geração com citações (fluência, correção, qualidade das citações).  
  **Resultado:** Mesmo os melhores modelos deixam de ter suporte completo de citação em 50% das respostas no ELI5.

- **Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena** (2023) — *Benchmark/dataset*  
  Lianmin Zheng, Wei-Lin Chiang, Ying Sheng, Siyuan Zhuang, Zhanghao Wu, Yonghao Zhuang et al. (13 autores)  
  arXiv v1: 2023-06-09 · última versão (v4): 2023-12-24 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2306.05685](https://arxiv.org/abs/2306.05685) · [DOI 10.52202/075280-2020](https://doi.org/10.52202/075280-2020) · [código](https://github.com/lm-sys/FastChat/tree/main/fastchat/llm_judge)  
  **Resumo:** Avalia LLMs como juízes (MT-Bench e Chatbot Arena) e seus vieses de posição, verbosidade e autopromoção.  
  **Resultado:** GPT-4 como juiz concorda com preferências humanas em mais de 80%, nível semelhante à concordância entre humanos.

- **Time Travel in LLMs: Tracing Data Contamination in Large Language Models** (2023) — *Método*  
  Shahriar Golchin, Mihai Surdeanu  
  arXiv v1: 2023-08-16 · última versão (v3): 2024-02-21 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2308.08493](https://arxiv.org/abs/2308.08493)  
  **Resumo:** Detecta contaminação pedindo ao modelo para completar instâncias a partir do nome do dataset e da partição (guided instruction).  
  **Resultado:** Acurácia de 92% a 100% na detecção em sete datasets comparada a especialistas; indica contaminação do GPT-4 em AG News, WNLI e outros.

- **Siren's Song in the AI Ocean: A Survey on Hallucination in Large Language Models** (2023) — *Survey/revisão*  
  Yue Zhang, Yafu Li, Leyang Cui, Deng Cai, Lemao Liu, Tingchen Fu et al. (16 autores)  
  arXiv v1: 2023-09-03 · última versão (v3): 2025-09-14 · **Revisado por pares**: Computational Linguistics · [arXiv:2309.01219](https://arxiv.org/abs/2309.01219) · [DOI 10.1162/coli.a.16](https://doi.org/10.1162/coli.a.16)  
  **Resumo:** Survey de alucinação em LLMs com taxonomias, benchmarks, explicações e mitigação.  
  **Resultado:** Referência ampla; sem experimento próprio.

- **Chain-of-Verification Reduces Hallucination in Large Language Models** (2023) — *Método*  
  Shehzaad Dhuliawala, Mojtaba Komeili, Jing Xu, Roberta Raileanu, Xian Li, Asli Celikyilmaz et al. (7 autores)  
  arXiv v1: 2023-09-20 · última versão (v2): 2023-09-25 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2309.11495](https://arxiv.org/abs/2309.11495)  
  **Resumo:** Chain-of-Verification: o modelo redige, planeja perguntas de verificação, responde-as de forma independente e reescreve a resposta.  
  **Resultado:** Reduz alucinações em listas do Wikidata, MultiSpanQA fechado e geração longa.

- **Ragas: Automated Evaluation of Retrieval Augmented Generation** (2023) — *Método*  
  Shahul Es, Jithin James, Luis Espinosa-Anke, Steven Schockaert  
  arXiv v1: 2023-09-26 · última versão (v2): 2025-04-28 · **Revisado por pares**: Conference of the European Chapter of the Association for Computational Linguistics · [arXiv:2309.15217](https://arxiv.org/abs/2309.15217)  
  **Resumo:** RAGAS: conjunto de métricas sem referência humana para avaliar pipelines RAG (relevância do contexto, fidelidade, relevância da resposta).  
  **Resultado:** Propõe a avaliação; validação empírica limitada — métricas dependem de um LLM avaliador.

- **FreshLLMs: Refreshing Large Language Models with Search Engine Augmentation** (2023) — *Benchmark/dataset*  
  Tu Vu, Mohit Iyyer, Xuezhi Wang, Noah Constant, Jerry Wei, Jason Wei et al. (11 autores)  
  arXiv v1: 2023-10-05 · última versão (v2): 2023-11-22 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2310.03214](https://arxiv.org/abs/2310.03214) · [código](https://github.com/freshllms/freshqa)  
  **Resumo:** FreshQA: benchmark dinâmico com perguntas sobre conhecimento que muda rápido e com premissas falsas; propõe FreshPrompt (busca na web no prompt).  
  **Resultado:** Todos os modelos, de qualquer tamanho, falham em conhecimento volátil e premissas falsas; FreshPrompt supera Self-Ask e o Perplexity.AI; número e ordem das evidências importam. Base: mais de 50 mil julgamentos humanos.

- **NeMo Guardrails: A Toolkit for Controllable and Safe LLM Applications with Programmable Rails** (2023) — *Sistema*  
  Traian Rebedea, Razvan Dinu, Makesh Sreedhar, Christopher Parisien, Jonathan Cohen  
  arXiv v1: 2023-10-16 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2310.10501](https://arxiv.org/abs/2310.10501)  
  **Resumo:** NeMo Guardrails: toolkit de trilhas programáveis em tempo de execução, independentes do modelo, para controlar conversas com LLMs.  
  **Resultado:** Resultados iniciais mostram viabilidade com vários provedores; evidência empírica limitada (demo track).

- **Proving Test Set Contamination in Black Box Language Models** (2023) — *Método*  
  Yonatan Oren, Nicole Meister, Niladri Chatterji, Faisal Ladhak, Tatsunori B. Hashimoto  
  arXiv v1: 2023-10-26 · última versão (v2): 2023-11-24 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2310.17623](https://arxiv.org/abs/2310.17623)  
  **Resumo:** Teste estatístico de contaminação sem acesso aos dados de treino: compara a verossimilhança da ordem canônica do benchmark com ordens embaralhadas.  
  **Resultado:** Detecta contaminação com modelos de 1,4B e conjuntos de mil exemplos; auditoria de cinco modelos populares encontrou pouca evidência de contaminação generalizada.

- **NLP Evaluation in trouble: On the Need to Measure LLM Data Contamination for each Benchmark** (2023) — *Posição*  
  Oscar Sainz, Jon Ander Campos, Iker García-Ferrero, Julen Etxaniz, Oier Lopez de Lacalle, Eneko Agirre  
  arXiv v1: 2023-10-27 · **Revisado por pares**: Findings of EMNLP (comentário do arXiv) · [arXiv:2310.18018](https://arxiv.org/abs/2310.18018)  
  **Resumo:** Artigo de posição sobre contaminação de dados em benchmarks de PLN, com níveis de contaminação e propostas de detecção.  
  **Resultado:** Argumenta que a contaminação superestima desempenho e pode levar a conclusões científicas erradas; sem experimento.

- **A Survey on Hallucination in Large Language Models: Principles, Taxonomy, Challenges, and Open Questions** (2023) — *Survey/revisão*  
  Lei Huang, Weijiang Yu, Weitao Ma, Weihong Zhong, Zhangyin Feng, Haotian Wang et al. (11 autores)  
  arXiv v1: 2023-11-09 · última versão (v2): 2024-11-19 · **Revisado por pares**: ACM Trans. Inf. Syst. · [arXiv:2311.05232](https://arxiv.org/abs/2311.05232) · [DOI 10.1145/3703155](https://doi.org/10.1145/3703155)  
  **Resumo:** Survey de alucinação em LLMs com taxonomia (factualidade vs fidelidade), causas, detecção, benchmarks e mitigação, incluindo limites de LLMs com recuperação.  
  **Resultado:** Referência de taxonomia; sem experimento próprio.

- **R-Tuning: Instructing Large Language Models to Say `I Don't Know'** (2023) — *Método*  
  Hanning Zhang, Shizhe Diao, Yong Lin, Yi R. Fung, Qing Lian, Xingyao Wang et al. (9 autores)  
  arXiv v1: 2023-11-16 · última versão (v3): 2024-06-07 · **Revisado por pares**: North American Chapter of the Association for Computational Linguistics · [arXiv:2311.09677](https://arxiv.org/abs/2311.09677) · [DOI 10.18653/v1/2024.naacl-long.394](https://doi.org/10.18653/v1/2024.naacl-long.394) · [código](https://github.com/shizhediao/R-Tuning)  
  **Resumo:** R-Tuning constrói dados de recusa a partir da diferença entre o conhecimento paramétrico e os dados de instruction tuning, ensinando o modelo a dizer «não sei».  
  **Resultado:** Melhora a resposta a perguntas conhecidas e a recusa nas desconhecidas; a recusa generaliza para outros domínios e melhora a calibração.

- **ARES: An Automated Evaluation Framework for Retrieval-Augmented Generation Systems** (2023) — *Método*  
  Jon Saad-Falcon, Omar Khattab, Christopher Potts, Matei Zaharia  
  arXiv v1: 2023-11-16 · última versão (v2): 2024-03-31 · **Revisado por pares**: North American Chapter of the Association for Computational Linguistics · [arXiv:2311.09476](https://arxiv.org/abs/2311.09476)  
  **Resumo:** ARES treina juízes leves com dados sintéticos e usa poucas anotações humanas com prediction-powered inference para avaliar RAG.  
  **Resultado:** Avaliação precisa em oito tarefas (KILT, SuperGLUE, AIS) com poucas centenas de anotações humanas, robusta a mudança de domínio.

- **Calibrated Language Models Must Hallucinate** (2023) — *Teórico*  
  Adam Tauman Kalai, Santosh S. Vempala  
  arXiv v1: 2023-11-24 · última versão (v3): 2024-03-20 · **Revisado por pares**: STOC 2024 · [arXiv:2311.14648](https://arxiv.org/abs/2311.14648) · [DOI 10.1145/3618260.3649777](https://doi.org/10.1145/3618260.3649777)  
  **Resumo:** Prova um limite inferior estatístico para a taxa de alucinação de modelos calibrados em fatos «arbitrários».  
  **Resultado:** A taxa aproxima-se da fração de fatos que aparecem uma única vez no treino (estimativa de Good-Turing), mesmo com dados perfeitos; não há razão estatística para alucinar fatos repetidos ou sistemáticos.

- **Llama Guard: LLM-based Input-Output Safeguard for Human-AI Conversations** (2023) — *Sistema*  
  Hakan Inan, Kartikeya Upasani, Jianfeng Chi, Rashi Rungta, Krithika Iyer, Yuning Mao et al. (11 autores)  
  arXiv v1: 2023-12-07 · **Preprint (arXiv)** · [arXiv:2312.06674](https://arxiv.org/abs/2312.06674)  
  **Resumo:** Llama Guard: Llama2-7b ajustado para classificar prompts e respostas segundo uma taxonomia de riscos.  
  **Resultado:** Igual ou superior a ferramentas de moderação existentes em OpenAI Moderation e ToxicChat; taxonomia adaptável por prompt.

- **Alignment for Honesty** (2023) — *Método*  
  Yuqing Yang, Ethan Chern, Xipeng Qiu, Graham Neubig, Pengfei Liu  
  arXiv v1: 2023-12-12 · última versão (v2): 2024-10-28 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2312.07000](https://arxiv.org/abs/2312.07000) · [código](https://github.com/GAIR-NLP/alignment-for-honesty)  
  **Resumo:** Define alinhamento para honestidade (recusar quando falta conhecimento sem ser excessivamente conservador) com métricas e arcabouço de treino.  
  **Resultado:** Modelos alinhados mostram aumento marcado de honestidade sem perder desempenho em outras tarefas.

- **PoisonedRAG: Knowledge Corruption Attacks to Retrieval-Augmented Generation of Large Language Models** (2024) — *Estudo empírico*  
  Wei Zou, Runpeng Geng, Binghui Wang, Jinyuan Jia  
  arXiv v1: 2024-02-12 · última versão (v3): 2024-08-13 · **Revisado por pares**: USENIX Security Symposium · [arXiv:2402.07867](https://arxiv.org/abs/2402.07867) · [código](https://github.com/sleeepeer/PoisonedRAG)  
  **Resumo:** PoisonedRAG: ataque de corrupção da base de conhecimento de RAG formulado como otimização.  
  **Resultado:** 90% de sucesso injetando cinco textos maliciosos por pergunta-alvo numa base de milhões de textos; defesas avaliadas foram insuficientes.

- **Language Models with Conformal Factuality Guarantees** (2024) — *Método*  
  Christopher Mohri, Tatsunori Hashimoto  
  arXiv v1: 2024-02-15 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2402.10978](https://arxiv.org/abs/2402.10978)  
  **Resumo:** Conformal factuality: liga predição conformal à correção de saídas de LMs, tornando-as progressivamente menos específicas até atingir a garantia.  
  **Resultado:** Garantias de 80–90% de correção mantendo a maior parte da saída original, em FActScore, NaturalQuestions e MATH.

- **Unfamiliar Finetuning Examples Control How Language Models Hallucinate** (2024) — *Estudo empírico*  
  Katie Kang, Eric Wallace, Claire Tomlin, Aviral Kumar, Sergey Levine  
  arXiv v1: 2024-03-08 · última versão (v2): 2024-05-28 · **Revisado por pares**: North American Chapter of the Association for Computational Linguistics · [arXiv:2403.05612](https://arxiv.org/abs/2403.05612)  
  **Resumo:** Mostra que exemplos não familiares no fine-tuning moldam como o modelo alucina: as respostas a perguntas desconhecidas imitam as respostas dadas a esses exemplos no treino (SFT, RL e modelo de recompensa; TriviaQA e MMLU).  
  **Resultado:** Supervisionar os exemplos não familiares (ex.: «não sei») controla a alucinação; modelos de recompensa mais confiáveis melhoram o RL de factualidade em geração longa. Converge com Gekhman et al.

- **Knowledge Conflicts for LLMs: A Survey** (2024) — *Survey/revisão*  
  Rongwu Xu, Zehan Qi, Zhijiang Guo, Cunxiang Wang, Hongru Wang, Yue Zhang et al. (7 autores)  
  arXiv v1: 2024-03-13 · última versão (v2): 2024-06-22 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2403.08319](https://arxiv.org/abs/2403.08319) · [código](https://github.com/pillowsofwind/Knowledge-Conflicts-Survey)  
  **Resumo:** Survey de conflitos de conhecimento: contexto vs memória, entre contextos e dentro da memória.  
  **Resultado:** Organiza causas, comportamentos e soluções; sem experimento próprio.

- **Detecting hallucinations in large language models using semantic entropy** (2024) — *Estudo empírico*  
  Sebastian Farquhar, Jannik Kossen, Lorenz Kuhn, Yarin Gal  
  Publicação: 2024-06-19 · **Revisado por pares**: Nature · [DOI 10.1038/s41586-024-07421-0](https://doi.org/10.1038/s41586-024-07421-0)  
  **Resumo:** Versão em periódico da entropia semântica aplicada à detecção de confabulações (alucinações arbitrárias) em LLMs.  
  **Resultado:** Detecta confabulações em vários datasets e modelos sem conhecimento prévio da tarefa; publicado na Nature.

- **Know Your Limits: A Survey of Abstention in Large Language Models** (2024) — *Survey/revisão*  
  Bingbing Wen, Jihan Yao, Shangbin Feng, Chenjun Xu, Yulia Tsvetkov, Bill Howe et al. (7 autores)  
  arXiv v1: 2024-07-25 · última versão (v3): 2025-02-12 · **Revisado por pares**: Transactions of the Association for Computational Linguistics · [arXiv:2407.18418](https://arxiv.org/abs/2407.18418) · [DOI 10.1162/tacl_a_00754](https://doi.org/10.1162/tacl_a_00754)  
  **Resumo:** Survey de abstenção em LLMs sob as perspectivas da consulta, do modelo e de valores humanos.  
  **Resultado:** Organiza métodos, benchmarks e métricas de abstenção; sem experimento próprio.

- **LLMs Know More Than They Show: On the Intrinsic Representation of LLM Hallucinations** (2024) — *Estudo empírico*  
  Hadas Orgad, Michael Toker, Zorik Gekhman, Roi Reichart, Idan Szpektor, Hadas Kotek et al. (7 autores)  
  arXiv v1: 2024-10-03 · última versão (v4): 2025-05-18 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2410.02707](https://arxiv.org/abs/2410.02707)  
  **Resumo:** Mostra que as representações internas de LLMs codificam muito mais informação sobre veracidade do que se supunha, concentrada em tokens específicos.  
  **Resultado:** Detectores de erro melhoram, mas não generalizam entre datasets; o modelo pode codificar a resposta certa e ainda gerar a errada.

- **HalluLens: LLM Hallucination Benchmark** (2025) — *Benchmark/dataset*  
  Yejin Bang, Ziwei Ji, Alan Schelten, Anthony Hartshorn, Tara Fowler, Cheng Zhang et al. (8 autores)  
  arXiv v1: 2025-04-24 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2504.17550](https://arxiv.org/abs/2504.17550)  
  **Resumo:** HalluLens: benchmark com taxonomia que separa alucinação extrínseca, intrínseca e factualidade, com geração dinâmica de testes contra vazamento.  
  **Resultado:** Analisa saturação e limites de benchmarks existentes.

- **The Hallucination Tax of Reinforcement Finetuning** (2025) — *Resultado negativo/crítica*  
  Linxin Song, Taiwei Shi, Jieyu Zhao  
  arXiv v1: 2025-05-20 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2505.13988](https://arxiv.org/abs/2505.13988)  
  **Resumo:** Identifica a «taxa de alucinação» do reinforcement fine-tuning para raciocínio, usando um dataset de problemas matemáticos sem resposta (SUM).  
  **Resultado:** RFT padrão reduz a taxa de recusa em mais de 80%; incluir 10% de SUM restaura a recusa com perda mínima, generalizando até para QA factual.

- **Why Language Models Hallucinate** (2025) — *Teórico*  
  Adam Tauman Kalai, Ofir Nachum, Santosh S. Vempala, Edwin Zhang  
  arXiv v1: 2025-09-04 · **Preprint (arXiv)** · [arXiv:2509.04664](https://arxiv.org/abs/2509.04664)  
  **Resumo:** Argumenta que alucinações surgem como erros de classificação binária no pré-treino e persistem porque avaliações premiam chutar em vez de admitir incerteza.  
  **Resultado:** Propõe mudar a pontuação dos benchmarks dominantes para não penalizar abstenção. Preprint teórico/posicional.

- **Why Fine-Tuning Encourages Hallucinations and How to Fix It** (2026) — *Método*  
  Guy Kaplan, Zorik Gekhman, Zhen Zhu, Lotem Rozner, Yuval Reif, Swabha Swayamdipta et al. (8 autores)  
  arXiv v1: 2026-04-16 · última versão (v3): 2026-09-25 · **Preprint (arXiv)** · [arXiv:2604.15574](https://arxiv.org/abs/2604.15574)  
  **Resumo:** Retoma o problema de Gekhman et al. e propõe SFT com auto-destilação que regulariza a deriva da distribuição de saída; também testa congelar grupos de parâmetros.  
  **Resultado:** Aprende fatos novos com menos alucinação sobre o conhecimento prévio; o principal mecanismo é interferência entre representações semânticas sobrepostas. Preprint de 2026.

<a id="c"></a>

### Eixo C — Arquiteturas modernas de sistemas de IA

- **Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer** (2017) — *Fundacional*  
  Noam Shazeer, Azalia Mirhoseini, Krzysztof Maziarz, Andy Davis, Quoc Le, Geoffrey Hinton et al. (7 autores)  
  arXiv v1: 2017-01-23 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:1701.06538](https://arxiv.org/abs/1701.06538)  
  **Resumo:** Camada Mixture-of-Experts esparsa com rede de gating treinável e milhares de especialistas.  
  **Resultado:** Aumento de capacidade acima de 1000 vezes com pequena perda de eficiência; melhores resultados em modelagem de linguagem e tradução a menor custo.

- **Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity** (2021) — *Fundacional*  
  William Fedus, Barret Zoph, Noam Shazeer  
  arXiv v1: 2021-01-11 · última versão (v3): 2022-06-16 · **Revisado por pares**: Journal of machine learning research · [arXiv:2101.03961](https://arxiv.org/abs/2101.03961)  
  **Resumo:** Switch Transformer simplifica o roteamento MoE (um especialista por token) e estabiliza o treino.  
  **Resultado:** Até 7 vezes mais rápido no pré-treino que T5 com o mesmo cômputo; modelos de até um trilhão de parâmetros com 4 vezes de aceleração sobre T5-XXL.

- **Learning Transferable Visual Models From Natural Language Supervision** (2021) — *Fundacional*  
  Alec Radford, Jong Wook Kim, Chris Hallacy, Aditya Ramesh, Gabriel Goh, Sandhini Agarwal et al. (12 autores)  
  arXiv v1: 2021-02-26 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2103.00020](https://arxiv.org/abs/2103.00020) · [código](https://github.com/OpenAI/CLIP)  
  **Resumo:** CLIP: pré-treino contrastivo imagem-texto em 400 milhões de pares.  
  **Resultado:** Transferência zero-shot competitiva em mais de 30 datasets; iguala a ResNet-50 no ImageNet sem usar seus exemplos de treino.

- **Chain-of-Thought Prompting Elicits Reasoning in Large Language Models** (2022) — *Fundacional*  
  Jason Wei, Xuezhi Wang, Dale Schuurmans, Maarten Bosma, Brian Ichter, Fei Xia et al. (9 autores)  
  arXiv v1: 2022-01-28 · última versão (v6): 2023-01-10 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2201.11903](https://arxiv.org/abs/2201.11903) · [DOI 10.52202/068431-1800](https://doi.org/10.52202/068431-1800)  
  **Resumo:** Chain-of-thought prompting: exemplos com passos intermediários de raciocínio.  
  **Resultado:** Com oito exemplos, um modelo de 540B atingiu o estado da arte no GSM8K; o efeito emerge em modelos grandes.

- **Self-Consistency Improves Chain of Thought Reasoning in Language Models** (2022) — *Fundacional*  
  Xuezhi Wang, Jason Wei, Dale Schuurmans, Quoc Le, Ed Chi, Sharan Narang et al. (8 autores)  
  arXiv v1: 2022-03-21 · última versão (v4): 2023-03-07 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2203.11171](https://arxiv.org/abs/2203.11171)  
  **Resumo:** Self-consistency amostra vários raciocínios e escolhe a resposta mais consistente.  
  **Resultado:** Ganhos sobre chain-of-thought: GSM8K +17,9%, SVAMP +11,0%, AQuA +12,2%, StrategyQA +6,4%, ARC-challenge +3,9%.

- **ReAct: Synergizing Reasoning and Acting in Language Models** (2022) — *Fundacional*  
  Shunyu Yao, Jeffrey Zhao, Dian Yu, Nan Du, Izhak Shafran, Karthik Narasimhan et al. (7 autores)  
  arXiv v1: 2022-10-06 · última versão (v3): 2023-03-10 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2210.03629](https://arxiv.org/abs/2210.03629)  
  **Resumo:** ReAct intercala raciocínio e ações (ex.: consultas a uma API da Wikipédia) no mesmo traço.  
  **Resultado:** Reduz alucinação em HotpotQA e Fever; em ALFWorld e WebShop supera imitação e RL por 34 e 10 pontos absolutos com um ou dois exemplos.

- **Toolformer: Language Models Can Teach Themselves to Use Tools** (2023) — *Fundacional*  
  Timo Schick, Jane Dwivedi-Yu, Roberto Dessì, Roberta Raileanu, Maria Lomeli, Luke Zettlemoyer et al. (8 autores)  
  arXiv v1: 2023-02-09 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2302.04761](https://arxiv.org/abs/2302.04761)  
  **Resumo:** Toolformer aprende de forma auto-supervisionada quando e como chamar APIs (calculadora, busca, tradução, calendário).  
  **Resultado:** Melhora substancial em zero-shot, competitivo com modelos maiores, sem perder capacidade de modelagem de linguagem.

- **Reflexion: Language Agents with Verbal Reinforcement Learning** (2023) — *Método*  
  Noah Shinn, Federico Cassano, Edward Berman, Ashwin Gopinath, Karthik Narasimhan, Shunyu Yao  
  arXiv v1: 2023-03-20 · última versão (v4): 2023-10-10 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2303.11366](https://arxiv.org/abs/2303.11366) · [DOI 10.52202/075280-0377](https://doi.org/10.52202/075280-0377)  
  **Resumo:** Reflexion: agentes refletem verbalmente sobre o feedback e guardam a reflexão em memória episódica, sem atualizar pesos.  
  **Resultado:** 91% pass@1 no HumanEval, acima dos 80% do GPT-4 reportados na época.

- **Generative Agents: Interactive Simulacra of Human Behavior** (2023) — *Sistema*  
  Joon Sung Park, Joseph C. O'Brien, Carrie J. Cai, Meredith Ringel Morris, Percy Liang, Michael S. Bernstein  
  arXiv v1: 2023-04-07 · última versão (v2): 2023-08-06 · **Revisado por pares**: ACM Symposium on User Interface Software and Technology · [arXiv:2304.03442](https://arxiv.org/abs/2304.03442) · [DOI 10.1145/3586183.3606763](https://doi.org/10.1145/3586183.3606763)  
  **Resumo:** Agentes generativos com memória em linguagem natural, reflexão e planejamento, simulando 25 personagens num ambiente.  
  **Resultado:** Comportamentos sociais emergentes críveis; ablação mostra que observação, planejamento e reflexão são essenciais.

- **FrugalGPT: How to Use Large Language Models While Reducing Cost and Improving Performance** (2023) — *Método*  
  Lingjiao Chen, Matei Zaharia, James Zou  
  arXiv v1: 2023-05-09 · **Revisado por pares**: Trans. Mach. Learn. Res. · [arXiv:2305.05176](https://arxiv.org/abs/2305.05176)  
  **Resumo:** FrugalGPT: estratégias de redução de custo (adaptação de prompt, aproximação, cascata) e uma cascata aprendida de LLMs.  
  **Resultado:** Iguala o melhor LLM individual com até 98% de redução de custo ou melhora 4% a acurácia com o mesmo custo.

- **Gorilla: Large Language Model Connected with Massive APIs** (2023) — *Método*  
  Shishir G. Patil, Tianjun Zhang, Xin Wang, Joseph E. Gonzalez  
  arXiv v1: 2023-05-24 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2305.15334](https://arxiv.org/abs/2305.15334) · [DOI 10.52202/079017-4020](https://doi.org/10.52202/079017-4020)  
  **Resumo:** Gorilla: LLaMA ajustado para gerar chamadas de API, combinado a recuperação de documentação (APIBench).  
  **Resultado:** Supera GPT-4 na escrita de chamadas de API e se adapta a mudanças de documentação em tempo de teste via recuperação.

- **Lost in the Middle: How Language Models Use Long Contexts** (2023) — *Estudo empírico*  
  Nelson F. Liu, Kevin Lin, John Hewitt, Ashwin Paranjape, Michele Bevilacqua, Fabio Petroni et al. (7 autores)  
  arXiv v1: 2023-07-06 · última versão (v3): 2023-11-20 · **Revisado por pares**: Transactions of the Association for Computational Linguistics · [arXiv:2307.03172](https://arxiv.org/abs/2307.03172) · [DOI 10.1162/tacl_a_00638](https://doi.org/10.1162/tacl_a_00638)  
  **Resumo:** Analisa como LMs usam contextos longos em QA multi-documento e recuperação chave-valor.  
  **Resultado:** Desempenho maior quando a informação está no início ou fim do contexto e cai no meio, mesmo em modelos de contexto longo («lost in the middle»).

- **AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation** (2023) — *Sistema*  
  Qingyun Wu, Gagan Bansal, Jieyu Zhang, Yiran Wu, Beibin Li, Erkang Zhu et al. (14 autores)  
  arXiv v1: 2023-08-16 · última versão (v2): 2023-10-03 · **Preprint (arXiv)** · [arXiv:2308.08155](https://arxiv.org/abs/2308.08155)  
  **Resumo:** AutoGen: framework de aplicações com múltiplos agentes conversacionais que combinam LLMs, humanos e ferramentas.  
  **Resultado:** Demonstra aplicações em vários domínios; evidência principalmente de estudos de caso.

- **Retrieval meets Long Context Large Language Models** (2023) — *Estudo empírico*  
  Peng Xu, Wei Ping, Xianchao Wu, Lawrence McAfee, Chen Zhu, Zihan Liu et al. (10 autores)  
  arXiv v1: 2023-10-04 · última versão (v2): 2024-01-23 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2310.03025](https://arxiv.org/abs/2310.03025)  
  **Resumo:** Compara recuperação e extensão de janela de contexto com GPT de 43B e Llama2-70B.  
  **Resultado:** Modelo com 4K de contexto e recuperação simples igualou um de 16K ajustado, com muito menos computação; recuperação ajuda qualquer tamanho de janela.

- **DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines** (2023) — *Método*  
  Omar Khattab, Arnav Singhvi, Paridhi Maheshwari, Zhiyuan Zhang, Keshav Santhanam, Sri Vardhamanan et al. (13 autores)  
  arXiv v1: 2023-10-05 · **Preprint (arXiv)** · [arXiv:2310.03714](https://arxiv.org/abs/2310.03714) · [código](https://github.com/stanfordnlp/dspy)  
  **Resumo:** DSPy: modelo de programação que trata pipelines de LMs como grafos declarativos e os otimiza por compilação.  
  **Resultado:** Pipelines auto-gerados superaram few-shot padrão (mais de 25% no GPT-3.5 e 65% no llama2-13b-chat) e demonstrações de especialistas. Preprint.

- **SWE-bench: Can Language Models Resolve Real-World GitHub Issues?** (2023) — *Benchmark/dataset*  
  Carlos E. Jimenez, John Yang, Alexander Wettig, Shunyu Yao, Kexin Pei, Ofir Press et al. (7 autores)  
  arXiv v1: 2023-10-10 · última versão (v3): 2024-11-11 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2310.06770](https://arxiv.org/abs/2310.06770)  
  **Resumo:** SWE-bench: 2.294 problemas reais de GitHub em 12 repositórios Python, resolvidos editando o código.  
  **Resultado:** O melhor modelo da época (Claude 2) resolveu apenas 1,96%; benchmark central para agentes de código.

- **MemGPT: Towards LLMs as Operating Systems** (2023) — *Sistema*  
  Charles Packer, Sarah Wooders, Kevin Lin, Vivian Fang, Shishir G. Patil, Ion Stoica et al. (7 autores)  
  arXiv v1: 2023-10-12 · última versão (v2): 2024-02-12 · **Preprint (arXiv)** · [arXiv:2310.08560](https://arxiv.org/abs/2310.08560)  
  **Resumo:** MemGPT: gerenciamento de contexto virtual inspirado em sistemas operacionais, com camadas de memória e interrupções.  
  **Resultado:** Permite analisar documentos maiores que a janela e manter memória em chats multi-sessão. Preprint.

- **Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection** (2023) — *Método*  
  Akari Asai, Zeqiu Wu, Yizhong Wang, Avirup Sil, Hannaneh Hajishirzi  
  arXiv v1: 2023-10-17 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2310.11511](https://arxiv.org/abs/2310.11511)  
  **Resumo:** Self-RAG treina um LM para decidir quando recuperar e para criticar trechos e a própria geração com tokens de reflexão.  
  **Resultado:** Modelos de 7B e 13B superaram ChatGPT e Llama2-chat com recuperação em QA aberto, raciocínio e verificação de fatos, com ganhos de citação em geração longa.

- **Mixtral of Experts** (2024) — *Sistema*  
  Albert Q. Jiang, Alexandre Sablayrolles, Antoine Roux, Arthur Mensch, Blanche Savary, Chris Bamford et al. (26 autores)  
  arXiv v1: 2024-01-08 · **Preprint (arXiv)** · [arXiv:2401.04088](https://arxiv.org/abs/2401.04088)  
  **Resumo:** Mixtral 8x7B: MoE esparso com 8 especialistas por camada e 2 ativos por token (47B parâmetros, 13B ativos).  
  **Resultado:** Iguala ou supera Llama 2 70B e GPT-3.5 nos benchmarks avaliados; pesos abertos (Apache 2.0). Relatório técnico.

- **Corrective Retrieval Augmented Generation** (2024) — *Método*  
  Shi-Qi Yan, Jia-Chen Gu, Yun Zhu, Zhen-Hua Ling  
  arXiv v1: 2024-01-29 · última versão (v3): 2024-10-07 · **Preprint (arXiv)** · [arXiv:2401.15884](https://arxiv.org/abs/2401.15884)  
  **Resumo:** CRAG: avaliador leve da qualidade dos documentos recuperados aciona ações corretivas (refinar, buscar na web, descartar).  
  **Resultado:** Melhora significativa de abordagens RAG em quatro datasets curtos e longos. Preprint.

- **Adaptive-RAG: Learning to Adapt Retrieval-Augmented Large Language Models through Question Complexity** (2024) — *Método*  
  Soyeong Jeong, Jinheon Baek, Sukmin Cho, Sung Ju Hwang, Jong C. Park  
  arXiv v1: 2024-03-21 · última versão (v2): 2024-03-28 · **Revisado por pares**: North American Chapter of the Association for Computational Linguistics · [arXiv:2403.14403](https://arxiv.org/abs/2403.14403) · [código](https://github.com/starsuzi/Adaptive-RAG)  
  **Resumo:** Adaptive-RAG usa um classificador pequeno para escolher, pela complexidade da pergunta, entre não recuperar, recuperar uma vez ou recuperar iterativamente.  
  **Resultado:** Melhor equilíbrio entre eficiência e acurácia que baselines, incluindo outras abordagens adaptativas, em QA aberto.

- **Mixture-of-Agents Enhances Large Language Model Capabilities** (2024) — *Método*  
  Junlin Wang, Jue Wang, Ben Athiwaratkun, Ce Zhang, James Zou  
  arXiv v1: 2024-06-07 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2406.04692](https://arxiv.org/abs/2406.04692)  
  **Resumo:** Mixture-of-Agents: camadas de LLMs em que cada agente usa as respostas da camada anterior.  
  **Resultado:** 65,1% no AlpacaEval 2.0 só com modelos abertos, contra 57,5% do GPT-4 Omni — avaliação baseada em juiz LLM.

- **RouteLLM: Learning to Route LLMs with Preference Data** (2024) — *Método*  
  Isaac Ong, Amjad Almahairi, Vincent Wu, Wei-Lin Chiang, Tianhao Wu, Joseph E. Gonzalez et al. (8 autores)  
  arXiv v1: 2024-06-26 · última versão (v4): 2025-02-23 · **Preprint (arXiv)** · [arXiv:2406.18665](https://arxiv.org/abs/2406.18665)  
  **Resumo:** RouteLLM treina roteadores entre um modelo forte e um fraco usando dados de preferência humana.  
  **Resultado:** Reduz custos em mais de 2 vezes em alguns casos sem perda de qualidade e mantém desempenho ao trocar os modelos. Preprint.

- **AI Agents That Matter** (2024) — *Resultado negativo/crítica*  
  Sayash Kapoor, Benedikt Stroebl, Zachary S. Siegel, Nitya Nadgir, Arvind Narayanan  
  arXiv v1: 2024-07-01 · **Revisado por pares**: Trans. Mach. Learn. Res. · [arXiv:2407.01502](https://arxiv.org/abs/2407.01502)  
  **Resumo:** Analisa práticas de avaliação de agentes e mostra foco exclusivo em acurácia, holdouts inadequados e falta de reprodutibilidade.  
  **Resultado:** Agentes de ponta são desnecessariamente complexos e caros; otimização conjunta de custo e acurácia reduz muito o custo mantendo acurácia.

- **Retrieval Augmented Generation or Long-Context LLMs? A Comprehensive Study and Hybrid Approach** (2024) — *Estudo empírico*  
  Zhuowan Li, Cheng Li, Mingyang Zhang, Qiaozhu Mei, Michael Bendersky  
  arXiv v1: 2024-07-23 · última versão (v2): 2024-10-17 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2407.16833](https://arxiv.org/abs/2407.16833)  
  **Resumo:** Compara RAG e LLMs de contexto longo (Gemini-1.5, GPT-4) e propõe Self-Route, que escolhe por autorreflexão.  
  **Resultado:** Com recursos suficientes, contexto longo supera RAG em média, mas RAG custa muito menos; Self-Route reduz custo com desempenho comparável. Trilha industrial.

- **Why Do Multi-Agent LLM Systems Fail?** (2025) — *Resultado negativo/crítica*  
  Mert Cemri, Melissa Z. Pan, Shuyi Yang, Lakshya A. Agrawal, Bhavya Chopra, Rishabh Tiwari et al. (13 autores)  
  arXiv v1: 2025-03-17 · última versão (v3): 2025-10-26 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2503.13657](https://arxiv.org/abs/2503.13657)  
  **Resumo:** Constrói MAST, taxonomia de 14 modos de falha de sistemas multiagente, a partir de mais de 1.600 traços anotados em 7 frameworks (kappa = 0,88).  
  **Resultado:** Ganhos de sistemas multiagente em benchmarks costumam ser mínimos; falhas vêm de design, desalinhamento entre agentes e verificação.

- **Small Language Models are the Future of Agentic AI** (2025) — *Posição*  
  Peter Belcak, Greg Heinrich, Shizhe Diao, Yonggan Fu, Xin Dong, Saurav Muralidharan et al. (8 autores)  
  arXiv v1: 2025-06-02 · última versão (v3): 2026-09-22 · **Preprint (arXiv)** · [arXiv:2506.02153](https://arxiv.org/abs/2506.02153)  
  **Resumo:** Posição de que modelos pequenos (SLMs) bastam e são mais econômicos para a maioria das chamadas em sistemas agênticos.  
  **Resultado:** Propõe algoritmo de conversão LLM→SLM e sistemas heterogêneos; argumento sem validação experimental sistemática.

- **A Survey of Context Engineering for Large Language Models** (2025) — *Survey/revisão*  
  Lingrui Mei, Jiayu Yao, Yuyao Ge, Yiwei Wang, Baolong Bi, Yujun Cai et al. (15 autores)  
  arXiv v1: 2025-07-17 · última versão (v2): 2025-07-21 · **Preprint (arXiv)** · [arXiv:2507.13334](https://arxiv.org/abs/2507.13334)  
  **Resumo:** Survey que formaliza engenharia de contexto (recuperação, processamento e gestão de contexto; RAG, memória, ferramentas, multiagentes) a partir de mais de 1.400 artigos.  
  **Resultado:** Aponta assimetria: modelos entendem contextos complexos melhor do que geram saídas longas equivalentes. Preprint.

<a id="d"></a>

### Eixo D — Recuperação de informação e bases de conhecimento

- **Cumulated gain-based evaluation of IR techniques** (2002) — *Fundacional*  
  Kalervo Järvelin, Jaana Kekäläinen  
  Publicação: 2002-10 · **Revisado por pares**: ACM Transactions on Information Systems · [DOI 10.1145/582415.582418](https://doi.org/10.1145/582415.582418)  
  **Resumo:** Define as medidas de ganho cumulativo (CG, DCG e nDCG) para relevância graduada.  
  **Resultado:** Base da métrica NDCG usada para avaliar recuperadores e rerankers.

- **Reciprocal rank fusion outperforms condorcet and individual rank learning methods** (2009) — *Fundacional*  
  Gordon V. Cormack, Charles L A Clarke, Stefan Buettcher  
  Publicação: 2009-07-19 · **Revisado por pares**: Proceedings of the 32nd international ACM SIGIR conference on Research and development in information retrieval · [DOI 10.1145/1571941.1572114](https://doi.org/10.1145/1571941.1572114)  
  **Resumo:** Reciprocal Rank Fusion: combina listas ranqueadas somando 1/(k + posição) de cada documento.  
  **Resultado:** Superou Condorcet e métodos individuais de learning-to-rank; é o método padrão de fusão em busca híbrida.

- **The Probabilistic Relevance Framework: BM25 and Beyond** (2009) — *Fundacional*  
  Stephen Robertson, Hugo Zaragoza  
  Publicação: 2009-09-17 · **Revisado por pares**: Foundations and Trends® in Information Retrieval · [DOI 10.1561/1500000019](https://doi.org/10.1561/1500000019)  
  **Resumo:** Monografia que deriva o Probabilistic Relevance Framework e as funções de ranqueamento BM25 e BM25F.  
  **Resultado:** Base teórica do baseline lexical que segue competitivo em benchmarks modernos (ver BEIR).

- **Efficient and robust approximate nearest neighbor search using Hierarchical Navigable Small World graphs** (2016) — *Fundacional*  
  Yu. A. Malkov, D. A. Yashunin  
  arXiv v1: 2016-03-30 · última versão (v4): 2018-08-14 · **Revisado por pares**: IEEE Transactions on Pattern Analysis and Machine Intelligence · [arXiv:1603.09320](https://arxiv.org/abs/1603.09320) · [DOI 10.1109/TPAMI.2018.2889473](https://doi.org/10.1109/TPAMI.2018.2889473)  
  **Resumo:** HNSW: grafos hierárquicos navegáveis para busca aproximada de vizinhos mais próximos com complexidade logarítmica.  
  **Resultado:** Supera fortemente soluções abertas anteriores, sobretudo em alta revocação; base da maioria dos bancos vetoriais.

- **MS MARCO: A Human Generated MAchine Reading COmprehension Dataset** (2016) — *Benchmark/dataset*  
  Payal Bajaj, Daniel Campos, Nick Craswell, Li Deng, Jianfeng Gao, Xiaodong Liu et al. (15 autores)  
  arXiv v1: 2016-11-28 · última versão (v3): 2018-10-31 · **Workshop**: CoCo@NIPS 2016 (workshop) · [arXiv:1611.09268](https://arxiv.org/abs/1611.09268)  
  **Resumo:** MS MARCO: ~1 milhão de perguntas reais do Bing com respostas humanas e 8,8 milhões de trechos.  
  **Resultado:** Dataset de referência para treinar e avaliar recuperadores e rerankers. Publicado em workshop.

- **Billion-scale similarity search with GPUs** (2017) — *Fundacional*  
  Jeff Johnson, Matthijs Douze, Hervé Jégou  
  arXiv v1: 2017-02-28 · **Revisado por pares**: IEEE Transactions on Big Data · [arXiv:1702.08734](https://arxiv.org/abs/1702.08734) · [DOI 10.1109/tbdata.2019.2921572](https://doi.org/10.1109/tbdata.2019.2921572)  
  **Resumo:** FAISS em GPU: k-seleção eficiente e busca exata, aproximada e por quantização de produto.  
  **Resultado:** 8,5 vezes mais rápido que o estado da arte em GPU; grafo k-NN de 1 bilhão de vetores em menos de 12 horas em 4 GPUs.

- **ANN-Benchmarks: A Benchmarking Tool for Approximate Nearest Neighbor Algorithms** (2018) — *Benchmark/dataset*  
  Martin Aumüller, Erik Bernhardsson, Alexander Faithfull  
  arXiv v1: 2018-07-15 · última versão (v2): 2018-07-17 · **Revisado por pares**: Similarity Search and Applications · [arXiv:1807.05614](https://arxiv.org/abs/1807.05614) · [DOI 10.1007/978-3-319-68474-1_3](https://doi.org/10.1007/978-3-319-68474-1_3)  
  **Resumo:** ANN-Benchmarks: ferramenta padronizada para comparar algoritmos de vizinhos aproximados em memória.  
  **Resultado:** Abordagens muito diferentes chegam a trade-offs qualidade/desempenho comparáveis.

- **DiskANN : Fast Accurate Billion-point Nearest Neighbor Search on a Single Node** (2019) — *Método*  
  Suhas Jayaram Subramanya, Devvrit, Rohan Kadekodi, Ravishankar Krishnaswamy, Harsha Vardhan Simhadri  
  Publicação: 2019 · **Venue não confirmado**: NeurIPS 2019 — venue não confirmado automaticamente · [registro](https://www.semanticscholar.org/paper/ae3db2312066a6a6696aeb7cad2778c193c017ea)  
  **Resumo:** DiskANN: índice em grafo (Vamana) armazenado em SSD para busca de vizinhos aproximados em bilhões de pontos num único nó.  
  **Resultado:** Permite busca bilionária com pouca memória RAM; relevante quando o índice não cabe em memória. Venue não confirmado automaticamente.

- **Passage Re-ranking with BERT** (2019) — *Fundacional*  
  Rodrigo Nogueira, Kyunghyun Cho  
  arXiv v1: 2019-01-13 · última versão (v5): 2020-04-14 · **Preprint (arXiv)** · [arXiv:1901.04085](https://arxiv.org/abs/1901.04085) · [código](https://github.com/nyu-dl/dl4marco-bert)  
  **Resumo:** Reimplementação simples do BERT como reranker de trechos.  
  **Resultado:** Topo do MS MARCO com ganho relativo de 27% em MRR@10 sobre o estado da arte anterior. Preprint.

- **Accelerating Large-Scale Inference with Anisotropic Vector Quantization** (2019) — *Método*  
  Ruiqi Guo, Philip Sun, Erik Lindgren, Quan Geng, David Simcha, Felix Chern et al. (7 autores)  
  arXiv v1: 2019-08-27 · última versão (v5): 2020-12-04 · **Revisado por pares**: ICML 2020 (DBLP conf/icml/GuoSLGSCK20) · [arXiv:1908.10396](https://arxiv.org/abs/1908.10396)  
  **Resumo:** ScaNN: quantização anisotrópica que penaliza mais o erro na direção paralela ao ponto, para busca por produto interno máximo.  
  **Resultado:** Estado da arte nos benchmarks do ann-benchmarks.com na época.

- **Dense Passage Retrieval for Open-Domain Question Answering** (2020) — *Fundacional*  
  Vladimir Karpukhin, Barlas Oğuz, Sewon Min, Patrick Lewis, Ledell Wu, Sergey Edunov et al. (8 autores)  
  arXiv v1: 2020-04-10 · última versão (v3): 2020-09-30 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2004.04906](https://arxiv.org/abs/2004.04906) · [DOI 10.18653/v1/2020.emnlp-main.550](https://doi.org/10.18653/v1/2020.emnlp-main.550)  
  **Resumo:** Dense Passage Retrieval: dual-encoder treinado com poucos pares pergunta-trecho.  
  **Resultado:** Supera um BM25 forte em 9–19 pontos absolutos de acurácia top-20 e estabelece novo estado da arte em QA aberto.

- **ColBERT: Efficient and Effective Passage Search via Contextualized Late Interaction over BERT** (2020) — *Fundacional*  
  Omar Khattab, Matei Zaharia  
  arXiv v1: 2020-04-27 · última versão (v2): 2020-06-04 · **Revisado por pares**: Annual International ACM SIGIR Conference on Research and Development in Information Retrieval · [arXiv:2004.12832](https://arxiv.org/abs/2004.12832) · [DOI 10.1145/3397271.3401075](https://doi.org/10.1145/3397271.3401075)  
  **Resumo:** ColBERT: interação tardia — codifica consulta e documento separadamente e compara em nível de token.  
  **Resultado:** Eficácia competitiva com rankers BERT, duas ordens de grandeza mais rápido e quatro ordens com menos FLOPs por consulta.

- **BEIR: A Heterogenous Benchmark for Zero-shot Evaluation of Information Retrieval Models** (2021) — *Benchmark/dataset*  
  Nandan Thakur, Nils Reimers, Andreas Rücklé, Abhishek Srivastava, Iryna Gurevych  
  arXiv v1: 2021-04-17 · última versão (v4): 2021-10-21 · **Revisado por pares**: NeurIPS Datasets and Benchmarks · [arXiv:2104.08663](https://arxiv.org/abs/2104.08663) · [código](https://github.com/UKPLab/beir)  
  **Resumo:** BEIR: 18 datasets heterogêneos para avaliar recuperação zero-shot; compara 10 sistemas lexicais, esparsos, densos, de interação tardia e rerankers.  
  **Resultado:** BM25 é um baseline robusto; rerankers e interação tardia têm a melhor média, a custo computacional alto; modelos densos generalizam pior fora do domínio.

- **SPLADE: Sparse Lexical and Expansion Model for First Stage Ranking** (2021) — *Método*  
  Thibault Formal, Benjamin Piwowarski, Stéphane Clinchant  
  arXiv v1: 2021-07-12 · **Revisado por pares**: Annual International ACM SIGIR Conference on Research and Development in Information Retrieval · [arXiv:2107.05720](https://arxiv.org/abs/2107.05720) · [DOI 10.1145/3404835.3463098](https://doi.org/10.1145/3404835.3463098)  
  **Resumo:** SPLADE: representações esparsas aprendidas com regularização de esparsidade e expansão de termos, usando índice invertido.  
  **Resultado:** Competitivo com métodos densos e esparsos de ponta, com controle do trade-off eficiência/eficácia.

- **ColBERTv2: Effective and Efficient Retrieval via Lightweight Late Interaction** (2021) — *Método*  
  Keshav Santhanam, Omar Khattab, Jon Saad-Falcon, Christopher Potts, Matei Zaharia  
  arXiv v1: 2021-12-02 · última versão (v3): 2022-07-10 · **Revisado por pares**: North American Chapter of the Association for Computational Linguistics · [arXiv:2112.01488](https://arxiv.org/abs/2112.01488) · [DOI 10.18653/v1/2022.naacl-main.272](https://doi.org/10.18653/v1/2022.naacl-main.272)  
  **Resumo:** ColBERTv2: compressão residual agressiva e supervisão com destilação de ruído para interação tardia.  
  **Resultado:** Estado da arte dentro e fora do domínio de treino, com 6–10 vezes menos espaço.

- **Unsupervised Dense Information Retrieval with Contrastive Learning** (2021) — *Método*  
  Gautier Izacard, Mathilde Caron, Lucas Hosseini, Sebastian Riedel, Piotr Bojanowski, Armand Joulin et al. (7 autores)  
  arXiv v1: 2021-12-16 · última versão (v4): 2022-08-29 · **Revisado por pares**: Trans. Mach. Learn. Res. · [arXiv:2112.09118](https://arxiv.org/abs/2112.09118)  
  **Resumo:** Contriever: recuperador denso treinado sem supervisão por aprendizado contrastivo.  
  **Resultado:** Supera BM25 em 11 de 15 datasets do BEIR em Recall@100 e transfere bem entre idiomas.

- **Least-to-Most Prompting Enables Complex Reasoning in Large Language Models** (2022) — *Método*  
  Denny Zhou, Nathanael Schärli, Le Hou, Jason Wei, Nathan Scales, Xuezhi Wang et al. (11 autores)  
  arXiv v1: 2022-05-21 · última versão (v3): 2023-04-16 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2205.10625](https://arxiv.org/abs/2205.10625)  
  **Resumo:** Least-to-most prompting: decompõe um problema em subproblemas resolvidos em sequência.  
  **Resultado:** Generaliza para problemas mais difíceis que os exemplos; resolve o SCAN em qualquer divisão com ≥99% usando 14 exemplos.

- **Matryoshka Representation Learning** (2022) — *Método*  
  Aditya Kusupati, Gantavya Bhatt, Aniket Rege, Matthew Wallingford, Aditya Sinha, Vivek Ramanujan et al. (11 autores)  
  arXiv v1: 2022-05-26 · última versão (v4): 2024-02-08 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2205.13147](https://arxiv.org/abs/2205.13147) · [DOI 10.52202/068431-2192](https://doi.org/10.52202/068431-2192) · [código](https://github.com/RAIVNLab/MRL)  
  **Resumo:** Matryoshka Representation Learning: embeddings que mantêm qualidade quando truncados em dimensões menores.  
  **Resultado:** Até 14 vezes menor para a mesma acurácia no ImageNet-1K e até 14 vezes de aceleração em recuperação.

- **Measuring and Narrowing the Compositionality Gap in Language Models** (2022) — *Método*  
  Ofir Press, Muru Zhang, Sewon Min, Ludwig Schmidt, Noah A. Smith, Mike Lewis  
  arXiv v1: 2022-10-07 · última versão (v3): 2023-10-17 · **Revisado por pares**: Findings of EMNLP 2023 (comentário do arXiv) · [arXiv:2210.03350](https://arxiv.org/abs/2210.03350)  
  **Resumo:** Mede o «compositionality gap» (acertar subperguntas mas errar a composta) e propõe self-ask, que pode usar busca nas subperguntas.  
  **Resultado:** O gap não diminui com a escala; self-ask com busca melhora a acurácia.

- **MTEB: Massive Text Embedding Benchmark** (2022) — *Benchmark/dataset*  
  Niklas Muennighoff, Nouamane Tazi, Loïc Magne, Nils Reimers  
  arXiv v1: 2022-10-13 · última versão (v3): 2023-03-19 · **Revisado por pares**: Conference of the European Chapter of the Association for Computational Linguistics · [arXiv:2210.07316](https://arxiv.org/abs/2210.07316) · [DOI 10.18653/v1/2023.eacl-main.148](https://doi.org/10.18653/v1/2023.eacl-main.148) · [código](https://github.com/embeddings-benchmark/mteb)  
  **Resumo:** MTEB: 8 tarefas, 58 datasets e 112 idiomas para avaliar embeddings de texto; 33 modelos avaliados.  
  **Resultado:** Nenhum método domina todas as tarefas — escolher embedding exige avaliação no próprio domínio.

- **Text Embeddings by Weakly-Supervised Contrastive Pre-training** (2022) — *Método*  
  Liang Wang, Nan Yang, Xiaolong Huang, Binxing Jiao, Linjun Yang, Daxin Jiang et al. (8 autores)  
  arXiv v1: 2022-12-07 · última versão (v2): 2024-02-22 · **Preprint (arXiv)** · [arXiv:2212.03533](https://arxiv.org/abs/2212.03533)  
  **Resumo:** E5: embeddings treinados por contraste com supervisão fraca num grande conjunto de pares (CCPairs).  
  **Resultado:** Primeiro modelo a superar BM25 no BEIR sem dados rotulados; melhor resultado no MTEB após ajuste, superando modelos 40 vezes maiores. Preprint.

- **Precise Zero-Shot Dense Retrieval without Relevance Labels** (2022) — *Método*  
  Luyu Gao, Xueguang Ma, Jimmy Lin, Jamie Callan  
  arXiv v1: 2022-12-20 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2212.10496](https://arxiv.org/abs/2212.10496) · [DOI 10.18653/v1/2023.acl-long.99](https://doi.org/10.18653/v1/2023.acl-long.99)  
  **Resumo:** HyDE: o LLM gera um documento hipotético para a consulta e o embedding desse documento é usado para buscar documentos reais.  
  **Resultado:** Supera o Contriever e se aproxima de recuperadores ajustados em várias tarefas e idiomas, sem rótulos de relevância.

- **Interleaving Retrieval with Chain-of-Thought Reasoning for Knowledge-Intensive Multi-Step Questions** (2022) — *Método*  
  Harsh Trivedi, Niranjan Balasubramanian, Tushar Khot, Ashish Sabharwal  
  arXiv v1: 2022-12-20 · última versão (v2): 2023-06-23 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2212.10509](https://arxiv.org/abs/2212.10509) · [código](https://github.com/stonybrooknlp/ircot)  
  **Resumo:** IRCoT intercala recuperação e passos de chain-of-thought em QA multi-hop.  
  **Resultado:** Com GPT-3, melhora a recuperação em até 21 pontos e o QA em até 15 pontos em HotpotQA, 2WikiMultihopQA, MuSiQue e IIRC; reduz alucinação.

- **Query2doc: Query Expansion with Large Language Models** (2023) — *Método*  
  Liang Wang, Nan Yang, Furu Wei  
  arXiv v1: 2023-03-14 · última versão (v2): 2023-10-11 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2303.07678](https://arxiv.org/abs/2303.07678)  
  **Resumo:** Query2doc: expande a consulta com pseudo-documentos gerados por LLM.  
  **Resultado:** Melhora o BM25 em 3–15% no MS MARCO e TREC DL sem ajuste de modelo; também ajuda recuperadores densos.

- **Is ChatGPT Good at Search? Investigating Large Language Models as Re-Ranking Agents** (2023) — *Método*  
  Weiwei Sun, Lingyong Yan, Xinyu Ma, Shuaiqiang Wang, Pengjie Ren, Zhumin Chen et al. (8 autores)  
  arXiv v1: 2023-04-19 · última versão (v3): 2024-12-28 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2304.09542](https://arxiv.org/abs/2304.09542) · [código](https://github.com/sunnweiwei/RankGPT)  
  **Resumo:** Avalia ChatGPT e GPT-4 como rerankers por permutação (RankGPT) e cria o conjunto NovelEval contra contaminação.  
  **Resultado:** LLMs instruídos igualam ou superam rerankers supervisionados; um modelo destilado de 440M superou um supervisionado de 3B no BEIR.

- **Unifying Large Language Models and Knowledge Graphs: A Roadmap** (2023) — *Survey/revisão*  
  Shirui Pan, Linhao Luo, Yufei Wang, Chen Chen, Jiapu Wang, Xindong Wu  
  arXiv v1: 2023-06-14 · última versão (v3): 2024-01-25 · **Revisado por pares**: IEEE Transactions on Knowledge and Data Engineering (TKDE) 2024 · [arXiv:2306.08302](https://arxiv.org/abs/2306.08302) · [DOI 10.1109/TKDE.2024.3352100](https://doi.org/10.1109/TKDE.2024.3352100)  
  **Resumo:** Roadmap para unificar LLMs e grafos de conhecimento: KG para LLMs, LLM para KGs e sistemas sinérgicos.  
  **Resultado:** Revisão e agenda; publicado no IEEE TKDE (versão curta).

- **Dense X Retrieval: What Retrieval Granularity Should We Use?** (2023) — *Estudo empírico*  
  Tong Chen, Hongwei Wang, Sihao Chen, Wenhao Yu, Kaixin Ma, Xinran Zhao et al. (8 autores)  
  arXiv v1: 2023-12-11 · última versão (v3): 2024-10-04 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2312.06648](https://arxiv.org/abs/2312.06648)  
  **Resumo:** Compara unidades de indexação (documento, trecho, sentença) e propõe proposições atômicas para recuperação densa.  
  **Resultado:** Indexar por proposições supera trechos na recuperação e melhora QA a jusante com orçamento de contexto fixo.

- **Seven Failure Points When Engineering a Retrieval Augmented Generation System** (2024) — *Estudo empírico*  
  Scott Barnett, Stefanus Kurniawan, Srikanth Thudumu, Zach Brannelly, Mohamed Abdelrazek  
  arXiv v1: 2024-01-11 · **Revisado por pares**: 2024 IEEE/ACM 3rd International Conference on AI Engineering – Software Engineering for AI (CAIN) · [arXiv:2401.05856](https://arxiv.org/abs/2401.05856) · [DOI 10.1145/3644815.3644945](https://doi.org/10.1145/3644815.3644945)  
  **Resumo:** Relato de experiência com três sistemas RAG (pesquisa, educação, biomedicina) que identifica sete pontos de falha.  
  **Resultado:** Validação de RAG só é viável em operação e a robustez evolui em vez de ser projetada de início.

- **RAPTOR: Recursive Abstractive Processing for Tree-Organized Retrieval** (2024) — *Método*  
  Parth Sarthi, Salman Abdullah, Aditi Tuli, Shubh Khanna, Anna Goldie, Christopher D. Manning  
  arXiv v1: 2024-01-31 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2401.18059](https://arxiv.org/abs/2401.18059)  
  **Resumo:** RAPTOR: agrupa e resume trechos recursivamente, formando uma árvore de abstrações consultada na recuperação.  
  **Resultado:** Ganhos sobre RAG tradicional em várias tarefas; com GPT-4, +20 pontos absolutos no QuALITY.

- **From Local to Global: A Graph RAG Approach to Query-Focused Summarization** (2024) — *Método*  
  Darren Edge, Ha Trinh, Newman Cheng, Joshua Bradley, Alex Chao, Apurva Mody et al. (10 autores)  
  arXiv v1: 2024-04-24 · última versão (v2): 2025-02-19 · **Preprint (arXiv)** · [arXiv:2404.16130](https://arxiv.org/abs/2404.16130)  
  **Resumo:** GraphRAG: um LLM constrói um grafo de entidades e resumos de comunidades; cada resumo gera respostas parciais que são consolidadas.  
  **Resultado:** Em perguntas globais de «sensemaking» sobre corpora de ~1 milhão de tokens, melhora abrangência e diversidade das respostas sobre RAG convencional. Avaliação por juiz LLM; custo de indexação alto. Preprint.

- **Evaluation of Retrieval-Augmented Generation: A Survey** (2024) — *Survey/revisão*  
  Hao Yu, Aoran Gan, Kai Zhang, Shiwei Tong, Qi Liu, Zhaofeng Liu  
  arXiv v1: 2024-05-13 · última versão (v2): 2024-07-03 · **Preprint (arXiv)** · [arXiv:2405.07437](https://arxiv.org/abs/2405.07437) · [DOI 10.1007/978-981-96-1024-2_8](https://doi.org/10.1007/978-981-96-1024-2_8)  
  **Resumo:** Survey de avaliação de RAG que propõe um processo unificado (Auepora) e compara métricas de recuperação e geração.  
  **Resultado:** Mapa de benchmarks e limitações; sem experimento próprio.

- **HippoRAG: Neurobiologically Inspired Long-Term Memory for Large Language Models** (2024) — *Método*  
  Bernal Jiménez Gutiérrez, Yiheng Shu, Yu Gu, Michihiro Yasunaga, Yu Su  
  arXiv v1: 2024-05-23 · última versão (v3): 2025-01-14 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2405.14831](https://arxiv.org/abs/2405.14831) · [código](https://github.com/OSU-NLP-Group/HippoRAG)  
  **Resumo:** HippoRAG combina LLM, grafo de conhecimento e Personalized PageRank, inspirado na teoria de indexação do hipocampo.  
  **Resultado:** Até 20% melhor em QA multi-hop; recuperação de uma etapa iguala o IRCoT iterativo sendo 10–30 vezes mais barata e 6–13 vezes mais rápida.

- **ColPali: Efficient Document Retrieval with Vision Language Models** (2024) — *Método*  
  Manuel Faysse, Hugues Sibille, Tony Wu, Bilel Omrani, Gautier Viaud, Céline Hudelot et al. (7 autores)  
  arXiv v1: 2024-06-27 · última versão (v6): 2025-02-28 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2407.01449](https://arxiv.org/abs/2407.01449) · [código](https://hf.co/vidore)  
  **Resumo:** ColPali indexa imagens de páginas com um modelo de visão-linguagem e interação tardia multi-vetor; introduz o benchmark ViDoRe.  
  **Resultado:** Supera pipelines de recuperação documental modernos, sendo mais simples e rápido de indexar — relevante para PDFs com tabelas e figuras.

- **Graph Retrieval-Augmented Generation: A Survey** (2024) — *Survey/revisão*  
  Boci Peng, Yun Zhu, Yongchao Liu, Xiaohe Bo, Haizhou Shi, Chuntao Hong et al. (8 autores)  
  arXiv v1: 2024-08-15 · última versão (v2): 2024-09-10 · **Revisado por pares**: ACM Trans. Inf. Syst. · [arXiv:2408.08921](https://arxiv.org/abs/2408.08921) · [DOI 10.1145/3777378](https://doi.org/10.1145/3777378) · [código](https://github.com/pengboci/GraphRAG-Survey)  
  **Resumo:** Primeiro survey de GraphRAG: indexação baseada em grafo, recuperação guiada por grafo e geração aumentada por grafo.  
  **Resultado:** Mapa de técnicas, aplicações e avaliação; sem experimento próprio.

- **Late Chunking: Contextual Chunk Embeddings Using Long-Context Embedding Models** (2024) — *Método*  
  Michael Günther, Isabelle Mohr, Daniel James Williams, Bo Wang, Han Xiao  
  arXiv v1: 2024-09-07 · última versão (v3): 2025-07-07 · **Preprint (arXiv)** · [arXiv:2409.04701](https://arxiv.org/abs/2409.04701)  
  **Resumo:** Late chunking: codifica o documento longo inteiro e só depois agrupa os embeddings de token por trecho.  
  **Resultado:** Embeddings de trecho com contexto completo e melhores resultados em várias tarefas, sem treino adicional. Preprint.

- **LightRAG: Simple and Fast Retrieval-Augmented Generation** (2024) — *Método*  
  Zirui Guo, Lianghao Xia, Yanhua Yu, Tu Ao, Chao Huang  
  arXiv v1: 2024-10-08 · última versão (v3): 2025-04-28 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2410.05779](https://arxiv.org/abs/2410.05779) · [código](https://github.com/HKUDS/LightRAG)  
  **Resumo:** LightRAG integra estruturas de grafo à indexação, com recuperação em dois níveis e atualização incremental.  
  **Resultado:** Ganhos de acurácia e eficiência de recuperação sobre abordagens existentes, avaliados principalmente com juiz LLM.

<a id="e"></a>

### Eixo E — Ciência de Dados, experimentação e otimização

- **Approximate Statistical Tests for Comparing Supervised Classification Learning Algorithms** (1998) — *Fundacional*  
  Thomas G. Dietterich  
  Publicação: 1998-10-01 · **Revisado por pares**: Neural Computation · [DOI 10.1162/089976698300017197](https://doi.org/10.1162/089976698300017197)  
  **Resumo:** Compara testes estatísticos para decidir se um classificador supera outro.  
  **Resultado:** O t-test com reamostragem repetida tem erro tipo I alto; McNemar e o 5x2cv t-test são recomendados.

- **Statistical Comparisons of Classifiers over Multiple Data Sets** (2006) — *Fundacional*  
  J. Demšar  
  Publicação: 2006 · **Revisado por pares**: Journal of Machine Learning Research 7 (2006) · [registro](https://jmlr.org/papers/v7/demsar06a.html)  
  **Resumo:** Analisa como comparar classificadores em múltiplos datasets.  
  **Resultado:** Recomenda Wilcoxon signed-rank para dois classificadores e Friedman com pós-teste de Nemenyi para vários.

- **Bias in error estimation when using cross-validation for model selection** (2006) — *Estudo empírico*  
  Sudhir Varma, Richard Simon  
  Publicação: 2006-02-23 · **Revisado por pares**: BMC Bioinformatics · [DOI 10.1186/1471-2105-7-91](https://doi.org/10.1186/1471-2105-7-91)  
  **Resumo:** Mostra o viés de usar a mesma validação cruzada para ajustar e estimar o erro.  
  **Resultado:** A estimativa fica otimista; validação cruzada aninhada dá estimativa quase não enviesada.

- **Controlled experiments on the web: survey and practical guide** (2008) — *Fundacional*  
  Ron Kohavi, Roger Longbotham, Dan Sommerfield, Randal M. Henne  
  Publicação: 2008-07-30 · **Revisado por pares**: Data Mining and Knowledge Discovery · [DOI 10.1007/s10618-008-0114-1](https://doi.org/10.1007/s10618-008-0114-1)  
  **Resumo:** Guia prático de experimentos controlados online (testes A/B): desenho, tamanho de amostra, armadilhas e cultura de experimentação.  
  **Resultado:** Referência metodológica para validar mudanças de produto com causalidade, incluindo testes A/A e cuidados com métricas.

- **Causal inference in statistics: An overview** (2009) — *Fundacional*  
  Judea Pearl  
  Publicação: 2009-01-01 · **Revisado por pares**: Statistics Surveys · [DOI 10.1214/09-SS057](https://doi.org/10.1214/09-SS057)  
  **Resumo:** Visão geral da inferência causal estrutural: modelos causais estruturais, do-cálculo e contrafactuais.  
  **Resultado:** Base conceitual para distinguir correlação de causalidade em análises operacionais.

- **Algorithms for Hyper-Parameter Optimization** (2011) — *Fundacional*  
  J. Bergstra, R. Bardenet, Yoshua Bengio, B. Kégl  
  Publicação: 2011 · **Revisado por pares**: NeurIPS 2011 · [registro](https://dblp.org/rec/conf/nips/BergstraBBK11)  
  **Resumo:** Propõe otimização sequencial baseada em modelos (processo gaussiano e Tree-structured Parzen Estimator) para hiperparâmetros.  
  **Resultado:** Supera busca aleatória e manual no ajuste de redes; o TPE é o algoritmo padrão de ferramentas como Hyperopt e Optuna.

- **Surrogate-assisted evolutionary computation: Recent advances and future challenges** (2011) — *Survey/revisão*  
  Yaochu Jin  
  Publicação: 2011-06 · **Revisado por pares**: Swarm and Evolutionary Computation · [DOI 10.1016/j.swevo.2011.05.001](https://doi.org/10.1016/j.swevo.2011.05.001)  
  **Resumo:** Revisão de computação evolutiva assistida por modelos substitutos (surrogates).  
  **Resultado:** Organiza estratégias de gestão de surrogates e direções futuras.

- **Random Search for Hyper-Parameter Optimization** (2012) — *Fundacional*  
  J. Bergstra, Yoshua Bengio  
  Publicação: 2012 · **Revisado por pares**: Journal of Machine Learning Research 13 (2012) · [registro](https://jmlr.org/papers/v13/bergstra12a.html)  
  **Resumo:** Compara busca aleatória e busca em grade para hiperparâmetros.  
  **Resultado:** Busca aleatória é mais eficiente porque poucos hiperparâmetros importam em cada problema.

- **Practical Bayesian Optimization of Machine Learning Algorithms** (2012) — *Fundacional*  
  Jasper Snoek, Hugo Larochelle, Ryan P. Adams  
  arXiv v1: 2012-06-13 · última versão (v2): 2012-08-29 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:1206.2944](https://arxiv.org/abs/1206.2944)  
  **Resumo:** Otimização bayesiana com processos gaussianos para ajustar hiperparâmetros, considerando custo variável e paralelismo.  
  **Resultado:** Atinge ou supera ajuste de especialistas em LDA, SVM estruturado e redes convolucionais.

- **Leakage in data mining: Formulation, detection, and avoidance** (2012) — *Fundacional*  
  Shachar Kaufman, Saharon Rosset, Claudia Perlich, Ori Stitelman  
  Publicação: 2012-12 · **Revisado por pares**: ACM Transactions on Knowledge Discovery from Data · [DOI 10.1145/2382577.2382579](https://doi.org/10.1145/2382577.2382579)  
  **Resumo:** Define formalmente vazamento em mineração de dados e propõe metodologia para evitá-lo (separação aprender–prever).  
  **Resultado:** Base conceitual para validação point-in-time e prevenção de vazamento temporal.

- **Improving the sensitivity of online controlled experiments by utilizing pre-experiment data** (2013) — *Método*  
  Alex Deng, Ya Xu, Ron Kohavi, Toby Walker  
  Publicação: 2013-02-04 · **Revisado por pares**: Proceedings of the sixth ACM international conference on Web search and data mining · [DOI 10.1145/2433396.2433413](https://doi.org/10.1145/2433396.2433413)  
  **Resumo:** CUPED: usa dados pré-experimento como covariável para reduzir a variância de experimentos online.  
  **Resultado:** Redução substancial de variância em experimentos do Bing, permitindo detectar efeitos menores com o mesmo tráfego.

- **Metaheuristics—the metaphor exposed** (2013) — *Resultado negativo/crítica*  
  Kenneth Sörensen  
  Publicação: 2013-02-08 · **Revisado por pares**: International Transactions in Operational Research · [DOI 10.1111/itor.12001](https://doi.org/10.1111/itor.12001)  
  **Resumo:** Crítica a metaheurísticas baseadas em metáforas naturais.  
  **Resultado:** Muitas não trazem novidade real e escondem a semelhança com métodos conhecidos sob nova terminologia.

- **Human-level control through deep reinforcement learning** (2015) — *Fundacional*  
  Volodymyr Mnih, Koray Kavukcuoglu, David Silver, Andrei A. Rusu, Joel Veness, Marc G. Bellemare et al. (19 autores)  
  Publicação: 2015-02-25 · **Revisado por pares**: Nature · [DOI 10.1038/nature14236](https://doi.org/10.1038/nature14236)  
  **Resumo:** Deep Q-Network: Q-learning com redes profundas, replay de experiência e rede-alvo.  
  **Resultado:** Desempenho de nível humano em jogos de Atari a partir de pixels.

- **Recursive Partitioning for Heterogeneous Causal Effects** (2015) — *Método*  
  Susan Athey, Guido Imbens  
  arXiv v1: 2015-04-05 · última versão (v3): 2015-12-30 · **Revisado por pares**: Proceedings of the National Academy of Sciences of the United States of America · [arXiv:1504.01132](https://arxiv.org/abs/1504.01132) · [DOI 10.1073/pnas.1510489113](https://doi.org/10.1073/pnas.1510489113)  
  **Resumo:** Árvores causais: partição recursiva para estimar efeitos heterogêneos de tratamento com inferência válida.  
  **Resultado:** Novos critérios de validação cruzada para efeitos causais; publicado no PNAS.

- **Pointer Networks** (2015) — *Fundacional*  
  Oriol Vinyals, Meire Fortunato, Navdeep Jaitly  
  arXiv v1: 2015-06-09 · última versão (v2): 2017-01-02 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:1506.03134](https://arxiv.org/abs/1506.03134)  
  **Resumo:** Pointer Networks: atenção como ponteiro para saídas que são posições da entrada.  
  **Resultado:** Aprende soluções aproximadas para envoltória convexa, triangulação de Delaunay e TSP planar.

- **XGBoost: A Scalable Tree Boosting System** (2016) — *Fundacional*  
  Tianqi Chen, Carlos Guestrin  
  arXiv v1: 2016-03-09 · última versão (v3): 2016-06-10 · **Revisado por pares**: Knowledge Discovery and Data Mining · [arXiv:1603.02754](https://arxiv.org/abs/1603.02754) · [DOI 10.1145/2939672.2939785](https://doi.org/10.1145/2939672.2939785)  
  **Resumo:** XGBoost: sistema escalável de gradient boosting com algoritmo para dados esparsos e sketch de quantis.  
  **Resultado:** Escala a bilhões de exemplos com poucos recursos; referência para dados tabulares.

- **Hyperband: A Novel Bandit-Based Approach to Hyperparameter Optimization** (2016) — *Método*  
  Lisha Li, Kevin Jamieson, Giulia DeSalvo, Afshin Rostamizadeh, Ameet Talwalkar  
  arXiv v1: 2016-03-21 · última versão (v4): 2018-06-18 · **Revisado por pares**: Journal of Machine Learning Research 18 (2018) 1-52 · [arXiv:1603.06560](https://arxiv.org/abs/1603.06560)  
  **Resumo:** Hyperband: alocação adaptativa de recursos com parada antecipada, formulada como problema de bandit.  
  **Resultado:** Aceleração de mais de uma ordem de grandeza sobre otimização bayesiana em vários problemas.

- **Double/Debiased Machine Learning for Treatment and Causal Parameters** (2016) — *Fundacional*  
  Victor Chernozhukov, Denis Chetverikov, Mert Demirer, Esther Duflo, Christian Hansen, Whitney Newey et al. (7 autores)  
  arXiv v1: 2016-07-30 · última versão (v7): 2024-11-03 · **Preprint (arXiv)** · [arXiv:1608.00060](https://arxiv.org/abs/1608.00060)  
  **Resumo:** Double/Debiased Machine Learning: estimadores ortogonais com cross-fitting para parâmetros causais usando ML nos componentes auxiliares.  
  **Resultado:** Estimadores com convergência à taxa raiz de n e intervalos de confiança válidos mesmo com ML flexível.

- **Semi-Supervised Classification with Graph Convolutional Networks** (2016) — *Fundacional*  
  Thomas N. Kipf, Max Welling  
  arXiv v1: 2016-09-09 · última versão (v4): 2017-02-22 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:1609.02907](https://arxiv.org/abs/1609.02907)  
  **Resumo:** Graph Convolutional Networks para classificação semi-supervisionada de nós.  
  **Resultado:** Supera métodos relacionados com margem significativa em redes de citação e grafo de conhecimento, escalando linearmente nas arestas.

- **Neural Message Passing for Quantum Chemistry** (2017) — *Fundacional*  
  Justin Gilmer, Samuel S. Schoenholz, Patrick F. Riley, Oriol Vinyals, George E. Dahl  
  arXiv v1: 2017-04-04 · última versão (v2): 2017-06-12 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:1704.01212](https://arxiv.org/abs/1704.01212)  
  **Resumo:** Unifica modelos de grafos moleculares no arcabouço Message Passing Neural Networks.  
  **Resultado:** Estado da arte num benchmark de propriedades moleculares (QM9).

- **Proximal Policy Optimization Algorithms** (2017) — *Fundacional*  
  John Schulman, Filip Wolski, Prafulla Dhariwal, Alec Radford, Oleg Klimov  
  arXiv v1: 2017-07-20 · última versão (v2): 2017-08-28 · **Preprint (arXiv)** · [arXiv:1707.06347](https://arxiv.org/abs/1707.06347)  
  **Resumo:** PPO: gradiente de política com objetivo «clipado» que permite várias épocas por lote.  
  **Resultado:** Supera outros métodos online de gradiente de política em locomoção simulada e Atari, sendo mais simples. Preprint.

- **Deep Reinforcement Learning that Matters** (2017) — *Resultado negativo/crítica*  
  Peter Henderson, Riashat Islam, Philip Bachman, Joelle Pineau, Doina Precup, David Meger  
  arXiv v1: 2017-09-19 · última versão (v3): 2019-01-30 · **Revisado por pares**: AAAI Conference on Artificial Intelligence · [arXiv:1709.06560](https://arxiv.org/abs/1709.06560) · [DOI 10.1609/aaai.v32i1.11694](https://doi.org/10.1609/aaai.v32i1.11694)  
  **Resumo:** Investiga a reprodutibilidade em RL profundo.  
  **Resultado:** Sementes, implementação e ambiente mudam resultados de forma significativa; propõe diretrizes de relato e testes de significância.

- **Smart "Predict, then Optimize"** (2017) — *Método*  
  Adam N. Elmachtoub, Paul Grigas  
  arXiv v1: 2017-10-22 · última versão (v5): 2020-11-19 · **Revisado por pares**: Management Sciences · [arXiv:1710.08005](https://arxiv.org/abs/1710.08005) · [DOI 10.1287/MNSC.2020.3922](https://doi.org/10.1287/MNSC.2020.3922)  
  **Resumo:** Smart «Predict, then Optimize»: função de perda (SPO e SPO+) que mede o erro de decisão induzido pela previsão.  
  **Resultado:** Melhora decisões em caminho mínimo e portfólio, sobretudo com modelos mal especificados; publicado na Management Science.

- **Graph Attention Networks** (2017) — *Fundacional*  
  Petar Veličković, Guillem Cucurull, Arantxa Casanova, Adriana Romero, Pietro Liò, Yoshua Bengio  
  arXiv v1: 2017-10-30 · última versão (v3): 2018-02-04 · **Revisado por pares**: ICLR 2018 · [arXiv:1710.10903](https://arxiv.org/abs/1710.10903)  
  **Resumo:** Graph Attention Networks: autoatenção mascarada sobre vizinhanças.  
  **Resultado:** Igual ou melhor que o estado da arte em Cora, Citeseer, Pubmed e PPI (indutivo).

- **The Hitchhiker’s Guide to Testing Statistical Significance in Natural Language Processing** (2018) — *Survey/revisão*  
  Rotem Dror, Gili Baumer, Segev Shlomov, Roi Reichart  
  Publicação: 2018 · **Revisado por pares**: Proceedings of the 56th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers) · [DOI 10.18653/v1/P18-1128](https://doi.org/10.18653/v1/P18-1128)  
  **Resumo:** Guia de testes de significância estatística em PLN, com análise de artigos do ACL.  
  **Resultado:** Muitos artigos não reportam testes ou usam o teste errado; propõe protocolo de escolha do teste.

- **Attention, Learn to Solve Routing Problems!** (2018) — *Método*  
  Wouter Kool, Herke van Hoof, Max Welling  
  arXiv v1: 2018-03-22 · última versão (v3): 2019-02-07 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:1803.08475](https://arxiv.org/abs/1803.08475)  
  **Resumo:** Modelo de atenção treinado com REINFORCE e baseline de rollout guloso para problemas de roteamento.  
  **Resultado:** Resultados próximos do ótimo no TSP até 100 nós e heurísticas fortes para VRP, OP e PCTSP.

- **A note on the validity of cross-validation for evaluating autoregressive time series prediction** (2018) — *Teórico*  
  Christoph Bergmeir, Rob J. Hyndman, Bonsoo Koo  
  Publicação: 2018-04 · **Revisado por pares**: Computational Statistics &amp; Data Analysis · [DOI 10.1016/j.csda.2017.11.003](https://doi.org/10.1016/j.csda.2017.11.003)  
  **Resumo:** Analisa a validade da validação cruzada K-fold para modelos autorregressivos de séries temporais.  
  **Resultado:** K-fold é válido para modelos puramente autorregressivos com erros não correlacionados; caso contrário, usar avaliação fora da amostra.

- **BOHB: Robust and Efficient Hyperparameter Optimization at Scale** (2018) — *Método*  
  Stefan Falkner, Aaron Klein, Frank Hutter  
  arXiv v1: 2018-07-04 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:1807.01774](https://arxiv.org/abs/1807.01774)  
  **Resumo:** BOHB combina otimização bayesiana (TPE) e Hyperband.  
  **Resultado:** Supera ambos isoladamente numa ampla gama de problemas, com bom desempenho a qualquer momento.

- **Machine Learning for Combinatorial Optimization: a Methodological Tour d'Horizon** (2018) — *Survey/revisão*  
  Yoshua Bengio, Andrea Lodi, Antoine Prouvost  
  arXiv v1: 2018-11-15 · última versão (v2): 2020-03-12 · **Revisado por pares**: European Journal of Operational Research · [arXiv:1811.06128](https://arxiv.org/abs/1811.06128) · [DOI 10.1016/j.ejor.2020.07.063](https://doi.org/10.1016/j.ejor.2020.07.063)  
  **Resumo:** Revisão metodológica do uso de ML em otimização combinatória, vista como aprender sobre distribuições de instâncias.  
  **Resultado:** Organiza o campo (ML de ponta a ponta, ML para configurar algoritmos, ML dentro de solvers).

- **N-BEATS: Neural basis expansion analysis for interpretable time series forecasting** (2019) — *Método*  
  Boris N. Oreshkin, Dmitri Carpov, Nicolas Chapados, Yoshua Bengio  
  arXiv v1: 2019-05-24 · última versão (v4): 2020-02-20 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:1905.10437](https://arxiv.org/abs/1905.10437)  
  **Resumo:** N-BEATS: rede profunda totalmente conectada com ligações residuais para previsão univariada.  
  **Resultado:** 11% melhor que um benchmark estatístico e 3% melhor que o vencedor da M4.

- **Exact Combinatorial Optimization with Graph Convolutional Neural Networks** (2019) — *Método*  
  Maxime Gasse, Didier Chételat, Nicola Ferroni, Laurent Charlin, Andrea Lodi  
  arXiv v1: 2019-06-04 · última versão (v3): 2019-10-30 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:1906.01629](https://arxiv.org/abs/1906.01629) · [código](https://github.com/ds4dm/learn2branch)  
  **Resumo:** GCNN sobre a representação bipartida variável-restrição de MILPs para aprender regras de branching por imitação.  
  **Resultado:** Generaliza para instâncias maiores e, pela primeira vez, supera regras de especialistas num solver de ponta em problemas grandes.

- **Can You Trust Your Model's Uncertainty? Evaluating Predictive Uncertainty Under Dataset Shift** (2019) — *Estudo empírico*  
  Yaniv Ovadia, Emily Fertig, Jie Ren, Zachary Nado, D Sculley, Sebastian Nowozin et al. (9 autores)  
  arXiv v1: 2019-06-06 · última versão (v2): 2019-12-17 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:1906.02530](https://arxiv.org/abs/1906.02530)  
  **Resumo:** Benchmark em larga escala de métodos de incerteza sob mudança de distribuição.  
  **Resultado:** A calibração pós-hoc falha sob mudança; métodos que agregam vários modelos (ensembles) são os mais robustos.

- **Optuna: A Next-generation Hyperparameter Optimization Framework** (2019) — *Sistema*  
  Takuya Akiba, Shotaro Sano, Toshihiko Yanase, Takeru Ohta, Masanori Koyama  
  arXiv v1: 2019-07-25 · **Revisado por pares**: Knowledge Discovery and Data Mining · [arXiv:1907.10902](https://arxiv.org/abs/1907.10902) · [DOI 10.1145/3292500.3330701](https://doi.org/10.1145/3292500.3330701) · [código](https://github.com/pfnet/optuna/)  
  **Resumo:** Optuna: framework de otimização de hiperparâmetros com API define-by-run, poda eficiente e execução distribuída.  
  **Resultado:** Ferramenta de referência; artigo descreve o design e aplicações (KDD).

- **The M4 Competition: 100,000 time series and 61 forecasting methods** (2020) — *Benchmark/dataset*  
  Spyros Makridakis, Evangelos Spiliotis, Vassilios Assimakopoulos  
  Publicação: 2020-01 · **Revisado por pares**: International Journal of Forecasting · [DOI 10.1016/j.ijforecast.2019.04.014](https://doi.org/10.1016/j.ijforecast.2019.04.014)  
  **Resumo:** Resultados da competição M4: 100 mil séries temporais e 61 métodos.  
  **Resultado:** Combinações e híbridos estatístico+ML foram os mais precisos; métodos puramente de ML tiveram desempenho fraco.

- **In Search of Lost Domain Generalization** (2020) — *Resultado negativo/crítica*  
  Ishaan Gulrajani, David Lopez-Paz  
  arXiv v1: 2020-07-02 · **Revisado por pares**: International Conference on Learning Representations · [arXiv:2007.01434](https://arxiv.org/abs/2007.01434)  
  **Resumo:** DomainBed: plataforma para comparar algoritmos de generalização de domínio com seleção de modelo explícita.  
  **Resultado:** Com implementação cuidadosa, ERM simples iguala o estado da arte em todos os datasets — algoritmos sofisticados não se sustentam.

- **With Little Power Comes Great Responsibility** (2020) — *Estudo empírico*  
  Dallas Card, Peter Henderson, Urvashi Khandelwal, Robin Jia, Kyle Mahowald, Dan Jurafsky  
  arXiv v1: 2020-10-13 · **Revisado por pares**: Conference on Empirical Methods in Natural Language Processing · [arXiv:2010.06595](https://arxiv.org/abs/2010.06595) · [DOI 10.18653/v1/2020.emnlp-main.745](https://doi.org/10.18653/v1/2020.emnlp-main.745)  
  **Resumo:** Meta-análise do poder estatístico em experimentos de PLN.  
  **Resultado:** Experimentos subdimensionados são comuns (GLUE, avaliações humanas); conjuntos de 2.000 sentenças têm ~75% de poder para detectar 1 BLEU.

- **WILDS: A Benchmark of in-the-Wild Distribution Shifts** (2020) — *Benchmark/dataset*  
  Pang Wei Koh, Shiori Sagawa, Henrik Marklund, Sang Michael Xie, Marvin Zhang, Akshay Balsubramani et al. (23 autores)  
  arXiv v1: 2020-12-14 · última versão (v3): 2021-07-16 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2012.07421](https://arxiv.org/abs/2012.07421)  
  **Resumo:** WILDS: 10 datasets com mudanças de distribuição reais (hospitais, câmeras, regiões, tempo).  
  **Resultado:** Modelos padrão perdem desempenho fora da distribuição e métodos de robustez existentes não fecham a lacuna.

- **Combinatorial optimization and reasoning with graph neural networks** (2021) — *Survey/revisão*  
  Quentin Cappart, Didier Chételat, Elias Khalil, Andrea Lodi, Christopher Morris, Petar Veličković  
  arXiv v1: 2021-02-18 · última versão (v3): 2022-09-23 · **Revisado por pares**: Journal of Machine Learning Research, 24(130):1-61, 2023 · [arXiv:2102.09544](https://arxiv.org/abs/2102.09544) · [DOI 10.24963/ijcai.2021/595](https://doi.org/10.24963/ijcai.2021/595)  
  **Resumo:** Revisão conceitual de GNNs para otimização combinatória e raciocínio.  
  **Resultado:** Mostra por que o viés indutivo das GNNs se ajusta a problemas relacionais e esparsos.

- **Towards Causal Representation Learning** (2021) — *Survey/revisão*  
  Bernhard Schölkopf, Francesco Locatello, Stefan Bauer, Nan Rosemary Ke, Nal Kalchbrenner, Anirudh Goyal et al. (7 autores)  
  arXiv v1: 2021-02-22 · **Revisado por pares**: Proceedings of the IEEE (edição especial) · [arXiv:2102.11107](https://arxiv.org/abs/2102.11107)  
  **Resumo:** Revisa conceitos de causalidade e sua relação com problemas de ML (transferência, generalização) e define aprendizado de representações causais.  
  **Resultado:** Agenda de pesquisa; publicado nos Proceedings of the IEEE.

- **Accounting for Variance in Machine Learning Benchmarks** (2021) — *Estudo empírico*  
  Xavier Bouthillier, Pierre Delaunay, Mirko Bronzi, Assya Trofimov, Brennan Nichyporuk, Justin Szeto et al. (17 autores)  
  arXiv v1: 2021-03-01 · **Revisado por pares**: Conference on Machine Learning and Systems · [arXiv:2103.03098](https://arxiv.org/abs/2103.03098)  
  **Resumo:** Modela a variância de benchmarks de ML (amostragem, inicialização, hiperparâmetros) e analisa métodos de comparação.  
  **Resultado:** A variância muda conclusões; aleatorizar mais fontes de variação aproxima o estimador ideal com 51 vezes menos cômputo.

- **Are Transformers Effective for Time Series Forecasting?** (2022) — *Resultado negativo/crítica*  
  Ailing Zeng, Muxi Chen, Lei Zhang, Qiang Xu  
  arXiv v1: 2022-05-26 · última versão (v3): 2022-08-17 · **Revisado por pares**: AAAI Conference on Artificial Intelligence · [arXiv:2205.13504](https://arxiv.org/abs/2205.13504) · [código](https://github.com/cure-lab/LTSF-Linear)  
  **Resumo:** Questiona Transformers para previsão de longo prazo comparando-os a modelos lineares de uma camada (LTSF-Linear).  
  **Resultado:** Os modelos lineares superaram todos os Transformers avaliados em nove datasets reais, muitas vezes com folga.

- **Leakage and the Reproducibility Crisis in ML-based Science** (2022) — *Resultado negativo/crítica*  
  Sayash Kapoor, Arvind Narayanan  
  arXiv v1: 2022-07-14 · **Preprint (arXiv)** · [arXiv:2207.07048](https://arxiv.org/abs/2207.07048)  
  **Resumo:** Levantamento de vazamento de dados (data leakage) em ciência baseada em ML, com taxonomia de 8 tipos e «model info sheets».  
  **Resultado:** Erros em 17 áreas afetando 329 artigos; em previsão de guerra civil, todos os modelos complexos que superavam regressão logística falharam ao corrigir o vazamento. Preprint.

- **Why do tree-based models still outperform deep learning on tabular data?** (2022) — *Resultado negativo/crítica*  
  Léo Grinsztajn, Edouard Oyallon, Gaël Varoquaux  
  arXiv v1: 2022-07-18 · **Preprint (arXiv)** · [arXiv:2207.08815](https://arxiv.org/abs/2207.08815)  
  **Resumo:** Benchmark de 45 datasets tabulares comparando árvores e redes neurais com busca de hiperparâmetros (20 mil horas de cômputo por modelo).  
  **Resultado:** Modelos de árvore seguem estado da arte em dados de porte médio (~10 mil amostras).

- **Decision-Focused Learning: Foundations, State of the Art, Benchmark and Future Opportunities** (2023) — *Survey/revisão*  
  Jayanta Mandi, James Kotary, Senne Berden, Maxime Mulamba, Victor Bucarey, Tias Guns et al. (7 autores)  
  arXiv v1: 2023-07-25 · última versão (v4): 2024-09-04 · **Revisado por pares**: Journal of Artificial Intelligence Research 81 (2024) 1623-1701 · [arXiv:2307.13565](https://arxiv.org/abs/2307.13565) · [DOI 10.1613/jair.1.15320](https://doi.org/10.1613/jair.1.15320) · [código](https://github.com/PredOpt/predopt-benchmarks)  
  **Resumo:** Revisão e benchmark de decision-focused learning: 11 métodos em 7 problemas.  
  **Resultado:** Avaliação empírica comparativa e código aberto; publicado no JAIR.

- **A decoder-only foundation model for time-series forecasting** (2023) — *Método*  
  Abhimanyu Das, Weihao Kong, Rajat Sen, Yichen Zhou  
  arXiv v1: 2023-10-14 · última versão (v4): 2024-04-17 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2310.10688](https://arxiv.org/abs/2310.10688)  
  **Resumo:** TimesFM: modelo de fundação decoder-only com patches para previsão de séries.  
  **Resultado:** Zero-shot próximo de modelos supervisionados de ponta em vários datasets públicos.

- **Mathematical discoveries from program search with large language models** (2023) — *Método*  
  Bernardino Romera-Paredes, Mohammadamin Barekatain, Alexander Novikov, Matej Balog, M. Pawan Kumar, Emilien Dupont et al. (12 autores)  
  Publicação: 2023-12-14 · **Revisado por pares**: Nature · [DOI 10.1038/s41586-023-06924-6](https://doi.org/10.1038/s41586-023-06924-6)  
  **Resumo:** FunSearch: busca evolutiva sobre programas gerados por LLM, guiada por um avaliador automático.  
  **Resultado:** Novas construções para o problema de cap set e heurísticas melhores de bin packing — exemplo de LLM + otimização com verificação.

- **Chronos: Learning the Language of Time Series** (2024) — *Método*  
  Abdul Fatir Ansari, Lorenzo Stella, Caner Turkmen, Xiyuan Zhang, Pedro Mercado, Huibin Shen et al. (18 autores)  
  arXiv v1: 2024-03-12 · última versão (v3): 2024-11-04 · **Revisado por pares**: Trans. Mach. Learn. Res. · [arXiv:2403.07815](https://arxiv.org/abs/2403.07815) · [código](https://github.com/amazon-science/chronos-forecasting)  
  **Resumo:** Chronos: tokeniza séries por escala e quantização e treina arquiteturas de LM (T5, 20M–710M) em muitos datasets.  
  **Resultado:** Em 42 datasets, supera métodos nos dados de treino e tem desempenho zero-shot comparável ou superior em dados novos.

- **Adding Error Bars to Evals: A Statistical Approach to Language Model Evaluations** (2024) — *Método*  
  Evan Miller  
  arXiv v1: 2024-11-01 · **Preprint (arXiv)** · [arXiv:2411.00640](https://arxiv.org/abs/2411.00640)  
  **Resumo:** Trata avaliações de LLMs como experimentos e fornece fórmulas para erros-padrão, comparações pareadas e planejamento de amostra.  
  **Resultado:** Recomendações práticas para reportar avaliações com intervalos de confiança. Preprint.

- **Accurate predictions on small data with a tabular foundation model** (2025) — *Método*  
  Noah Hollmann, Samuel Müller, Lennart Purucker, Arjun Krishnakumar, Max Körfer, Shi Bin Hoo et al. (8 autores)  
  Publicação: 2025-01-08 · **Revisado por pares**: Nature · [DOI 10.1038/s41586-024-08328-6](https://doi.org/10.1038/s41586-024-08328-6)  
  **Resumo:** TabPFN: Transformer pré-treinado em dados sintéticos que faz previsão tabular por aprendizado em contexto.  
  **Resultado:** Em datasets pequenos, supera baselines ajustados com muito menos tempo; publicado na Nature.

<a id="f"></a>

### Eixo F — Engenharia de Dados para sistemas de IA

- **Why and Where: A Characterization of Data Provenance** (2001) — *Fundacional*  
  Peter Buneman, Sanjeev Khanna, Tan Wang-Chiew  
  Publicação: 2001 · **Revisado por pares**: Lecture Notes in Computer Science · [DOI 10.1007/3-540-44503-X_20](https://doi.org/10.1007/3-540-44503-X_20)  
  **Resumo:** Caracteriza proveniência de dados em why-provenance e where-provenance.  
  **Resultado:** Base formal para linhagem e rastreabilidade.

- **MapReduce: simplified data processing on large clusters** (2008) — *Fundacional*  
  Jeffrey Dean, Sanjay Ghemawat  
  Publicação: 2008-01 · **Revisado por pares**: Communications of the ACM · [DOI 10.1145/1327452.1327492](https://doi.org/10.1145/1327452.1327492)  
  **Resumo:** MapReduce: modelo de programação e execução para processar grandes volumes em clusters.  
  **Resultado:** Base do processamento distribuído em lote.

- **Kafka : a Distributed Messaging System for Log Processing** (2011) — *Fundacional*  
  Jay Kreps, Neha Narkhede, Jun Rao  
  Publicação: 2011 · **Venue não confirmado**: NetDB 2011 (workshop) — venue não confirmado automaticamente · [registro](https://www.semanticscholar.org/paper/ea97f112c165e4da1062c30812a41afca4dab628)  
  **Resumo:** Kafka: sistema distribuído de mensagens baseado em log para processamento de logs no LinkedIn.  
  **Resultado:** Base de arquiteturas orientadas a eventos e Kappa. Publicado em workshop (NetDB); venue não confirmado automaticamente.

- **The dataflow model: a practical approach to balancing correctness, latency, and cost in massive-scale, unbounded, out-of-order data processing** (2015) — *Fundacional*  
  Tyler Akidau, Robert Bradshaw, Craig Chambers, Slava Chernyak, Rafael J. Fernández-Moctezuma, Reuven Lax et al. (11 autores)  
  Publicação: 2015-08 · **Revisado por pares**: Proceedings of the VLDB Endowment · [DOI 10.14778/2824032.2824076](https://doi.org/10.14778/2824032.2824076)  
  **Resumo:** Modelo Dataflow: janelas, gatilhos, marcas d'água e acumulação para dados ilimitados e fora de ordem.  
  **Resultado:** Unifica lote e streaming com controle explícito de correção, latência e custo.

- **Apache Spark: a unified engine for big data processing** (2016) — *Fundacional*  
  Matei Zaharia, Reynold S. Xin, Patrick Wendell, Tathagata Das, Michael Armbrust, Ankur Dave et al. (14 autores)  
  Publicação: 2016-10-28 · **Revisado por pares**: Communications of the ACM · [DOI 10.1145/2934664](https://doi.org/10.1145/2934664)  
  **Resumo:** Apache Spark: motor unificado baseado em RDDs para lote, streaming, SQL, ML e grafos.  
  **Resultado:** Consolida cargas heterogêneas num único motor distribuído.

- **Datasheets for Datasets** (2018) — *Fundacional*  
  Timnit Gebru, Jamie Morgenstern, Briana Vecchione, Jennifer Wortman Vaughan, Hanna Wallach, Hal Daumé et al. (7 autores)  
  arXiv v1: 2018-03-23 · última versão (v8): 2021-12-01 · **Revisado por pares**: Communications of the ACM · [arXiv:1803.09010](https://arxiv.org/abs/1803.09010) · [DOI 10.1145/3458723](https://doi.org/10.1145/3458723)  
  **Resumo:** Datasheets for datasets: documentação padronizada de motivação, composição, coleta e usos de um dataset.  
  **Resultado:** Proposta de prática; publicado na CACM.

- **Automating large-scale data quality verification** (2018) — *Sistema*  
  Sebastian Schelter, Dustin Lange, Philipp Schmidt, Meltem Celikel, Felix Biessmann, Andreas Grafberger  
  Publicação: 2018-08 · **Revisado por pares**: Proceedings of the VLDB Endowment · [DOI 10.14778/3229863.3229867](https://doi.org/10.14778/3229863.3229867)  
  **Resumo:** Deequ: verificação declarativa de qualidade de dados em larga escala («testes unitários para dados»).  
  **Resultado:** Usado em produção na Amazon; incremental e escalável sobre Spark.

- **Data Lifecycle Challenges in Production Machine Learning: A Survey** (2018) — *Survey/revisão*  
  Neoklis Polyzotis, Sudip Roy, Steven Euijong Whang, Martin Zinkevich  
  Publicação: 2018-12-11 · **Revisado por pares**: ACM SIGMOD Record · [DOI 10.1145/3299887.3299891](https://doi.org/10.1145/3299887.3299891)  
  **Resumo:** Desafios do ciclo de vida de dados em ML de produção (Google): entendimento, validação, limpeza e preparação.  
  **Resultado:** Mostra que dados, e não modelos, concentram os problemas de produção.

- **Delta lake: high-performance ACID table storage over cloud object stores** (2020) — *Sistema*  
  Michael Armbrust, Tathagata Das, Liwen Sun, Burak Yavuz, Shixiong Zhu, Mukul Murthy et al. (21 autores)  
  Publicação: 2020-08 · **Revisado por pares**: Proceedings of the VLDB Endowment · [DOI 10.14778/3415478.3415560](https://doi.org/10.14778/3415478.3415560)  
  **Resumo:** Delta Lake: armazenamento de tabelas ACID sobre object storage, com log de transações.  
  **Resultado:** Transações, viagem no tempo e upserts sobre data lakes — base do padrão lakehouse.

- **DBLog: A Watermark Based Change-Data-Capture Framework** (2020) — *Sistema*  
  Andreas Andreakis, Ioannis Papapanagiotou  
  arXiv v1: 2020-10-23 · **Preprint (arXiv)** · [arXiv:2010.12597](https://arxiv.org/abs/2010.12597)  
  **Resumo:** DBLog: change data capture com marcas d'água que intercala eventos do log transacional com seleções completas das tabelas.  
  **Resultado:** Sem locks e com baixo impacto na origem; em produção na Netflix. Preprint.

- **Lakehouse: A New Generation of Open Platforms that Unify Data Warehousing and Advanced Analytics** (2021) — *Posição*  
  M. Zaharia, Ali Ghodsi, R. Xin, Michael Armbrust  
  Publicação: 2021 · **Revisado por pares**: CIDR 2021 · [registro](https://www.cidrdb.org/cidr2021/papers/cidr2021_paper17.pdf)  
  **Resumo:** Propõe o lakehouse: plataformas abertas que unem recursos de data warehouse a data lakes.  
  **Resultado:** Argumenta que a arquitetura de duas camadas será substituída; artigo de visão (CIDR).

- **“Everyone wants to do the model work, not the data work”: Data Cascades in High-Stakes AI** (2021) — *Estudo empírico*  
  Nithya Sambasivan, Shivani Kapania, Hannah Highfill, Diana Akrong, Praveen Paritosh, Lora M Aroyo  
  Publicação: 2021-05-06 · **Revisado por pares**: Proceedings of the 2021 CHI Conference on Human Factors in Computing Systems · [DOI 10.1145/3411764.3445518](https://doi.org/10.1145/3411764.3445518)  
  **Resumo:** Estudo qualitativo sobre «cascatas de dados»: problemas de dados que se acumulam e geram impactos negativos em sistemas de IA de alto risco.  
  **Resultado:** Cascatas são frequentes, invisíveis e evitáveis; trabalho com dados é subvalorizado.

- **Milvus: A Purpose-Built Vector Data Management System** (2021) — *Sistema*  
  Jianguo Wang, Xiaomeng Yi, Rentong Guo, Hai Jin, Peng Xu, Shengjun Li et al. (22 autores)  
  Publicação: 2021-06-09 · **Revisado por pares**: Proceedings of the 2021 International Conference on Management of Data · [DOI 10.1145/3448016.3457550](https://doi.org/10.1145/3448016.3457550)  
  **Resumo:** Milvus: sistema de gerenciamento de dados vetoriais construído para esse fim, com computação heterogênea.  
  **Resultado:** Desempenho e funcionalidades superiores a sistemas da época em consultas vetoriais e híbridas.

- **Deduplicating Training Data Makes Language Models Better** (2021) — *Estudo empírico*  
  Katherine Lee, Daphne Ippolito, Andrew Nystrom, Chiyuan Zhang, Douglas Eck, Chris Callison-Burch et al. (7 autores)  
  arXiv v1: 2021-07-14 · última versão (v2): 2022-03-24 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2107.06499](https://arxiv.org/abs/2107.06499) · [DOI 10.18653/v1/2022.acl-long.577](https://doi.org/10.18653/v1/2022.acl-long.577) · [código](https://github.com/google-research/deduplicate-text-datasets)  
  **Resumo:** Desduplicação de dados de treino de LMs.  
  **Resultado:** Mais de 1% das saídas copiadas de dados duplicados; desduplicar reduz em 10 vezes a memorização e a sobreposição treino-teste (que afetava mais de 4% da validação).

- **Data-centric AI: Perspectives and Challenges** (2023) — *Posição*  
  Daochen Zha, Zaid Pervaiz Bhat, Kwei-Herng Lai, Fan Yang, Xia Hu  
  arXiv v1: 2023-01-12 · última versão (v3): 2023-04-02 · **Revisado por pares**: SDM · [arXiv:2301.04819](https://arxiv.org/abs/2301.04819) · [código](https://github.com/daochenzha/data-centric-AI)  
  **Resumo:** Perspectiva de IA centrada em dados: desenvolvimento de dados de treino, de inferência e manutenção.  
  **Resultado:** Agenda e desafios abertos (SDM Blue Sky).

- **Scaling Data-Constrained Language Models** (2023) — *Estudo empírico*  
  Niklas Muennighoff, Alexander M. Rush, Boaz Barak, Teven Le Scao, Aleksandra Piktus, Nouamane Tazi et al. (9 autores)  
  arXiv v1: 2023-05-25 · última versão (v5): 2025-06-28 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2305.16264](https://arxiv.org/abs/2305.16264) · [código](https://github.com/huggingface/datablations)  
  **Resumo:** Leis de escala com dados limitados, variando repetição e orçamento (até 900 bilhões de tokens, 9B parâmetros).  
  **Resultado:** Até 4 épocas de repetição quase não mudam a perda; depois disso, o valor de mais cômputo decai a zero.

- **Survey of Vector Database Management Systems** (2023) — *Survey/revisão*  
  James Jie Pan, Jianguo Wang, Guoliang Li  
  arXiv v1: 2023-10-21 · **Revisado por pares**: The VLDB journal · [arXiv:2310.14021](https://arxiv.org/abs/2310.14021) · [DOI 10.1007/s00778-024-00864-x](https://doi.org/10.1007/s00778-024-00864-x)  
  **Resumo:** Survey de sistemas de gerenciamento de bancos vetoriais: processamento de consultas, armazenamento, indexação e otimização.  
  **Resultado:** Identifica cinco obstáculos (semântica vaga, vetores grandes, comparação cara, falta de partição natural, consultas híbridas). VLDB Journal.

- **Dolma: an Open Corpus of Three Trillion Tokens for Language Model Pretraining Research** (2024) — *Benchmark/dataset*  
  Luca Soldaini, Rodney Kinney, Akshita Bhagia, Dustin Schwenk, David Atkinson, Russell Authur et al. (36 autores)  
  arXiv v1: 2024-01-31 · última versão (v2): 2024-06-06 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:2402.00159](https://arxiv.org/abs/2402.00159) · [código](https://hf.co/datasets/allenai/dolma) · [código 2](https://github.com/allenai/dolma)  
  **Resumo:** Dolma: corpus aberto de 3 trilhões de tokens com documentação e toolkit de curadoria.  
  **Resultado:** Viabiliza pesquisa reprodutível sobre efeito dos dados de pré-treino.

- **The FineWeb Datasets: Decanting the Web for the Finest Text Data at Scale** (2024) — *Benchmark/dataset*  
  Guilherme Penedo, Hynek Kydlíček, Loubna Ben allal, Anton Lozhkov, Margaret Mitchell, Colin Raffel et al. (8 autores)  
  arXiv v1: 2024-06-25 · última versão (v2): 2024-10-31 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2406.17557](https://arxiv.org/abs/2406.17557)  
  **Resumo:** FineWeb: 15 trilhões de tokens de 96 snapshots do Common Crawl, com ablações documentadas de filtragem e desduplicação.  
  **Resultado:** Modelos treinados nele superam outros datasets abertos; o subconjunto FineWeb-Edu melhora muito MMLU e ARC.

<a id="g"></a>

### Eixo G — MLOps, LLMOps e operação em produção

- **A survey on concept drift adaptation** (2014) — *Survey/revisão*  
  João Gama, Indrė Žliobaitė, Albert Bifet, Mykola Pechenizkiy, Abdelhamid Bouchachia  
  Publicação: 2014-03 · **Revisado por pares**: ACM Computing Surveys · [DOI 10.1145/2523813](https://doi.org/10.1145/2523813)  
  **Resumo:** Survey de adaptação a concept drift: detecção, estratégias de adaptação e avaliação.  
  **Resultado:** Referência para monitoramento de modelos em fluxo (ACM CSUR).

- **Hidden Technical Debt in Machine Learning Systems** (2015) — *Fundacional*  
  D. Sculley, Gary Holt, Daniel Golovin, E. Davydov, Todd Phillips, D. Ebner et al. (10 autores)  
  Publicação: 2015 · **Revisado por pares**: NeurIPS 2015 · [registro](https://dblp.org/rec/conf/nips/SculleyHGDPECYC15)  
  **Resumo:** Dívida técnica em sistemas de ML: entrelaçamento, laços de realimentação ocultos, código de cola e selvas de pipelines.  
  **Resultado:** Mostra que o código de ML é pequena parte do sistema e que a dívida está nos dados e na infraestrutura.

- **Clipper: A Low-Latency Online Prediction Serving System** (2016) — *Sistema*  
  Daniel Crankshaw, Xin Wang, Giulio Zhou, Michael J. Franklin, Joseph E. Gonzalez, Ion Stoica  
  arXiv v1: 2016-12-09 · última versão (v2): 2017-02-28 · **Revisado por pares**: Symposium on Networked Systems Design and Implementation · [arXiv:1612.03079](https://arxiv.org/abs/1612.03079)  
  **Resumo:** Clipper: sistema de serving de baixa latência com cache, batching e seleção adaptativa de modelos.  
  **Resultado:** Atende requisitos de latência e throughput, comparável ao TensorFlow Serving (NSDI 2017).

- **TFX: A TensorFlow-Based Production-Scale Machine Learning Platform** (2017) — *Sistema*  
  Denis Baylor, Eric Breck, Heng-Tze Cheng, Noah Fiedel, Chuan Yu Foo, Zakaria Haque et al. (22 autores)  
  Publicação: 2017-08-13 · **Revisado por pares**: Proceedings of the 23rd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining · [DOI 10.1145/3097983.3098021](https://doi.org/10.1145/3097983.3098021)  
  **Resumo:** TFX: plataforma de ML de produção do Google integrando análise e validação de dados, treino, avaliação e serving.  
  **Resultado:** Redução do tempo de produção e mais confiabilidade; referência de arquitetura de MLOps (KDD).

- **The ML test score: A rubric for ML production readiness and technical debt reduction** (2017) — *Fundacional*  
  Eric Breck, Shanqing Cai, Eric Nielsen, Michael Salib, D. Sculley  
  Publicação: 2017-12 · **Revisado por pares**: 2017 IEEE International Conference on Big Data (Big Data) · [DOI 10.1109/BigData.2017.8258038](https://doi.org/10.1109/BigData.2017.8258038)  
  **Resumo:** ML Test Score: rubrica de testes para prontidão de produção em ML (dados, modelo, infraestrutura e monitoramento).  
  **Resultado:** Checklist aplicável para auditar maturidade de sistemas de ML.

- **Model Cards for Model Reporting** (2018) — *Fundacional*  
  Margaret Mitchell, Simone Wu, Andrew Zaldivar, Parker Barnes, Lucy Vasserman, Ben Hutchinson et al. (9 autores)  
  arXiv v1: 2018-10-05 · última versão (v2): 2019-01-14 · **Revisado por pares**: FAT* '19: Conference on Fairness, Accountability, and Transparency, January 29--31, 2019, Atlanta, GA, USA · [arXiv:1810.03993](https://arxiv.org/abs/1810.03993) · [DOI 10.1145/3287560.3287596](https://doi.org/10.1145/3287560.3287596)  
  **Resumo:** Model cards: documentação curta de modelos com avaliação desagregada, uso pretendido e limitações.  
  **Resultado:** Prática padrão de transparência (FAT* 2019).

- **Failing Loudly: An Empirical Study of Methods for Detecting Dataset Shift** (2018) — *Estudo empírico*  
  Stephan Rabanser, Stephan Günnemann, Zachary C. Lipton  
  arXiv v1: 2018-10-29 · última versão (v4): 2019-10-28 · **Revisado por pares**: NeurIPS 2019 · [arXiv:1810.11953](https://arxiv.org/abs/1810.11953)  
  **Resumo:** Estudo empírico de métodos de detecção de dataset shift.  
  **Resultado:** Teste de duas amostras com redução de dimensionalidade por classificador pré-treinado foi o melhor detector.

- **Data Validation for Machine Learning** (2019) — *Sistema*  
  Eric Breck, Neoklis Polyzotis, Sudip Roy, Steven Euijong Whang, Martin A. Zinkevich  
  Publicação: 2019 · **Revisado por pares**: MLSys 2019 (DBLP conf/mlsys/BreckP0WZ19) · [registro](https://dblp.org/rec/conf/mlsys/BreckP0WZ19)  
  **Resumo:** Sistema de validação de dados para ML do Google: esquema, detecção de anomalias e de desvio treino-serviço.  
  **Resultado:** Detecta problemas de dados antes que afetem modelos em produção (MLSys).

- **Energy and Policy Considerations for Deep Learning in NLP** (2019) — *Estudo empírico*  
  Emma Strubell, Ananya Ganesh, Andrew McCallum  
  arXiv v1: 2019-06-05 · **Revisado por pares**: Annual Meeting of the Association for Computational Linguistics · [arXiv:1906.02243](https://arxiv.org/abs/1906.02243) · [DOI 10.18653/v1/P19-1355](https://doi.org/10.18653/v1/P19-1355)  
  **Resumo:** Quantifica custo financeiro e ambiental de treinar modelos de PLN.  
  **Resultado:** Custos elevados de energia e carbono; recomenda reportar custo computacional e priorizar eficiência.

- **Towards CRISP-ML(Q): A Machine Learning Process Model with Quality Assurance Methodology** (2020) — *Método*  
  Stefan Studer, Thanh Binh Bui, Christian Drescher, Alexander Hanuschkin, Ludwig Winkler, Steven Peters et al. (7 autores)  
  arXiv v1: 2020-03-11 · última versão (v2): 2021-02-24 · **Revisado por pares**: Machine Learning and Knowledge Extraction · [arXiv:2003.05155](https://arxiv.org/abs/2003.05155)  
  **Resumo:** CRISP-ML(Q): modelo de processo para ML com metodologia de garantia de qualidade em seis fases.  
  **Resultado:** Extensão do CRISP-DM para ML, incluindo monitoramento e manutenção.

- **Learning under Concept Drift: A Review** (2020) — *Survey/revisão*  
  Jie Lu, Anjin Liu, Fan Dong, Feng Gu, Joao Gama, Guangquan Zhang  
  arXiv v1: 2020-04-13 · **Revisado por pares**: IEEE Transactions on Knowledge and Data Engineering 31, no. 12 (2018): 2346-2363 · [arXiv:2004.05785](https://arxiv.org/abs/2004.05785) · [DOI 10.1109/TKDE.2018.2876857](https://doi.org/10.1109/TKDE.2018.2876857)  
  **Resumo:** Revisão de mais de 130 trabalhos sobre aprendizado sob concept drift (detecção, entendimento, adaptação).  
  **Resultado:** Arcabouço unificado e lista de datasets de avaliação; IEEE TKDE.

- **Monitoring and explainability of models in production** (2020) — *Posição*  
  Janis Klaise, Arnaud Van Looveren, Clive Cox, Giovanni Vacanti, Alexandru Coca  
  arXiv v1: 2020-07-13 · **Workshop**: Workshop on Challenges in Deploying and Monitoring ML Systems · [arXiv:2007.06299](https://arxiv.org/abs/2007.06299)  
  **Resumo:** Discute monitoramento de modelos em produção: desempenho, drift, outliers e explicabilidade.  
  **Resultado:** Exemplos com ferramentas abertas; artigo de workshop.

- **Challenges in Deploying Machine Learning: a Survey of Case Studies** (2020) — *Survey/revisão*  
  Andrei Paleyes, Raoul-Gabriel Urma, Neil D. Lawrence  
  arXiv v1: 2020-11-18 · última versão (v3): 2022-05-19 · **Revisado por pares**: ACM Computing Surveys · [arXiv:2011.09926](https://arxiv.org/abs/2011.09926) · [DOI 10.1145/3533378](https://doi.org/10.1145/3533378)  
  **Resumo:** Revisão de relatos publicados de implantação de ML por etapa do fluxo de implantação.  
  **Resultado:** Há desafios em todas as etapas; agenda de pesquisa (ACM CSUR).

- **Orca: A Distributed Serving System for Transformer-Based Generative Models** (2022) — *Sistema*  
  Gyeong-In Yu, Joo Seong Jeong, G. Kim, Soojeong Kim, Byung-Gon Chun  
  Publicação: 2022 · **Revisado por pares**: OSDI 2022 · [registro](https://dblp.org/rec/conf/osdi/YuJKKC22)  
  **Resumo:** Orca: serving de modelos generativos com escalonamento por iteração (continuous batching) e batching seletivo.  
  **Resultado:** Ganho grande de throughput sobre sistemas da época com mesma latência (OSDI 2022).

- **Machine Learning Operations (MLOps): Overview, Definition, and Architecture** (2022) — *Survey/revisão*  
  Dominik Kreuzberger, Niklas Kühl, Sebastian Hirschl  
  arXiv v1: 2022-05-04 · última versão (v3): 2022-05-14 · **Revisado por pares**: IEEE Access · [arXiv:2205.02302](https://arxiv.org/abs/2205.02302) · [DOI 10.1109/ACCESS.2023.3262138](https://doi.org/10.1109/ACCESS.2023.3262138)  
  **Resumo:** Pesquisa mista (literatura, ferramentas e entrevistas) que define MLOps, seus princípios, componentes, papéis e arquitetura.  
  **Resultado:** Definição e arquitetura de referência; IEEE Access.

- **FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness** (2022) — *Fundacional*  
  Tri Dao, Daniel Y. Fu, Stefano Ermon, Atri Rudra, Christopher Ré  
  arXiv v1: 2022-05-27 · última versão (v2): 2022-06-23 · **Revisado por pares**: Neural Information Processing Systems · [arXiv:2205.14135](https://arxiv.org/abs/2205.14135) · [DOI 10.52202/068431-1189](https://doi.org/10.52202/068431-1189)  
  **Resumo:** FlashAttention: atenção exata consciente de IO com tiling entre HBM e SRAM.  
  **Resultado:** 15% mais rápido que o recorde MLPerf no BERT-large e 3x no GPT-2; permite contextos maiores.

- **LLM.int8(): 8-bit Matrix Multiplication for Transformers at Scale** (2022) — *Método*  
  Tim Dettmers, Mike Lewis, Younes Belkada, Luke Zettlemoyer  
  arXiv v1: 2022-08-15 · última versão (v2): 2022-11-10 · **Revisado por pares**: Advances in Neural Information Processing Systems 35 · [arXiv:2208.07339](https://arxiv.org/abs/2208.07339)  
  **Resumo:** LLM.int8(): multiplicação em 8 bits com decomposição em precisão mista para features atípicas.  
  **Resultado:** Inferência em modelos de até 175B sem degradação, reduzindo a memória pela metade.

- **Operationalizing Machine Learning: An Interview Study** (2022) — *Estudo empírico*  
  Shreya Shankar, Rolando Garcia, Joseph M. Hellerstein, Aditya G. Parameswaran  
  arXiv v1: 2022-09-16 · **Preprint (arXiv)** · [arXiv:2209.09125](https://arxiv.org/abs/2209.09125)  
  **Resumo:** Entrevistas com 18 engenheiros de ML sobre como operam ML em produção.  
  **Resultado:** Três variáveis governam o sucesso: velocidade, validação e versionamento. Preprint.

- **GPTQ: Accurate Post-Training Quantization for Generative Pre-trained Transformers** (2022) — *Método*  
  Elias Frantar, Saleh Ashkboos, Torsten Hoefler, Dan Alistarh  
  arXiv v1: 2022-10-31 · última versão (v2): 2023-03-22 · **Revisado por pares**: ICLR 2023 (comentário do arXiv) · [arXiv:2210.17323](https://arxiv.org/abs/2210.17323) · [código](https://github.com/IST-DASLab/gptq)  
  **Resumo:** GPTQ: quantização pós-treino de pesos com informação de segunda ordem.  
  **Resultado:** Quantiza modelos de 175B para 3–4 bits em ~4 horas de GPU com perda desprezível; aceleração de ~3,25x (A100) e ~4,5x (A6000).

- **SmoothQuant: Accurate and Efficient Post-Training Quantization for Large Language Models** (2022) — *Método*  
  Guangxuan Xiao, Ji Lin, Mickael Seznec, Hao Wu, Julien Demouth, Song Han  
  arXiv v1: 2022-11-18 · última versão (v7): 2024-03-29 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2211.10438](https://arxiv.org/abs/2211.10438) · [código](https://github.com/mit-han-lab/smoothquant)  
  **Resumo:** SmoothQuant: migra a dificuldade de quantização das ativações para os pesos (W8A8).  
  **Resultado:** Até 1,56x de aceleração e 2x de redução de memória com perda desprezível.

- **Fast Inference from Transformers via Speculative Decoding** (2022) — *Método*  
  Yaniv Leviathan, Matan Kalman, Yossi Matias  
  arXiv v1: 2022-11-30 · última versão (v2): 2023-05-18 · **Revisado por pares**: International Conference on Machine Learning · [arXiv:2211.17192](https://arxiv.org/abs/2211.17192)  
  **Resumo:** Speculative decoding: um modelo pequeno propõe tokens que o grande verifica em paralelo, sem mudar a distribuição de saída.  
  **Resultado:** Aceleração de 2–3x no T5-XXL com saídas idênticas.

- **AWQ: Activation-aware Weight Quantization for LLM Compression and Acceleration** (2023) — *Método*  
  Ji Lin, Jiaming Tang, Haotian Tang, Shang Yang, Wei-Ming Chen, Wei-Chen Wang et al. (10 autores)  
  arXiv v1: 2023-06-01 · última versão (v6): 2026-04-25 · **Revisado por pares**: MLSys 2024 · [arXiv:2306.00978](https://arxiv.org/abs/2306.00978) · [DOI 10.1145/3714983.3714987](https://doi.org/10.1145/3714983.3714987) · [código](https://github.com/mit-han-lab/llm-awq)  
  **Resumo:** AWQ: quantização só de pesos que protege canais salientes identificados pelas ativações.  
  **Resultado:** Supera métodos anteriores e funciona em modelos instruídos e multimodais; TinyChat dá mais de 3x de aceleração. Melhor artigo do MLSys 2024.

- **Efficient Memory Management for Large Language Model Serving with PagedAttention** (2023) — *Sistema*  
  Woosuk Kwon, Zhuohan Li, Siyuan Zhuang, Ying Sheng, Lianmin Zheng, Cody Hao Yu et al. (9 autores)  
  arXiv v1: 2023-09-12 · **Revisado por pares**: Symposium on Operating Systems Principles · [arXiv:2309.06180](https://arxiv.org/abs/2309.06180) · [DOI 10.1145/3600006.3613165](https://doi.org/10.1145/3600006.3613165) · [código](https://github.com/vllm-project/vllm)  
  **Resumo:** vLLM/PagedAttention: gerência do cache KV em páginas, inspirada em memória virtual.  
  **Resultado:** Desperdício quase nulo de cache KV e throughput 2–4x maior que FasterTransformer e Orca na mesma latência (SOSP 2023).

- **Splitwise: Efficient generative LLM inference using phase splitting** (2023) — *Sistema*  
  Pratyush Patel, Esha Choukse, Chaojie Zhang, Aashaka Shah, Íñigo Goiri, Saeed Maleki et al. (7 autores)  
  arXiv v1: 2023-11-30 · última versão (v2): 2024-05-20 · **Revisado por pares**: International Symposium on Computer Architecture · [arXiv:2311.18677](https://arxiv.org/abs/2311.18677) · [DOI 10.1109/ISCA59077.2024.00019](https://doi.org/10.1109/ISCA59077.2024.00019)  
  **Resumo:** Splitwise divide prompt e geração de tokens em máquinas diferentes, adequando o hardware a cada fase.  
  **Resultado:** Clusters otimizados para throughput, custo e energia (ISCA 2024).

- **DistServe: Disaggregating Prefill and Decoding for Goodput-optimized Large Language Model Serving** (2024) — *Sistema*  
  Yinmin Zhong, Shengyu Liu, Junda Chen, Jianbo Hu, Yibo Zhu, Xuanzhe Liu et al. (8 autores)  
  arXiv v1: 2024-01-18 · última versão (v3): 2024-06-06 · **Revisado por pares**: USENIX Symposium on Operating Systems Design and Implementation · [arXiv:2401.09670](https://arxiv.org/abs/2401.09670)  
  **Resumo:** DistServe separa prefill e decodificação em GPUs diferentes para otimizar goodput sob SLOs de TTFT e TPOT.  
  **Resultado:** Atende 7,4x mais requisições ou SLO 12,6x mais apertado que sistemas de ponta (OSDI 2024).

- **Taming Throughput-Latency Tradeoff in LLM Inference with Sarathi-Serve** (2024) — *Sistema*  
  Amey Agrawal, Nitin Kedia, Ashish Panwar, Jayashree Mohan, Nipun Kwatra, Bhargav S. Gulavani et al. (8 autores)  
  arXiv v1: 2024-03-04 · última versão (v3): 2024-06-17 · **Revisado por pares**: USENIX Symposium on Operating Systems Design and Implementation · [arXiv:2403.02310](https://arxiv.org/abs/2403.02310) · [código](https://github.com/microsoft/sarathi-serve)  
  **Resumo:** Sarathi-Serve: chunked prefill e escalonamento sem pausas para equilibrar throughput e latência.  
  **Resultado:** 2,6x mais capacidade com Mistral-7B numa A100 e até 3,7x com Yi-34B, comparado ao vLLM (OSDI 2024).

- **Who Validates the Validators? Aligning LLM-Assisted Evaluation of LLM Outputs with Human Preferences** (2024) — *Estudo empírico*  
  Shreya Shankar, J. D. Zamfirescu-Pereira, Björn Hartmann, Aditya G. Parameswaran, Ian Arawjo  
  arXiv v1: 2024-04-18 · **Revisado por pares**: ACM Symposium on User Interface Software and Technology · [arXiv:2404.12272](https://arxiv.org/abs/2404.12272) · [DOI 10.1145/3654777.3676450](https://doi.org/10.1145/3654777.3676450)  
  **Resumo:** EvalGen: interface para alinhar avaliadores gerados por LLM com julgamentos humanos.  
  **Resultado:** Identifica «criteria drift»: os critérios mudam ao observar saídas, o que questiona avaliações definidas a priori.

<!-- CATALOGO:FIM -->

---

*Sínteses, matrizes e análises são trabalho próprio. Títulos, autores e metadados pertencem às respectivas publicações; consulte sempre a fonte original antes de citar.*
