# Knowledge-in-LLMs-and-AI-Systems-Papers

Aqui listo os principais trabalhos sobre como sistemas de IA **adquirem, atualizam, recuperam e usam conhecimento** — fine-tuning vs RAG, alucinação, arquiteturas, recuperação de informação, ciência de dados, engenharia de dados e MLOps/LLMOps. 
Todos os títulos, anos e links foram conferidos nas fontes oficiais (arXiv, Crossref, Semantic Scholar, DBLP) em 2026-10-10.

📄 A análise completa — resumo e resultado de cada trabalho, fichamentos, matrizes, controvérsias e guia arquitetural — está em **[Analise.md](Analise.md)** e na pasta [portfolio](portfolio/).


## Artigos-semente

- 2024, Fine-Tuning or Retrieval? Comparing Knowledge Injection in LLMs, [EMNLP](https://doi.org/10.18653/v1/2024.emnlp-main.15) [arXiv](https://arxiv.org/abs/2312.05934)

- 2024, Does Fine-Tuning LLMs on New Knowledge Encourage Hallucinations?, [EMNLP](https://doi.org/10.18653/v1/2024.emnlp-main.444) [arXiv](https://arxiv.org/abs/2405.05904)


## Survey

- 2025, A Survey of Context Engineering for Large Language Models, [arXiv](https://arxiv.org/abs/2507.13334)

- 2024, Graph Retrieval-Augmented Generation: A Survey, [ACM TOIS](https://doi.org/10.1145/3777378) [arXiv](https://arxiv.org/abs/2408.08921)

- 2024, Know Your Limits: A Survey of Abstention in Large Language Models, [TACL](https://doi.org/10.1162/tacl_a_00754) [arXiv](https://arxiv.org/abs/2407.18418)

- 2024, Knowledge Mechanisms in Large Language Models: A Survey and Perspective, EMNLP [arXiv](https://arxiv.org/abs/2407.15017)

- 2024, Evaluation of Retrieval-Augmented Generation: A Survey, [DOI](https://doi.org/10.1007/978-981-96-1024-2_8) [arXiv](https://arxiv.org/abs/2405.07437)

- 2024, Knowledge Conflicts for LLMs: A Survey, EMNLP [arXiv](https://arxiv.org/abs/2403.08319)

- 2024, Continual Learning for Large Language Models: A Survey, [arXiv](https://arxiv.org/abs/2402.01364)

- 2024, A Comprehensive Study of Knowledge Editing for Large Language Models, [arXiv](https://arxiv.org/abs/2401.01286)

- 2023, Retrieval-Augmented Generation for Large Language Models: A Survey, [arXiv](https://arxiv.org/abs/2312.10997)

- 2023, A Survey on Hallucination in Large Language Models: Principles, Taxonomy, Challenges, and Open Questions, [ACM TOIS](https://doi.org/10.1145/3703155) [arXiv](https://arxiv.org/abs/2311.05232)

- 2023, Survey of Vector Database Management Systems, [VLDB Journal](https://doi.org/10.1007/s00778-024-00864-x) [arXiv](https://arxiv.org/abs/2310.14021)

- 2023, Siren's Song in the AI Ocean: A Survey on Hallucination in Large Language Models, [Computational Linguistics](https://doi.org/10.1162/coli.a.16) [arXiv](https://arxiv.org/abs/2309.01219)

- 2024, Decision-Focused Learning: Foundations, State of the Art, Benchmark and Future Opportunities, [JAIR](https://doi.org/10.1613/jair.1.15320) [arXiv](https://arxiv.org/abs/2307.13565)

- 2024, Unifying Large Language Models and Knowledge Graphs: A Roadmap, [IEEE TKDE](https://doi.org/10.1109/TKDE.2024.3352100) [arXiv](https://arxiv.org/abs/2306.08302)

- 2023, Editing Large Language Models: Problems, Methods, and Opportunities, EMNLP [arXiv](https://arxiv.org/abs/2305.13172)

- 2022, Machine Learning Operations (MLOps): Overview, Definition, and Architecture, [IEEE Access](https://doi.org/10.1109/ACCESS.2023.3262138) [arXiv](https://arxiv.org/abs/2205.02302)

- 2022, Survey of Hallucination in Natural Language Generation, [ACM CSUR](https://doi.org/10.1145/3571730) [arXiv](https://arxiv.org/abs/2202.03629)

- 2021, A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification, [arXiv](https://arxiv.org/abs/2107.07511)

- 2021, Towards Causal Representation Learning, Proc. IEEE [arXiv](https://arxiv.org/abs/2102.11107)

- 2023, Combinatorial optimization and reasoning with graph neural networks, [JMLR](https://doi.org/10.24963/ijcai.2021/595) [arXiv](https://arxiv.org/abs/2102.09544)

- 2020, Challenges in Deploying Machine Learning: a Survey of Case Studies, [ACM CSUR](https://doi.org/10.1145/3533378) [arXiv](https://arxiv.org/abs/2011.09926)

- 2018, Learning under Concept Drift: A Review, [IEEE TKDE](https://doi.org/10.1109/TKDE.2018.2876857) [arXiv](https://arxiv.org/abs/2004.05785)

- 2018, Data Lifecycle Challenges in Production Machine Learning: A Survey, [SIGMOD Record](https://doi.org/10.1145/3299887.3299891)

- 2018, Machine Learning for Combinatorial Optimization: a Methodological Tour d'Horizon, [EJOR](https://doi.org/10.1016/j.ejor.2020.07.063) [arXiv](https://arxiv.org/abs/1811.06128)

- 2018, The Hitchhiker’s Guide to Testing Statistical Significance in Natural Language Processing, [ACL](https://doi.org/10.18653/v1/P18-1128)

- 2014, A survey on concept drift adaptation, [ACM CSUR](https://doi.org/10.1145/2523813)

- 2011, Surrogate-assisted evolutionary computation: Recent advances and future challenges, [Swarm Evol. Comput.](https://doi.org/10.1016/j.swevo.2011.05.001)


## Papers&Codes

[Aquisição, atualização e representação de conhecimento](#a) · [Confiabilidade, alucinações e avaliação](#b) · [Arquiteturas modernas de sistemas de IA](#c) · [Recuperação de informação e bases de conhecimento](#d) · [Ciência de Dados, experimentação e otimização](#e) · [Engenharia de Dados para sistemas de IA](#f) · [MLOps, LLMOps e operação em produção](#g)


<a id="a"></a>

### Aquisição, atualização e representação de conhecimento

| ID | Year | Title | Model | Published | Code |
| -- | ---- | ----- | ----- | --------- | ---- |
| [1] | 2014 | Distilling the Knowledge in a Neural Network | - | NIPS Workshop [arXiv](https://arxiv.org/abs/1503.02531) | - |
| [2] | 2016 | Overcoming catastrophic forgetting in neural networks | - | [PNAS](https://doi.org/10.1073/pnas.1611835114) [arXiv](https://arxiv.org/abs/1612.00796) | - |
| [3] | 2020 | REALM: Retrieval-Augmented Language Model Pre-Training | REALM | ICML [arXiv](https://arxiv.org/abs/2002.08909) | - |
| [4] | 2020 | Don't Stop Pretraining: Adapt Language Models to Domains and Tasks | Don't Stop Pretraining | [ACL](https://doi.org/10.18653/v1/2020.acl-main.740) [arXiv](https://arxiv.org/abs/2004.10964) | - |
| [5] | 2020 | Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks | - | NeurIPS [arXiv](https://arxiv.org/abs/2005.11401) | - |
| [6] | 2020 | Leveraging Passage Retrieval with Generative Models for Open Domain Question Answering | - | [EACL](https://doi.org/10.18653/v1/2021.eacl-main.74) [arXiv](https://arxiv.org/abs/2007.01282) | - |
| [7] | 2021 | LoRA: Low-Rank Adaptation of Large Language Models | LoRA | ICLR [arXiv](https://arxiv.org/abs/2106.09685) | [code](https://github.com/microsoft/LoRA)![GitHub stars](http://img.shields.io/github/stars/microsoft/LoRA.svg?logo=github&label=Stars) |
| [8] | 2021 | Improving language models by retrieving from trillions of tokens | - | ICML [arXiv](https://arxiv.org/abs/2112.04426) | - |
| [9] | 2022 | Locating and Editing Factual Associations in GPT | - | [NeurIPS](https://doi.org/10.52202/068431-1262) [arXiv](https://arxiv.org/abs/2202.05262) | - |
| [10] | 2022 | Model soups: averaging weights of multiple fine-tuned models improves accuracy without increasing inference time | Model soups | ICML [arXiv](https://arxiv.org/abs/2203.05482) | [code](https://github.com/mlfoundations/model-soups)![GitHub stars](http://img.shields.io/github/stars/mlfoundations/model-soups.svg?logo=github&label=Stars) |
| [11] | 2022 | Atlas: Few-shot Learning with Retrieval Augmented Language Models | Atlas | JMLR [arXiv](https://arxiv.org/abs/2208.03299) | - |
| [12] | 2022 | Mass-Editing Memory in a Transformer | - | ICLR [arXiv](https://arxiv.org/abs/2210.07229) | - |
| [13] | 2022 | Large Language Models Struggle to Learn Long-Tail Knowledge | - | ICML [arXiv](https://arxiv.org/abs/2211.08411) | - |
| [14] | 2022 | Editing Models with Task Arithmetic | - | ICLR [arXiv](https://arxiv.org/abs/2212.04089) | - |
| [15] | 2022 | When Not to Trust Language Models: Investigating Effectiveness of Parametric and Non-Parametric Memories | - | [ACL](https://doi.org/10.18653/v1/2023.acl-long.546) [arXiv](https://arxiv.org/abs/2212.10511) | [code](https://github.com/AlexTMallen/adaptive-retrieval)![GitHub stars](http://img.shields.io/github/stars/AlexTMallen/adaptive-retrieval.svg?logo=github&label=Stars) |
| [16] | 2023 | REPLUG: Retrieval-Augmented Black-Box Language Models | REPLUG | NAACL [arXiv](https://arxiv.org/abs/2301.12652) | - |
| [17] | 2023 | In-Context Retrieval-Augmented Language Models | - | [TACL](https://doi.org/10.1162/tacl_a_00605) [arXiv](https://arxiv.org/abs/2302.00083) | - |
| [18] | 2023 | LIMA: Less Is More for Alignment | LIMA | [NeurIPS](https://doi.org/10.52202/075280-2400) [arXiv](https://arxiv.org/abs/2305.11206) | - |
| [19] | 2023 | QLoRA: Efficient Finetuning of Quantized LLMs | QLoRA | NeurIPS [arXiv](https://arxiv.org/abs/2305.14314) | - |
| [20] | 2023 | MQuAKE: Assessing Knowledge Editing in Language Models via Multi-Hop Questions | MQuAKE | EMNLP [arXiv](https://arxiv.org/abs/2305.14795) | [code](https://github.com/princeton-nlp/MQuAKE)![GitHub stars](http://img.shields.io/github/stars/princeton-nlp/MQuAKE.svg?logo=github&label=Stars) |
| [21] | 2023 | TIES-Merging: Resolving Interference When Merging Models | TIES-Merging | [NeurIPS](https://doi.org/10.52202/075280-0310) [arXiv](https://arxiv.org/abs/2306.01708) | [code](https://github.com/prateeky2806/ties-merging)![GitHub stars](http://img.shields.io/github/stars/prateeky2806/ties-merging.svg?logo=github&label=Stars) |
| [22] | 2023 | Evaluating the Ripple Effects of Knowledge Editing in Language Models | - | [TACL](https://doi.org/10.1162/tacl_a_00644) [arXiv](https://arxiv.org/abs/2307.12976) | - |
| [23] | 2023 | An Empirical Study of Catastrophic Forgetting in Large Language Models During Continual Fine-tuning | - | [IEEE TASLP](https://doi.org/10.1109/TASLPRO.2025.3606231) [arXiv](https://arxiv.org/abs/2308.08747) | - |
| [24] | 2023 | The Reversal Curse: LLMs trained on "A is B" fail to learn "B is A" | The Reversal Curse | ICLR [arXiv](https://arxiv.org/abs/2309.12288) | [code](https://github.com/lukasberglund/reversal_curse)![GitHub stars](http://img.shields.io/github/stars/lukasberglund/reversal_curse.svg?logo=github&label=Stars) |
| [25] | 2023 | Physics of Language Models: Part 3.1, Knowledge Storage and Extraction | - | ICML [arXiv](https://arxiv.org/abs/2309.14316) | - |
| [26] | 2024 | RAG vs Fine-tuning: Pipelines, Tradeoffs, and a Case Study on Agriculture | RAG vs Fine-tuning | [arXiv](https://arxiv.org/abs/2401.08406) | - |
| [27] | 2024 | Instruction-tuned Language Models are Better Knowledge Learners | - | ACL [arXiv](https://arxiv.org/abs/2402.12847) | [code](https://github.com/Edward-Sun/PIT)![GitHub stars](http://img.shields.io/github/stars/Edward-Sun/PIT.svg?logo=github&label=Stars) |
| [28] | 2024 | Learning or Self-aligning? Rethinking Instruction Fine-tuning | - | ACL [arXiv](https://arxiv.org/abs/2402.18243) | - |
| [29] | 2024 | Fine Tuning vs. Retrieval Augmented Generation for Less Popular Knowledge | - | [SIGIR-AP](https://doi.org/10.1145/3673791.3698415) [arXiv](https://arxiv.org/abs/2403.01432) | [code](https://github.com/informagi/RAGvsFT)![GitHub stars](http://img.shields.io/github/stars/informagi/RAGvsFT.svg?logo=github&label=Stars) |
| [30] | 2024 | Reliable, Adaptable, and Attributable Language Models with Retrieval | - | [arXiv](https://arxiv.org/abs/2403.03187) | - |
| [31] | 2024 | RAFT: Adapting Language Model to Domain Specific RAG | RAFT | [arXiv](https://arxiv.org/abs/2403.10131) | [code](https://github.com/ShishirPatil/gorilla)![GitHub stars](http://img.shields.io/github/stars/ShishirPatil/gorilla.svg?logo=github&label=Stars) |
| [32] | 2024 | Injecting New Knowledge into Large Language Models via Supervised Fine-Tuning | - | [arXiv](https://arxiv.org/abs/2404.00213) | - |
| [33] | 2024 | FLAME: Factuality-Aware Alignment for Large Language Models | FLAME | NeurIPS [arXiv](https://arxiv.org/abs/2405.01525) | - |
| [34] | 2024 | LoRA Learns Less and Forgets Less | - | TMLR [arXiv](https://arxiv.org/abs/2405.09673) | - |
| [35] | 2024 | WISE: Rethinking the Knowledge Memory for Lifelong Model Editing of Large Language Models | WISE | NeurIPS [arXiv](https://arxiv.org/abs/2405.14768) | [code](https://github.com/zjunlp/EasyEdit)![GitHub stars](http://img.shields.io/github/stars/zjunlp/EasyEdit.svg?logo=github&label=Stars) |
| [36] | 2024 | Self-Tuning: Instructing LLMs to Effectively Acquire New Knowledge through Self-Teaching | Self-Tuning | ACL [arXiv](https://arxiv.org/abs/2406.06326) | - |
| [37] | 2024 | How Do Large Language Models Acquire Factual Knowledge During Pretraining? | - | NeurIPS [arXiv](https://arxiv.org/abs/2406.11813) | - |
| [38] | 2024 | Understanding Finetuning for Factual Knowledge Extraction | - | ICML [arXiv](https://arxiv.org/abs/2406.14785) | - |
| [39] | 2024 | Scaling Laws for Fact Memorization of Large Language Models | - | EMNLP [arXiv](https://arxiv.org/abs/2406.15720) | - |
| [40] | 2024 | Learning Dynamics of LLM Finetuning | - | ICLR [arXiv](https://arxiv.org/abs/2407.10490) | - |
| [41] | 2024 | Synthetic continued pretraining | - | ICLR [arXiv](https://arxiv.org/abs/2409.07431) | - |
| [42] | 2024 | Revisiting the Superficial Alignment Hypothesis | - | [arXiv](https://arxiv.org/abs/2410.03717) | - |
| [43] | 2024 | Fictitious Synthetic Data Can Improve LLM Factuality via Prerequisite Learning | - | ICLR [arXiv](https://arxiv.org/abs/2410.19290) | [code](https://github.com/UCSB-NLP-Chang/Prereq_tune.git)![GitHub stars](http://img.shields.io/github/stars/UCSB-NLP-Chang/Prereq_tune.svg?logo=github&label=Stars) |
| [44] | 2024 | FineTuneBench: How well do commercial fine-tuning APIs infuse knowledge into LLMs? | FineTuneBench | [arXiv](https://arxiv.org/abs/2411.05059) | [code](https://github.com/kevinwu23/StanfordFineTuneBench)![GitHub stars](http://img.shields.io/github/stars/kevinwu23/StanfordFineTuneBench.svg?logo=github&label=Stars) |
| [45] | 2024 | Efficient Knowledge Injection in LLMs via Self-Distillation | - | TMLR [arXiv](https://arxiv.org/abs/2412.14964) | - |
| [46] | 2025 | SimRAG: Self-Improving Retrieval-Augmented Generation for Adapting Large Language Models to Specialized Domains | SimRAG | NAACL [arXiv](https://arxiv.org/abs/2410.17952) | - |
| [47] | 2025 | Upweighting Easy Samples in Fine-Tuning Mitigates Forgetting | - | ICML [arXiv](https://arxiv.org/abs/2502.02797) | [code](https://github.com/sanyalsunny111/FLOW_finetuning)![GitHub stars](http://img.shields.io/github/stars/sanyalsunny111/FLOW_finetuning.svg?logo=github&label=Stars) |
| [48] | 2025 | How Do LLMs Acquire New Knowledge? A Knowledge Circuits Perspective on Continual Pre-Training | - | ACL [arXiv](https://arxiv.org/abs/2502.11196) | [code](https://github.com/zjunlp/DynamicKnowledgeCircuits)![GitHub stars](http://img.shields.io/github/stars/zjunlp/DynamicKnowledgeCircuits.svg?logo=github&label=Stars) |
| [49] | 2025 | From Style to Facts: Mapping the Boundaries of Knowledge Injection with Finetuning | - | NeurIPS [arXiv](https://arxiv.org/abs/2503.05919) | - |
| [50] | 2025 | How do language models learn facts? Dynamics, curricula and hallucinations | - | COLM [arXiv](https://arxiv.org/abs/2503.21676) | - |
| [51] | 2025 | Memorization vs. Reasoning: Updating LLMs with New Knowledge | - | ACL [arXiv](https://arxiv.org/abs/2504.12523) | - |
| [52] | 2025 | On the generalization of language models from in-context learning and finetuning: a controlled study | - | [arXiv](https://arxiv.org/abs/2505.00661) | - |
| [53] | 2025 | Data Doping or True Intelligence? Evaluating the Transferability of Injected Knowledge in LLMs | - | EMNLP [arXiv](https://arxiv.org/abs/2505.17140) | - |
| [54] | 2025 | Comparing Knowledge Injection Methods for LLMs in a Low-Resource Regime | - | ENIAC [arXiv](https://arxiv.org/abs/2508.06178) | [code](https://github.com/hugoabonizio/knowledge-injection-methods)![GitHub stars](http://img.shields.io/github/stars/hugoabonizio/knowledge-injection-methods.svg?logo=github&label=Stars) |
| [55] | 2026 | Fine-Tuning vs. RAG for Multi-Hop Question Answering with Novel Knowledge | - | IEEE GEM [arXiv](https://arxiv.org/abs/2601.07054) | - |
| [56] | 2026 | SPA: A Simple but Tough-to-Beat Baseline for Knowledge Injection | SPA | [arXiv](https://arxiv.org/abs/2603.22213) | [code](https://github.com/Tangkexian/SPA)![GitHub stars](http://img.shields.io/github/stars/Tangkexian/SPA.svg?logo=github&label=Stars) |

<a id="b"></a>

### Confiabilidade, alucinações e avaliação

| ID | Year | Title | Model | Published | Code |
| -- | ---- | ----- | ----- | --------- | ---- |
| [57] | 2017 | Selective Classification for Deep Neural Networks | - | NeurIPS [arXiv](https://arxiv.org/abs/1705.08500) | - |
| [58] | 2017 | On Calibration of Modern Neural Networks | - | ICML [arXiv](https://arxiv.org/abs/1706.04599) | - |
| [59] | 2021 | Mind the Gap: Assessing Temporal Generalization in Neural Language Models | Mind the Gap | NeurIPS [arXiv](https://arxiv.org/abs/2102.01951) | - |
| [60] | 2021 | TruthfulQA: Measuring How Models Mimic Human Falsehoods | TruthfulQA | [ACL](https://doi.org/10.18653/v1/2022.acl-long.229) [arXiv](https://arxiv.org/abs/2109.07958) | [code](https://github.com/sylinrl/TruthfulQA)![GitHub stars](http://img.shields.io/github/stars/sylinrl/TruthfulQA.svg?logo=github&label=Stars) |
| [61] | 2021 | Entity-Based Knowledge Conflicts in Question Answering | - | [EMNLP](https://doi.org/10.18653/v1/2021.emnlp-main.565) [arXiv](https://arxiv.org/abs/2109.05052) | - |
| [62] | 2021 | Measuring Attribution in Natural Language Generation Models | - | [Computational Linguistics](https://doi.org/10.1162/coli_a_00486) [arXiv](https://arxiv.org/abs/2112.12870) | - |
| [63] | 2022 | Language Models (Mostly) Know What They Know | - | [arXiv](https://arxiv.org/abs/2207.05221) | - |
| [64] | 2022 | RealTime QA: What's the Answer Right Now? | RealTime QA | NeurIPS [arXiv](https://arxiv.org/abs/2207.13332) | - |
| [65] | 2022 | Holistic Evaluation of Language Models | - | TMLR [arXiv](https://arxiv.org/abs/2211.09110) | - |
| [66] | 2023 | Semantic Uncertainty: Linguistic Invariances for Uncertainty Estimation in Natural Language Generation | Semantic Uncertainty | ICLR [arXiv](https://arxiv.org/abs/2302.09664) | - |
| [67] | 2023 | Not what you've signed up for: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection | - | [AISec@CCS](https://doi.org/10.1145/3605764.3623985) [arXiv](https://arxiv.org/abs/2302.12173) | - |
| [68] | 2023 | SelfCheckGPT: Zero-Resource Black-Box Hallucination Detection for Generative Large Language Models | SelfCheckGPT | EMNLP [arXiv](https://arxiv.org/abs/2303.08896) | - |
| [69] | 2023 | Adaptive Chameleon or Stubborn Sloth: Revealing the Behavior of Large Language Models in Knowledge Conflicts | - | ICLR [arXiv](https://arxiv.org/abs/2305.13300) | [code](https://github.com/OSU-NLP-Group/LLM-Knowledge-Conflict)![GitHub stars](http://img.shields.io/github/stars/OSU-NLP-Group/LLM-Knowledge-Conflict.svg?logo=github&label=Stars) |
| [70] | 2023 | FActScore: Fine-grained Atomic Evaluation of Factual Precision in Long Form Text Generation | FActScore | EMNLP [arXiv](https://arxiv.org/abs/2305.14251) | [code](https://github.com/shmsw25/FActScore)![GitHub stars](http://img.shields.io/github/stars/shmsw25/FActScore.svg?logo=github&label=Stars) |
| [71] | 2023 | Enabling Large Language Models to Generate Text with Citations | - | EMNLP [arXiv](https://arxiv.org/abs/2305.14627) | [code](https://github.com/princeton-nlp/ALCE)![GitHub stars](http://img.shields.io/github/stars/princeton-nlp/ALCE.svg?logo=github&label=Stars) |
| [72] | 2023 | Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena | - | [NeurIPS](https://doi.org/10.52202/075280-2020) [arXiv](https://arxiv.org/abs/2306.05685) | [code](https://github.com/lm-sys/FastChat/tree/main/fastchat/llm_judge)![GitHub stars](http://img.shields.io/github/stars/lm-sys/FastChat.svg?logo=github&label=Stars) |
| [73] | 2023 | Time Travel in LLMs: Tracing Data Contamination in Large Language Models | - | ICLR [arXiv](https://arxiv.org/abs/2308.08493) | - |
| [74] | 2023 | Chain-of-Verification Reduces Hallucination in Large Language Models | - | ACL [arXiv](https://arxiv.org/abs/2309.11495) | - |
| [75] | 2023 | Ragas: Automated Evaluation of Retrieval Augmented Generation | Ragas | EACL [arXiv](https://arxiv.org/abs/2309.15217) | - |
| [76] | 2023 | FreshLLMs: Refreshing Large Language Models with Search Engine Augmentation | FreshLLMs | ACL [arXiv](https://arxiv.org/abs/2310.03214) | [code](https://github.com/freshllms/freshqa)![GitHub stars](http://img.shields.io/github/stars/freshllms/freshqa.svg?logo=github&label=Stars) |
| [77] | 2023 | NeMo Guardrails: A Toolkit for Controllable and Safe LLM Applications with Programmable Rails | NeMo Guardrails | EMNLP [arXiv](https://arxiv.org/abs/2310.10501) | - |
| [78] | 2023 | Proving Test Set Contamination in Black Box Language Models | - | ICLR [arXiv](https://arxiv.org/abs/2310.17623) | - |
| [79] | 2023 | NLP Evaluation in trouble: On the Need to Measure LLM Data Contamination for each Benchmark | - | EMNLP Findings [arXiv](https://arxiv.org/abs/2310.18018) | - |
| [80] | 2023 | R-Tuning: Instructing Large Language Models to Say `I Don't Know' | R-Tuning | [NAACL](https://doi.org/10.18653/v1/2024.naacl-long.394) [arXiv](https://arxiv.org/abs/2311.09677) | [code](https://github.com/shizhediao/R-Tuning)![GitHub stars](http://img.shields.io/github/stars/shizhediao/R-Tuning.svg?logo=github&label=Stars) |
| [81] | 2023 | ARES: An Automated Evaluation Framework for Retrieval-Augmented Generation Systems | ARES | NAACL [arXiv](https://arxiv.org/abs/2311.09476) | - |
| [82] | 2023 | Llama Guard: LLM-based Input-Output Safeguard for Human-AI Conversations | Llama Guard | [arXiv](https://arxiv.org/abs/2312.06674) | - |
| [83] | 2023 | Alignment for Honesty | - | NeurIPS [arXiv](https://arxiv.org/abs/2312.07000) | [code](https://github.com/GAIR-NLP/alignment-for-honesty)![GitHub stars](http://img.shields.io/github/stars/GAIR-NLP/alignment-for-honesty.svg?logo=github&label=Stars) |
| [84] | 2024 | Calibrated Language Models Must Hallucinate | - | [STOC](https://doi.org/10.1145/3618260.3649777) [arXiv](https://arxiv.org/abs/2311.14648) | - |
| [85] | 2024 | PoisonedRAG: Knowledge Corruption Attacks to Retrieval-Augmented Generation of Large Language Models | PoisonedRAG | USENIX Security [arXiv](https://arxiv.org/abs/2402.07867) | [code](https://github.com/sleeepeer/PoisonedRAG)![GitHub stars](http://img.shields.io/github/stars/sleeepeer/PoisonedRAG.svg?logo=github&label=Stars) |
| [86] | 2024 | Language Models with Conformal Factuality Guarantees | - | ICML [arXiv](https://arxiv.org/abs/2402.10978) | - |
| [87] | 2024 | Unfamiliar Finetuning Examples Control How Language Models Hallucinate | - | NAACL [arXiv](https://arxiv.org/abs/2403.05612) | - |
| [88] | 2024 | Detecting hallucinations in large language models using semantic entropy | - | [Nature](https://doi.org/10.1038/s41586-024-07421-0) | - |
| [89] | 2024 | LLMs Know More Than They Show: On the Intrinsic Representation of LLM Hallucinations | - | ICLR [arXiv](https://arxiv.org/abs/2410.02707) | - |
| [90] | 2025 | HalluLens: LLM Hallucination Benchmark | HalluLens | ACL [arXiv](https://arxiv.org/abs/2504.17550) | - |
| [91] | 2025 | The Hallucination Tax of Reinforcement Finetuning | - | EMNLP [arXiv](https://arxiv.org/abs/2505.13988) | - |
| [92] | 2025 | Why Language Models Hallucinate | - | [arXiv](https://arxiv.org/abs/2509.04664) | - |
| [93] | 2026 | Why Fine-Tuning Encourages Hallucinations and How to Fix It | - | [arXiv](https://arxiv.org/abs/2604.15574) | - |

<a id="c"></a>

### Arquiteturas modernas de sistemas de IA

| ID | Year | Title | Model | Published | Code |
| -- | ---- | ----- | ----- | --------- | ---- |
| [94] | 2017 | Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer | - | ICLR [arXiv](https://arxiv.org/abs/1701.06538) | - |
| [95] | 2021 | Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity | Switch Transformers | JMLR [arXiv](https://arxiv.org/abs/2101.03961) | - |
| [96] | 2021 | Learning Transferable Visual Models From Natural Language Supervision | - | ICML [arXiv](https://arxiv.org/abs/2103.00020) | [code](https://github.com/OpenAI/CLIP)![GitHub stars](http://img.shields.io/github/stars/OpenAI/CLIP.svg?logo=github&label=Stars) |
| [97] | 2022 | Chain-of-Thought Prompting Elicits Reasoning in Large Language Models | - | [NeurIPS](https://doi.org/10.52202/068431-1800) [arXiv](https://arxiv.org/abs/2201.11903) | - |
| [98] | 2022 | Self-Consistency Improves Chain of Thought Reasoning in Language Models | - | ICLR [arXiv](https://arxiv.org/abs/2203.11171) | - |
| [99] | 2022 | ReAct: Synergizing Reasoning and Acting in Language Models | ReAct | ICLR [arXiv](https://arxiv.org/abs/2210.03629) | - |
| [100] | 2023 | Toolformer: Language Models Can Teach Themselves to Use Tools | Toolformer | NeurIPS [arXiv](https://arxiv.org/abs/2302.04761) | - |
| [101] | 2023 | Reflexion: Language Agents with Verbal Reinforcement Learning | Reflexion | [NeurIPS](https://doi.org/10.52202/075280-0377) [arXiv](https://arxiv.org/abs/2303.11366) | - |
| [102] | 2023 | Generative Agents: Interactive Simulacra of Human Behavior | Generative Agents | [UIST](https://doi.org/10.1145/3586183.3606763) [arXiv](https://arxiv.org/abs/2304.03442) | - |
| [103] | 2023 | FrugalGPT: How to Use Large Language Models While Reducing Cost and Improving Performance | FrugalGPT | TMLR [arXiv](https://arxiv.org/abs/2305.05176) | - |
| [104] | 2023 | Gorilla: Large Language Model Connected with Massive APIs | Gorilla | [NeurIPS](https://doi.org/10.52202/079017-4020) [arXiv](https://arxiv.org/abs/2305.15334) | - |
| [105] | 2023 | Lost in the Middle: How Language Models Use Long Contexts | - | [TACL](https://doi.org/10.1162/tacl_a_00638) [arXiv](https://arxiv.org/abs/2307.03172) | - |
| [106] | 2023 | AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation | AutoGen | [arXiv](https://arxiv.org/abs/2308.08155) | - |
| [107] | 2023 | Retrieval meets Long Context Large Language Models | - | ICLR [arXiv](https://arxiv.org/abs/2310.03025) | - |
| [108] | 2023 | DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines | DSPy | [arXiv](https://arxiv.org/abs/2310.03714) | [code](https://github.com/stanfordnlp/dspy)![GitHub stars](http://img.shields.io/github/stars/stanfordnlp/dspy.svg?logo=github&label=Stars) |
| [109] | 2023 | SWE-bench: Can Language Models Resolve Real-World GitHub Issues? | SWE-bench | ICLR [arXiv](https://arxiv.org/abs/2310.06770) | - |
| [110] | 2023 | MemGPT: Towards LLMs as Operating Systems | MemGPT | [arXiv](https://arxiv.org/abs/2310.08560) | - |
| [111] | 2023 | Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection | Self-RAG | ICLR [arXiv](https://arxiv.org/abs/2310.11511) | - |
| [112] | 2024 | Mixtral of Experts | - | [arXiv](https://arxiv.org/abs/2401.04088) | - |
| [113] | 2024 | Corrective Retrieval Augmented Generation | - | [arXiv](https://arxiv.org/abs/2401.15884) | - |
| [114] | 2024 | Adaptive-RAG: Learning to Adapt Retrieval-Augmented Large Language Models through Question Complexity | Adaptive-RAG | NAACL [arXiv](https://arxiv.org/abs/2403.14403) | [code](https://github.com/starsuzi/Adaptive-RAG)![GitHub stars](http://img.shields.io/github/stars/starsuzi/Adaptive-RAG.svg?logo=github&label=Stars) |
| [115] | 2024 | Mixture-of-Agents Enhances Large Language Model Capabilities | - | ICLR [arXiv](https://arxiv.org/abs/2406.04692) | - |
| [116] | 2024 | RouteLLM: Learning to Route LLMs with Preference Data | RouteLLM | [arXiv](https://arxiv.org/abs/2406.18665) | - |
| [117] | 2024 | AI Agents That Matter | - | TMLR [arXiv](https://arxiv.org/abs/2407.01502) | - |
| [118] | 2024 | Retrieval Augmented Generation or Long-Context LLMs? A Comprehensive Study and Hybrid Approach | - | EMNLP [arXiv](https://arxiv.org/abs/2407.16833) | - |
| [119] | 2025 | Why Do Multi-Agent LLM Systems Fail? | - | NeurIPS [arXiv](https://arxiv.org/abs/2503.13657) | - |
| [120] | 2025 | Small Language Models are the Future of Agentic AI | - | [arXiv](https://arxiv.org/abs/2506.02153) | - |

<a id="d"></a>

### Recuperação de informação e bases de conhecimento

| ID | Year | Title | Model | Published | Code |
| -- | ---- | ----- | ----- | --------- | ---- |
| [121] | 2002 | Cumulated gain-based evaluation of IR techniques | - | [ACM TOIS](https://doi.org/10.1145/582415.582418) | - |
| [122] | 2009 | Reciprocal rank fusion outperforms condorcet and individual rank learning methods | - | [SIGIR](https://doi.org/10.1145/1571941.1572114) | - |
| [123] | 2009 | The Probabilistic Relevance Framework: BM25 and Beyond | - | [FnTIR](https://doi.org/10.1561/1500000019) | - |
| [124] | 2016 | Efficient and robust approximate nearest neighbor search using Hierarchical Navigable Small World graphs | - | [IEEE TPAMI](https://doi.org/10.1109/TPAMI.2018.2889473) [arXiv](https://arxiv.org/abs/1603.09320) | - |
| [125] | 2016 | MS MARCO: A Human Generated MAchine Reading COmprehension Dataset | MS MARCO | NIPS Workshop [arXiv](https://arxiv.org/abs/1611.09268) | - |
| [126] | 2017 | Billion-scale similarity search with GPUs | - | [IEEE TBD](https://doi.org/10.1109/tbdata.2019.2921572) [arXiv](https://arxiv.org/abs/1702.08734) | - |
| [127] | 2018 | ANN-Benchmarks: A Benchmarking Tool for Approximate Nearest Neighbor Algorithms | ANN-Benchmarks | [SISAP](https://doi.org/10.1007/978-3-319-68474-1_3) [arXiv](https://arxiv.org/abs/1807.05614) | - |
| [128] | 2019 | DiskANN : Fast Accurate Billion-point Nearest Neighbor Search on a Single Node | DiskANN | [NeurIPS?](https://www.semanticscholar.org/paper/ae3db2312066a6a6696aeb7cad2778c193c017ea) | - |
| [129] | 2019 | Passage Re-ranking with BERT | - | [arXiv](https://arxiv.org/abs/1901.04085) | [code](https://github.com/nyu-dl/dl4marco-bert)![GitHub stars](http://img.shields.io/github/stars/nyu-dl/dl4marco-bert.svg?logo=github&label=Stars) |
| [130] | 2020 | Accelerating Large-Scale Inference with Anisotropic Vector Quantization | - | ICML [arXiv](https://arxiv.org/abs/1908.10396) | - |
| [131] | 2020 | Dense Passage Retrieval for Open-Domain Question Answering | - | [EMNLP](https://doi.org/10.18653/v1/2020.emnlp-main.550) [arXiv](https://arxiv.org/abs/2004.04906) | - |
| [132] | 2020 | ColBERT: Efficient and Effective Passage Search via Contextualized Late Interaction over BERT | ColBERT | [SIGIR](https://doi.org/10.1145/3397271.3401075) [arXiv](https://arxiv.org/abs/2004.12832) | - |
| [133] | 2021 | BEIR: A Heterogenous Benchmark for Zero-shot Evaluation of Information Retrieval Models | BEIR | NeurIPS D&B [arXiv](https://arxiv.org/abs/2104.08663) | [code](https://github.com/UKPLab/beir)![GitHub stars](http://img.shields.io/github/stars/UKPLab/beir.svg?logo=github&label=Stars) |
| [134] | 2021 | SPLADE: Sparse Lexical and Expansion Model for First Stage Ranking | SPLADE | [SIGIR](https://doi.org/10.1145/3404835.3463098) [arXiv](https://arxiv.org/abs/2107.05720) | - |
| [135] | 2021 | ColBERTv2: Effective and Efficient Retrieval via Lightweight Late Interaction | ColBERTv2 | [NAACL](https://doi.org/10.18653/v1/2022.naacl-main.272) [arXiv](https://arxiv.org/abs/2112.01488) | - |
| [136] | 2021 | Unsupervised Dense Information Retrieval with Contrastive Learning | - | TMLR [arXiv](https://arxiv.org/abs/2112.09118) | - |
| [137] | 2022 | Least-to-Most Prompting Enables Complex Reasoning in Large Language Models | - | ICLR [arXiv](https://arxiv.org/abs/2205.10625) | - |
| [138] | 2022 | Matryoshka Representation Learning | - | [NeurIPS](https://doi.org/10.52202/068431-2192) [arXiv](https://arxiv.org/abs/2205.13147) | [code](https://github.com/RAIVNLab/MRL)![GitHub stars](http://img.shields.io/github/stars/RAIVNLab/MRL.svg?logo=github&label=Stars) |
| [139] | 2022 | MTEB: Massive Text Embedding Benchmark | MTEB | [EACL](https://doi.org/10.18653/v1/2023.eacl-main.148) [arXiv](https://arxiv.org/abs/2210.07316) | [code](https://github.com/embeddings-benchmark/mteb)![GitHub stars](http://img.shields.io/github/stars/embeddings-benchmark/mteb.svg?logo=github&label=Stars) |
| [140] | 2022 | Text Embeddings by Weakly-Supervised Contrastive Pre-training | - | [arXiv](https://arxiv.org/abs/2212.03533) | - |
| [141] | 2022 | Precise Zero-Shot Dense Retrieval without Relevance Labels | - | [ACL](https://doi.org/10.18653/v1/2023.acl-long.99) [arXiv](https://arxiv.org/abs/2212.10496) | - |
| [142] | 2022 | Interleaving Retrieval with Chain-of-Thought Reasoning for Knowledge-Intensive Multi-Step Questions | - | ACL [arXiv](https://arxiv.org/abs/2212.10509) | [code](https://github.com/stonybrooknlp/ircot)![GitHub stars](http://img.shields.io/github/stars/stonybrooknlp/ircot.svg?logo=github&label=Stars) |
| [143] | 2023 | Measuring and Narrowing the Compositionality Gap in Language Models | - | EMNLP Findings [arXiv](https://arxiv.org/abs/2210.03350) | - |
| [144] | 2023 | Query2doc: Query Expansion with Large Language Models | Query2doc | EMNLP [arXiv](https://arxiv.org/abs/2303.07678) | - |
| [145] | 2023 | Is ChatGPT Good at Search? Investigating Large Language Models as Re-Ranking Agents | - | EMNLP [arXiv](https://arxiv.org/abs/2304.09542) | [code](https://github.com/sunnweiwei/RankGPT)![GitHub stars](http://img.shields.io/github/stars/sunnweiwei/RankGPT.svg?logo=github&label=Stars) |
| [146] | 2023 | Dense X Retrieval: What Retrieval Granularity Should We Use? | Dense X Retrieval | EMNLP [arXiv](https://arxiv.org/abs/2312.06648) | - |
| [147] | 2024 | Seven Failure Points When Engineering a Retrieval Augmented Generation System | - | [CAIN](https://doi.org/10.1145/3644815.3644945) [arXiv](https://arxiv.org/abs/2401.05856) | - |
| [148] | 2024 | RAPTOR: Recursive Abstractive Processing for Tree-Organized Retrieval | RAPTOR | ICLR [arXiv](https://arxiv.org/abs/2401.18059) | - |
| [149] | 2024 | From Local to Global: A Graph RAG Approach to Query-Focused Summarization | - | [arXiv](https://arxiv.org/abs/2404.16130) | - |
| [150] | 2024 | HippoRAG: Neurobiologically Inspired Long-Term Memory for Large Language Models | HippoRAG | NeurIPS [arXiv](https://arxiv.org/abs/2405.14831) | [code](https://github.com/OSU-NLP-Group/HippoRAG)![GitHub stars](http://img.shields.io/github/stars/OSU-NLP-Group/HippoRAG.svg?logo=github&label=Stars) |
| [151] | 2024 | ColPali: Efficient Document Retrieval with Vision Language Models | ColPali | ICLR [arXiv](https://arxiv.org/abs/2407.01449) | [code](https://hf.co/vidore) |
| [152] | 2024 | Late Chunking: Contextual Chunk Embeddings Using Long-Context Embedding Models | Late Chunking | [arXiv](https://arxiv.org/abs/2409.04701) | - |
| [153] | 2024 | LightRAG: Simple and Fast Retrieval-Augmented Generation | LightRAG | EMNLP [arXiv](https://arxiv.org/abs/2410.05779) | [code](https://github.com/HKUDS/LightRAG)![GitHub stars](http://img.shields.io/github/stars/HKUDS/LightRAG.svg?logo=github&label=Stars) |

<a id="e"></a>

### Ciência de Dados, experimentação e otimização

| ID | Year | Title | Model | Published | Code |
| -- | ---- | ----- | ----- | --------- | ---- |
| [154] | 1998 | Approximate Statistical Tests for Comparing Supervised Classification Learning Algorithms | - | [Neural Computation](https://doi.org/10.1162/089976698300017197) | - |
| [155] | 2006 | Statistical Comparisons of Classifiers over Multiple Data Sets | - | [JMLR](https://jmlr.org/papers/v7/demsar06a.html) | - |
| [156] | 2006 | Bias in error estimation when using cross-validation for model selection | - | [BMC Bioinformatics](https://doi.org/10.1186/1471-2105-7-91) | - |
| [157] | 2008 | Controlled experiments on the web: survey and practical guide | - | [DMKD](https://doi.org/10.1007/s10618-008-0114-1) | - |
| [158] | 2009 | Causal inference in statistics: An overview | - | [Statistics Surveys](https://doi.org/10.1214/09-SS057) | - |
| [159] | 2011 | Algorithms for Hyper-Parameter Optimization | - | [NeurIPS](https://dblp.org/rec/conf/nips/BergstraBBK11) | - |
| [160] | 2012 | Random Search for Hyper-Parameter Optimization | - | [JMLR](https://jmlr.org/papers/v13/bergstra12a.html) | - |
| [161] | 2012 | Practical Bayesian Optimization of Machine Learning Algorithms | - | NeurIPS [arXiv](https://arxiv.org/abs/1206.2944) | - |
| [162] | 2012 | Leakage in data mining: Formulation, detection, and avoidance | - | [ACM TKDD](https://doi.org/10.1145/2382577.2382579) | - |
| [163] | 2013 | Improving the sensitivity of online controlled experiments by utilizing pre-experiment data | - | [WSDM](https://doi.org/10.1145/2433396.2433413) | - |
| [164] | 2013 | Metaheuristics—the metaphor exposed | - | [ITOR](https://doi.org/10.1111/itor.12001) | - |
| [165] | 2015 | Human-level control through deep reinforcement learning | - | [Nature](https://doi.org/10.1038/nature14236) | - |
| [166] | 2015 | Recursive Partitioning for Heterogeneous Causal Effects | - | [PNAS](https://doi.org/10.1073/pnas.1510489113) [arXiv](https://arxiv.org/abs/1504.01132) | - |
| [167] | 2015 | Pointer Networks | - | NeurIPS [arXiv](https://arxiv.org/abs/1506.03134) | - |
| [168] | 2016 | XGBoost: A Scalable Tree Boosting System | XGBoost | [KDD](https://doi.org/10.1145/2939672.2939785) [arXiv](https://arxiv.org/abs/1603.02754) | - |
| [169] | 2016 | Double/Debiased Machine Learning for Treatment and Causal Parameters | - | [arXiv](https://arxiv.org/abs/1608.00060) | - |
| [170] | 2016 | Semi-Supervised Classification with Graph Convolutional Networks | - | ICLR [arXiv](https://arxiv.org/abs/1609.02907) | - |
| [171] | 2017 | Neural Message Passing for Quantum Chemistry | - | ICML [arXiv](https://arxiv.org/abs/1704.01212) | - |
| [172] | 2017 | Proximal Policy Optimization Algorithms | - | [arXiv](https://arxiv.org/abs/1707.06347) | - |
| [173] | 2017 | Deep Reinforcement Learning that Matters | - | [AAAI](https://doi.org/10.1609/aaai.v32i1.11694) [arXiv](https://arxiv.org/abs/1709.06560) | - |
| [174] | 2017 | Smart "Predict, then Optimize" | - | [Management Science](https://doi.org/10.1287/MNSC.2020.3922) [arXiv](https://arxiv.org/abs/1710.08005) | - |
| [175] | 2018 | Hyperband: A Novel Bandit-Based Approach to Hyperparameter Optimization | Hyperband | JMLR [arXiv](https://arxiv.org/abs/1603.06560) | - |
| [176] | 2018 | Graph Attention Networks | - | ICLR [arXiv](https://arxiv.org/abs/1710.10903) | - |
| [177] | 2018 | Attention, Learn to Solve Routing Problems! | - | ICLR [arXiv](https://arxiv.org/abs/1803.08475) | - |
| [178] | 2018 | A note on the validity of cross-validation for evaluating autoregressive time series prediction | - | [CSDA](https://doi.org/10.1016/j.csda.2017.11.003) | - |
| [179] | 2018 | BOHB: Robust and Efficient Hyperparameter Optimization at Scale | BOHB | ICML [arXiv](https://arxiv.org/abs/1807.01774) | - |
| [180] | 2019 | N-BEATS: Neural basis expansion analysis for interpretable time series forecasting | N-BEATS | ICLR [arXiv](https://arxiv.org/abs/1905.10437) | - |
| [181] | 2019 | Exact Combinatorial Optimization with Graph Convolutional Neural Networks | - | NeurIPS [arXiv](https://arxiv.org/abs/1906.01629) | [code](https://github.com/ds4dm/learn2branch)![GitHub stars](http://img.shields.io/github/stars/ds4dm/learn2branch.svg?logo=github&label=Stars) |
| [182] | 2019 | Can You Trust Your Model's Uncertainty? Evaluating Predictive Uncertainty Under Dataset Shift | - | NeurIPS [arXiv](https://arxiv.org/abs/1906.02530) | - |
| [183] | 2019 | Optuna: A Next-generation Hyperparameter Optimization Framework | Optuna | [KDD](https://doi.org/10.1145/3292500.3330701) [arXiv](https://arxiv.org/abs/1907.10902) | [code](https://github.com/pfnet/optuna/)![GitHub stars](http://img.shields.io/github/stars/pfnet/optuna.svg?logo=github&label=Stars) |
| [184] | 2020 | The M4 Competition: 100,000 time series and 61 forecasting methods | The M4 Competition | [IJF](https://doi.org/10.1016/j.ijforecast.2019.04.014) | - |
| [185] | 2020 | In Search of Lost Domain Generalization | - | ICLR [arXiv](https://arxiv.org/abs/2007.01434) | - |
| [186] | 2020 | With Little Power Comes Great Responsibility | - | [EMNLP](https://doi.org/10.18653/v1/2020.emnlp-main.745) [arXiv](https://arxiv.org/abs/2010.06595) | - |
| [187] | 2020 | WILDS: A Benchmark of in-the-Wild Distribution Shifts | WILDS | ICML [arXiv](https://arxiv.org/abs/2012.07421) | - |
| [188] | 2021 | Accounting for Variance in Machine Learning Benchmarks | - | MLSys [arXiv](https://arxiv.org/abs/2103.03098) | - |
| [189] | 2022 | Are Transformers Effective for Time Series Forecasting? | - | AAAI [arXiv](https://arxiv.org/abs/2205.13504) | [code](https://github.com/cure-lab/LTSF-Linear)![GitHub stars](http://img.shields.io/github/stars/cure-lab/LTSF-Linear.svg?logo=github&label=Stars) |
| [190] | 2022 | Leakage and the Reproducibility Crisis in ML-based Science | - | [arXiv](https://arxiv.org/abs/2207.07048) | - |
| [191] | 2022 | Why do tree-based models still outperform deep learning on tabular data? | - | [arXiv](https://arxiv.org/abs/2207.08815) | - |
| [192] | 2023 | A decoder-only foundation model for time-series forecasting | - | ICML [arXiv](https://arxiv.org/abs/2310.10688) | - |
| [193] | 2023 | Mathematical discoveries from program search with large language models | - | [Nature](https://doi.org/10.1038/s41586-023-06924-6) | - |
| [194] | 2024 | Chronos: Learning the Language of Time Series | Chronos | TMLR [arXiv](https://arxiv.org/abs/2403.07815) | [code](https://github.com/amazon-science/chronos-forecasting)![GitHub stars](http://img.shields.io/github/stars/amazon-science/chronos-forecasting.svg?logo=github&label=Stars) |
| [195] | 2024 | Adding Error Bars to Evals: A Statistical Approach to Language Model Evaluations | - | [arXiv](https://arxiv.org/abs/2411.00640) | - |
| [196] | 2025 | Accurate predictions on small data with a tabular foundation model | - | [Nature](https://doi.org/10.1038/s41586-024-08328-6) | - |

<a id="f"></a>

### Engenharia de Dados para sistemas de IA

| ID | Year | Title | Model | Published | Code |
| -- | ---- | ----- | ----- | --------- | ---- |
| [197] | 2001 | Why and Where: A Characterization of Data Provenance | Why and Where | [ICDT (LNCS)](https://doi.org/10.1007/3-540-44503-X_20) | - |
| [198] | 2008 | MapReduce: simplified data processing on large clusters | MapReduce | [CACM](https://doi.org/10.1145/1327452.1327492) | - |
| [199] | 2011 | Kafka : a Distributed Messaging System for Log Processing | Kafka | [NetDB?](https://www.semanticscholar.org/paper/ea97f112c165e4da1062c30812a41afca4dab628) | - |
| [200] | 2015 | The dataflow model: a practical approach to balancing correctness, latency, and cost in massive-scale, unbounded, out-of-order data processing | The dataflow model | [PVLDB](https://doi.org/10.14778/2824032.2824076) | - |
| [201] | 2016 | Apache Spark: a unified engine for big data processing | Apache Spark | [CACM](https://doi.org/10.1145/2934664) | - |
| [202] | 2018 | Datasheets for Datasets | - | [CACM](https://doi.org/10.1145/3458723) [arXiv](https://arxiv.org/abs/1803.09010) | - |
| [203] | 2018 | Automating large-scale data quality verification | - | [PVLDB](https://doi.org/10.14778/3229863.3229867) | - |
| [204] | 2020 | Delta lake: high-performance ACID table storage over cloud object stores | Delta lake | [PVLDB](https://doi.org/10.14778/3415478.3415560) | - |
| [205] | 2020 | DBLog: A Watermark Based Change-Data-Capture Framework | DBLog | [arXiv](https://arxiv.org/abs/2010.12597) | - |
| [206] | 2021 | Lakehouse: A New Generation of Open Platforms that Unify Data Warehousing and Advanced Analytics | Lakehouse | [CIDR](https://www.cidrdb.org/cidr2021/papers/cidr2021_paper17.pdf) | - |
| [207] | 2021 | “Everyone wants to do the model work, not the data work”: Data Cascades in High-Stakes AI | - | [CHI](https://doi.org/10.1145/3411764.3445518) | - |
| [208] | 2021 | Milvus: A Purpose-Built Vector Data Management System | Milvus | [SIGMOD](https://doi.org/10.1145/3448016.3457550) | - |
| [209] | 2021 | Deduplicating Training Data Makes Language Models Better | - | [ACL](https://doi.org/10.18653/v1/2022.acl-long.577) [arXiv](https://arxiv.org/abs/2107.06499) | [code](https://github.com/google-research/deduplicate-text-datasets)![GitHub stars](http://img.shields.io/github/stars/google-research/deduplicate-text-datasets.svg?logo=github&label=Stars) |
| [210] | 2023 | Data-centric AI: Perspectives and Challenges | Data-centric AI | SDM [arXiv](https://arxiv.org/abs/2301.04819) | [code](https://github.com/daochenzha/data-centric-AI)![GitHub stars](http://img.shields.io/github/stars/daochenzha/data-centric-AI.svg?logo=github&label=Stars) |
| [211] | 2023 | Scaling Data-Constrained Language Models | - | NeurIPS [arXiv](https://arxiv.org/abs/2305.16264) | [code](https://github.com/huggingface/datablations)![GitHub stars](http://img.shields.io/github/stars/huggingface/datablations.svg?logo=github&label=Stars) |
| [212] | 2024 | Dolma: an Open Corpus of Three Trillion Tokens for Language Model Pretraining Research | Dolma | ACL [arXiv](https://arxiv.org/abs/2402.00159) | [code](https://hf.co/datasets/allenai/dolma) [code](https://github.com/allenai/dolma)![GitHub stars](http://img.shields.io/github/stars/allenai/dolma.svg?logo=github&label=Stars) |
| [213] | 2024 | The FineWeb Datasets: Decanting the Web for the Finest Text Data at Scale | The FineWeb Datasets | NeurIPS [arXiv](https://arxiv.org/abs/2406.17557) | - |

<a id="g"></a>

### MLOps, LLMOps e operação em produção

| ID | Year | Title | Model | Published | Code |
| -- | ---- | ----- | ----- | --------- | ---- |
| [214] | 2015 | Hidden Technical Debt in Machine Learning Systems | - | [NeurIPS](https://dblp.org/rec/conf/nips/SculleyHGDPECYC15) | - |
| [215] | 2016 | Clipper: A Low-Latency Online Prediction Serving System | Clipper | NSDI [arXiv](https://arxiv.org/abs/1612.03079) | - |
| [216] | 2017 | TFX: A TensorFlow-Based Production-Scale Machine Learning Platform | TFX | [KDD](https://doi.org/10.1145/3097983.3098021) | - |
| [217] | 2017 | The ML test score: A rubric for ML production readiness and technical debt reduction | - | [IEEE BigData](https://doi.org/10.1109/BigData.2017.8258038) | - |
| [218] | 2019 | Model Cards for Model Reporting | - | [FAT*](https://doi.org/10.1145/3287560.3287596) [arXiv](https://arxiv.org/abs/1810.03993) | - |
| [219] | 2019 | Failing Loudly: An Empirical Study of Methods for Detecting Dataset Shift | Failing Loudly | NeurIPS [arXiv](https://arxiv.org/abs/1810.11953) | - |
| [220] | 2019 | Data Validation for Machine Learning | - | [MLSys](https://dblp.org/rec/conf/mlsys/BreckP0WZ19) | - |
| [221] | 2019 | Energy and Policy Considerations for Deep Learning in NLP | - | [ACL](https://doi.org/10.18653/v1/P19-1355) [arXiv](https://arxiv.org/abs/1906.02243) | - |
| [222] | 2020 | Towards CRISP-ML(Q): A Machine Learning Process Model with Quality Assurance Methodology | Towards CRISP-ML(Q) | MAKE [arXiv](https://arxiv.org/abs/2003.05155) | - |
| [223] | 2020 | Monitoring and explainability of models in production | - | Workshop [arXiv](https://arxiv.org/abs/2007.06299) | - |
| [224] | 2022 | Orca: A Distributed Serving System for Transformer-Based Generative Models | Orca | [OSDI](https://dblp.org/rec/conf/osdi/YuJKKC22) | - |
| [225] | 2022 | FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness | FlashAttention | [NeurIPS](https://doi.org/10.52202/068431-1189) [arXiv](https://arxiv.org/abs/2205.14135) | - |
| [226] | 2022 | LLM.int8(): 8-bit Matrix Multiplication for Transformers at Scale | LLM.int8() | NeurIPS [arXiv](https://arxiv.org/abs/2208.07339) | - |
| [227] | 2022 | Operationalizing Machine Learning: An Interview Study | - | [arXiv](https://arxiv.org/abs/2209.09125) | - |
| [228] | 2022 | SmoothQuant: Accurate and Efficient Post-Training Quantization for Large Language Models | SmoothQuant | ICML [arXiv](https://arxiv.org/abs/2211.10438) | [code](https://github.com/mit-han-lab/smoothquant)![GitHub stars](http://img.shields.io/github/stars/mit-han-lab/smoothquant.svg?logo=github&label=Stars) |
| [229] | 2022 | Fast Inference from Transformers via Speculative Decoding | - | ICML [arXiv](https://arxiv.org/abs/2211.17192) | - |
| [230] | 2023 | GPTQ: Accurate Post-Training Quantization for Generative Pre-trained Transformers | GPTQ | ICLR [arXiv](https://arxiv.org/abs/2210.17323) | [code](https://github.com/IST-DASLab/gptq)![GitHub stars](http://img.shields.io/github/stars/IST-DASLab/gptq.svg?logo=github&label=Stars) |
| [231] | 2023 | Efficient Memory Management for Large Language Model Serving with PagedAttention | - | [SOSP](https://doi.org/10.1145/3600006.3613165) [arXiv](https://arxiv.org/abs/2309.06180) | [code](https://github.com/vllm-project/vllm)![GitHub stars](http://img.shields.io/github/stars/vllm-project/vllm.svg?logo=github&label=Stars) |
| [232] | 2023 | Splitwise: Efficient generative LLM inference using phase splitting | Splitwise | [ISCA](https://doi.org/10.1109/ISCA59077.2024.00019) [arXiv](https://arxiv.org/abs/2311.18677) | - |
| [233] | 2024 | AWQ: Activation-aware Weight Quantization for LLM Compression and Acceleration | AWQ | [MLSys](https://doi.org/10.1145/3714983.3714987) [arXiv](https://arxiv.org/abs/2306.00978) | [code](https://github.com/mit-han-lab/llm-awq)![GitHub stars](http://img.shields.io/github/stars/mit-han-lab/llm-awq.svg?logo=github&label=Stars) |
| [234] | 2024 | DistServe: Disaggregating Prefill and Decoding for Goodput-optimized Large Language Model Serving | DistServe | OSDI [arXiv](https://arxiv.org/abs/2401.09670) | - |
| [235] | 2024 | Taming Throughput-Latency Tradeoff in LLM Inference with Sarathi-Serve | - | OSDI [arXiv](https://arxiv.org/abs/2403.02310) | [code](https://github.com/microsoft/sarathi-serve)![GitHub stars](http://img.shields.io/github/stars/microsoft/sarathi-serve.svg?logo=github&label=Stars) |
| [236] | 2024 | Who Validates the Validators? Aligning LLM-Assisted Evaluation of LLM Outputs with Human Preferences | - | [UIST](https://doi.org/10.1145/3654777.3676450) [arXiv](https://arxiv.org/abs/2404.12272) | - |

## Citation

Se este repositório for útil para sua pesquisa, cite os trabalhos originais listados acima. A lista é atualizada pelos scripts em [ferramentas](ferramentas/) (ver [Analise.md](Analise.md#como-atualizar)).

Sugestões e correções são bem-vindas via issue ou pull request :)
