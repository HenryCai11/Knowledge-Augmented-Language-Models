# Knowledge-Augmented-Language-Models
A survey and paper-list of Knowledge-Augmented Language Models

## Paper-List
### Explicitly inject knowledge representation into language model pre-training
- **K-BERT: Enabling Language Representation with Knowledge Graph** [[pdf]](https://arxiv.org/pdf/1909.07606.pdf)
  - Injecting triplets from KGs by adding them to relevant entities, which leads to inputs of tree-structure;
  - To obtain the tree-structure in Transformer, they propose to modify the position embedding and the attention mask matrix, keeping the injected knowledge invisible to irrelevant tokens;
  - Pretrain task: MLM (Masked Language Modeling).
- **ERNIE: Enhanced Language Representation with Informative Entities** [[pdf]](https://arxiv.org/pdf/1905.07129v3/n)
- **KG-BART: Knowledge Graph-Augmented BART for Generative Commonsense Reasoning** [[pdf]](https://arxiv.org/pdf/2009.12677.pdf)
- **DKPLM: Decomposable Knowledge-Enhanced Pre-trained Language Model for Natural Language Understanding**, in AAAI 2022. [[pdf]](https://arxiv.org/pdf/2112.01047.pdf)
- **Language Generation with Multi-Hop Reasoning on Commonsense Knowledge Graph**, in EMNLP 2020. [[pdf]](https://arxiv.org/pdf/2009.11692.pdf)
- **KEPLER: A Unified Model for Knowledge Embedding and Pre-trained Language Representation**, in TACL 2020. [[pdf]](https://arxiv.org/pdf/1911.06136.pdf)

### Implicitly model knowledge information into language model by performing knowledge-related tasks
- **JAKET: Joint Pre-training of Knowledge Graph and Language Understanding** [[pdf]](https://arxiv.org/pdf/2010.00796.pdf)
- **JointGT: Graph-Text Joint Representation Learning for Text Generation from Knowledge Graphs** [[pdf]](https://arxiv.org/pdf/2106.10502.pdf)


### Knowledge Injection for Specific Tasks
**Loosely-coupled**
- KagNet: Knowledge-Aware Graph Networks for Commonsense Reasoning
- Scalable Multi-Hop Relational Reasoning for Knowledge-Aware Question Answering
- QA-GNN: Reasoning with Language Models and Knowledge Graphs for Question Answering


**Tightly-coupled**
- GREASELM: Graph Reasoning Enhanced Language Models for Question Answering
- 
