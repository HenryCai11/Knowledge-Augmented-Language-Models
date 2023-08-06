# Knowledge-Augmented-Language-Models
A survey and paper-list of Knowledge-Augmented Language Models

## Paper-List
### Explicitly inject knowledge representation into language model pre-training
- **K-BERT: Enabling Language Representation with Knowledge Graph** [[pdf]](https://arxiv.org/pdf/1909.07606.pdf)
  - Inject triplets from KGs by adding them to relevant entities, which leads to inputs of tree-structure;
  - To obtain the tree-structure in Transformer, they propose to modify the position embedding and the attention mask matrix, keeping the injected knowledge invisible to irrelevant tokens;
  - Challenges addressed: (1) heterogeneous embedding space and (2) knowledge noise;
  - Pretrain tasks: MLM (Masked Language Modeling) and NSP (Next Sentence Prediction).
- **Knowledge Enhanced Contextual Word Representations** [[pdf]](https://arxiv.org/pdf/1909.04164.pdf)
  - Introduce a Knowledge Attention and Recontextualization (KAR) component to integrate KB knowledge into PLMs (e.g., BERT);
  - The KAR layer can be inserted between two Transformer layers and it calculates attention scores over entity-span representations, which will be used to recontextualize output embeddings of a Transformer block;
  - Entity-span representations = contextualized mention-span representations + weighted entity embeddings (from a KB)
  - Pretrain tasks: MLM, NSP, and EL (Entity Linking)
- **ERNIE: Enhanced Language Representation with Informative Entities** [[pdf]](https://arxiv.org/pdf/1905.07129v3/n)
  - M Knowledgeable Encoders (K-Encoder) are appended after N Transformer Encoders;
  - In a K-Encoder, retrieved entity embeddings are first contextualized, then aggregated with their aligned token embeddings, and then all the embeddings (tokens & entities) are updated;
  - Pretrain tasks: MLM, NSP, and dEA (denoising Entity Autoencoder)
  - dEA: (1) In [5% of the time](https://github.com/thunlp/ERNIE/blob/eee03e37c0c81e3d4b3bbe6dd4774da58f571453/code/run_pretrain.py#L225C35-L225C35), for a given token-entity alignment, replace the entity with another random entity, (2) in 15% of the time, mask token-entity alignments, and (3) in the rest of the time, keep token-entity alignments unchanged.
- **KG-BART: Knowledge Graph-Augmented BART for Generative Commonsense Reasoning** [[pdf]](https://arxiv.org/pdf/2009.12677.pdf)
  - M KG-augmented Encoders are appended to N BART Encoders; M KG-augmented Decoders are appended to N BART Decoders;
  - Inject knowledge from KGs by using Multi-head Graph Attention over the input subgraphs for both KG-augmented encoders and decoders;
  - Use subgraphs of different granularity in KG-augmented decoders (w/ one-hop neighborring nodes) compared with encoders;
  - Pretrain task: generate the original concept token from the masked concept nodes
- **DKPLM: Decomposable Knowledge-Enhanced Pre-trained Language Model for Natural Language Understanding**, in AAAI 2022. [[pdf]](https://arxiv.org/pdf/2112.01047.pdf)
  - Pretrain task: MLM and De (relational knowledge decoding);
  - De: (1) Knowledge-aware long-tail entity detection (2) calculate (long-tail) head/tail entity embeddings (3) calculate the loss against a sampled entity list with sampled softmax function.
- **Language Generation with Multi-Hop Reasoning on Commonsense Knowledge Graph**, in EMNLP 2020. [[pdf]](https://arxiv.org/pdf/2009.11692.pdf)
- **KEPLER: A Unified Model for Knowledge Embedding and Pre-trained Language Representation**, in TACL 2020. [[pdf]](https://arxiv.org/pdf/1911.06136.pdf)
- **Relation-Guided Pre-Training for Open-Domain Question Answering** [[pdf]](https://arxiv.org/pdf/2109.10346.pdf)

### Implicitly model knowledge information into language model by performing knowledge-related tasks
- **JAKET: Joint Pre-training of Knowledge Graph and Language Understanding** [[pdf]](https://arxiv.org/pdf/2010.00796.pdf)
- **JointGT: Graph-Text Joint Representation Learning for Text Generation from Knowledge Graphs** [[pdf]](https://arxiv.org/pdf/2106.10502.pdf)


### Knowledge Injection for Specific Tasks
**Loosely-coupled**
- **KagNet: Knowledge-Aware Graph Networks for Commonsense Reasoning**
- **Scalable Multi-Hop Relational Reasoning for Knowledge-Aware Question Answering**
- **QA-GNN: Reasoning with Language Models and Knowledge Graphs for Question Answering**


**Tightly-coupled**
- **GREASELM: Graph Reasoning Enhanced Language Models for Question Answering**
- 
