# A Semantic-Annotated Corpus for Asturian Based on PropBank

**Lilia Marina Jiménez Redondo, Inés Martínez Fernández, Paula Posadas Postigo**


## Introduction

Asturian (also known as Asturleonese) is a Romance language spoken in the north of the Iberian Peninsula. As a low-resource language, it lacks many of the annotated corpora and NLP tools that are commonly available for majority languages, making it difficult to develop advanced NLP applications. This work takes a step towards reducing that gap by using a PropBank-style semantic annotation framework adapted to Asturian.

The PropBank framework (Bonial et al., 2014) is one of the most widely used approaches to represent verb semantics, focusing on predicate-argument structures in a consistent and systematic way. While similar resources exist for languages such as Spanish and Catalan through projects like AncoraVerb (Aparicio et al., 2008), no equivalent resource existed for Asturian. Our work provides a first foundational resource for semantic parsing and other NLP tasks in this language.


## Data

The corpus was compiled from the Asturian Wikipedia via the Leipzig Corpora Collection (2021), which contains 1,248,982 sentences and 24,553,187 tokens. To balance coverage with computational constraints, a subset of 10,000 sentences was used.

Automatic preprocessing was carried out using FreeLing (Padró and Stanilovsky, 2012), one of the few NLP tools with support for Asturian. Due to instability in FreeLing's Python API, a parallelized bash script was written to process sentences individually, preventing data loss from crashes. POS-tagging and lemmatization results were then manually reviewed and corrected. From the processed corpus, verb frequency counts were extracted to guide verb selection.


## Verb Lexicon

Five high-frequency verbs were selected for annotation: *poder*, *haber*, *ganar*, *caltener* and *cuntar*. The selection prioritized verbs that were both frequent and linguistically interesting, covering a range of semantic behaviors including modality, possession, achievement and narration.

Each verb entry was constructed following a structured pipeline: dictionary entries were consulted in the ALLA dictionary (Academia de la Llingua Asturiana, 2026) and cross-referenced with additional lexical resources (La Nueva España, 2026). Closely related senses were merged and simplified, and argument structures were defined following PropBank conventions. The resulting entries include a unique identifier, a semantic description, a set of core arguments and an illustrative example from the corpus. The full lexicon is available in [`verb-lexicon/`](./verb-lexicon/).


## Annotation Scheme

The annotation scheme is based on PropBank, with adaptations to account for the characteristics of Asturian and the constraints of a low-resource setting. Core arguments (ARG0–ARG4) are defined as a fixed set across all verbs to ensure consistency, while modifier arguments (ARGM) cover a rich range of contextual information including locative, temporal, manner, modal, negation and discourse roles. The full label reference is available in [`annotation-guidelines/annotation-scheme.md`](./annotation-guidelines/annotation-scheme.md).

To illustrate the scheme, the following example shows a sentence annotated with the verb *caltener*:

```
El ministru [ARG1] caltúvose [REL] tres años [ARGM-TMP] nel gobiernu [ARGM-LOC].
'The minister remained in government for three years.'
```

---

## Results

Annotation quality was evaluated on 50 sentences (10 per verb) by two annotators, one of whom was a native Asturian speaker. Inter-annotator agreement was measured using Cohen's Kappa, resulting in a score of **0.818**, indicating strong agreement and suggesting that the resource is well-defined and consistently applicable.


## Limitations and Future Work

The main limitation of this work is its scope: the lexicon covers only five verbs and the annotation is limited to sentences containing those verbs. FreeLing's incomplete support for Asturian also required significant manual intervention during preprocessing. Additionally, only one of the two annotators was a native speaker, which may have introduced some inconsistencies.

The methodology is designed to be extensible. Future work could expand the lexicon by following the same pipeline, use larger corpora from the Leipzig Corpora Collection, and improve preprocessing tools for Asturian. The resource also opens the door to downstream NLP tasks such as semantic role labeling and semantic parsing for the language.

---

## Repository Structure

```
asturian-propbank/
├── README.md
├── corpus/                        # Annotated sentences
├── verb-lexicon/                  # Full verb entries
└── annotation-guidelines/
    └── annotation-scheme.md       # Full label reference
```

---

## References

Academia de la Llingua Asturiana. (2026). *Diccionariu de la llingua asturiana*.

Aparicio, J., Taulé, M., and Martí, M. A. (2008). AnCora-Verb: Two large-scale verbal lexicons for Catalan and Spanish.

Bonial, C., Bonn, J., Conger, K., Hwang, J., and Palmer, M. (2014). PropBank: Semantics of new predicate types. In *Proceedings of LREC*.

La Nueva España. (2026). *Diccionario general de la lengua asturiana*.

Leipzig Corpora Collection. (2021). Asturian Wikipedia corpus. https://corpora.wortschatz-leipzig.de

Padró, L. and Stanilovsky, E. (2012). FreeLing 3.0: Towards wider multilinguality. In *Proceedings of LREC*, pages 2473–2479.
