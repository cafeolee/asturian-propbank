# Annotation Scheme

This document describes the full set of labels used in the Asturian PropBank annotation framework.

## Core Arguments

| Label | Description |
|-------|-------------|
| REL   | Predicate / verb |
| ARG0  | Agent / causer / experiencer |
| ARG1  | Patient / theme |
| ARG2  | Instrument / beneficiary / attribute |
| ARG3  | Source / beneficiary / attribute |
| ARG4  | Destination / end point |
| ARGA  | Secondary agent |

## Modifier Arguments

| Label      | Description |
|------------|-------------|
| ARGM-COM   | Comitative |
| ARGM-LOC   | Locative |
| ARGM-DIR   | Directional |
| ARGM-GOL   | Goal |
| ARGM-MNR   | Manner |
| ARGM-TMP   | Temporal |
| ARGM-EXT   | Extent / degree |
| ARGM-REC   | Reciprocal / reflexive |
| ARGM-PRD   | Secondary predication |
| ARGM-PRP   | Purpose |
| ARGM-CAU   | Cause |
| ARGM-DIS   | Discourse |
| ARGM-ADV   | Adverbial |
| ARGM-ADJ   | Adjectival |
| ARGM-MOD   | Modal |
| ARGM-NEG   | Negation |
| ARGM-DSP   | Direct speech |
| ARGM-CXN   | Construction |

## Annotation Example

```
El ministru [ARG1] caltúvose [REL] tres años [ARGM-TMP] nel gobiernu [ARGM-LOC].
```

- **REL**: *caltúvose* — the predicate
- **ARG1**: *El ministru* — entity remaining
- **ARGM-TMP**: *tres años* — temporal modifier
- **ARGM-LOC**: *nel gobiernu* — locative modifier