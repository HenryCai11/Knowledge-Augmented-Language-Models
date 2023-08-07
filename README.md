# Knowledge-Augmented-Language-Models
A simple survey and paper-list of Knowledge-Augmented Language Models

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
  - Pretrain tasks: generate the original concept token from the masked concept nodes
- **K-ADAPTER: Infusing Knowledge into Pre-Trained Models with Adapters** [[pdf]](https://arxiv.org/pdf/2002.01808.pdf)
  - Parameters of the model are fixed, and two adapters are inserted into the LM, which will be separately pre-trained on the tasks;
  - Pretrain tasks: predication prediction (classify relation labels of given entity pairs based on context), and dependency relation prediction (predict the head index of each token in the given sentence).
- **DKPLM: Decomposable Knowledge-Enhanced Pre-trained Language Model for Natural Language Understanding**, in AAAI 2022. [[pdf]](https://arxiv.org/pdf/2112.01047.pdf)
  - Pretrain tasks: MLM and De (relational knowledge decoding);
  - De: (1) Knowledge-aware long-tail entity detection (2) calculate (long-tail) head/tail entity embeddings (3) calculate the loss against a sampled entity list with Sampled Softmax Function.
- **Language Generation with Multi-Hop Reasoning on Commonsense Knowledge Graph**, in EMNLP 2020. [[pdf]](https://arxiv.org/pdf/2009.11692.pdf)
  - Reason on a KG, model the distribution of nodes in the KG, and learn to directly copy concepts (node) from the KG during generation;
  - The distribution of nodes is obtained by calculating scores of each node (node score). The score of node consists of two parts: (1) node scores from previous hops, and (2) triple relevance that reflects the relevancy of the evidence given by the triplet (u, r, v) under the current context (LM output embeddings);
  - Pretrain tasks: (1) language modeling, (2) a gate which controls copying concepts from the KG, and (3) [weak supervision of matching triplets](https://github.com/cdjhz/multigen/blob/728ef720ac44986beadee8d845debe5d37a3d966/scripts/modeling_gpt2.py#L946) along "gold reasoning paths" gathered by breadth-first search.
- **KEPLER: A Unified Model for Knowledge Embedding and Pre-trained Language Representation**, in TACL 2020. [[pdf]](https://arxiv.org/pdf/1911.06136.pdf)
  - Pretrain tasks: MLM and KE (Knowledge Embedding);
  - KE: (1) maintain a set of relation embeddings, (2) use a shared encoder to encode texts of h, r, and t (w/ or w/o descriptions) to get the corresponding embeddings, and then (3) calculate the KE loss with negative sampling.
- **Relation-Guided Pre-Training for Open-Domain Question Answering** [[pdf]](https://arxiv.org/pdf/2109.10346.pdf)
  - Construct a Grounded Relational Wiki-Graph, where each relation triplet 〈s, r, t〉 is linked to a set of description passages {desc.(s, t)} in the Wiki-page of entity s;
  - Generate relational QA pair for relation-guided QA pretraining (based on the DPR framework);
  - Pretrain tasks (same as [DPR](https://github.com/facebookresearch/DPR/blob/a31212dc0a54dfa85d8bfa01e1669f149ac832b7/dpr/models/reader.py#L111)): (1) Retriever (dense retrieval); (2) Reader (rerank & span extraction)
- **Facts as Experts: Adaptable and Interpretable Neural Memory over Symbolic Knowledge** [[pdf]](https://arxiv.org/pdf/2007.00849.pdf)
  - Insert an Entity Memory Layer between two sets of Transformer blocks, which retrieves entity embeddings that are related to mentions in the input sentence;
  - Weighted sum of the entity embeddings will be added to the previous Transformer output embeddings;
  - Entity embeddings will also be updated using the mentions (pseudo entity embeddings);
  - Pretrain tasks: MLM, mention boundary detection, entity linking.
- **Entities as Experts: Sparse Memory Access with Entity Supervision** [[pdf]](https://arxiv.org/pdf/2004.07202v1.pdf)


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
