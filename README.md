# HaSpeeDe3-reloaded 🔁

> Una rivisitazione del task HaSpeeDe3 (EVALITA 2023) con modelli encoder-only e decoder-only moderni applicati al rilevamento dell'hate speech in tweet politici italiani.

---

## Panoramica

Questo repository contiene il codice e gli esperimenti sviluppati nell'ambito di un progetto d'esame universitario. L'obiettivo è riprendere il task **HaSpeeDe3** — proposto originariamente nell'ambito di EVALITA 2023 — e rivalutarlo con modelli linguistici più recenti rispetto a quelli disponibili al momento della competizione.

Il task consiste nella **classificazione binaria** di tweet italiani tratti dal dataset **PolicyCorpusXL**, con l'obiettivo di determinare se un tweet contenga hate speech (`label=1`) o meno (`label=0`). Le performance sono valutate tramite la **media delle F1-score** sulle due classi:

$$F1_{avg} = \frac{F1_{HS} + F1_{\neg HS}}{2}$$

Vengono sviluppati e confrontati due modelli:
- **Encoder-only** — fine-tuning di un modello italiano pre-addestrato di tipo BERT-like
- **Decoder-only** — fine-tuning di un modello di tipo GPT-like per la classificazione

Entrambi i notebook includono analisi esplorativa del dataset, pre-processing, selezione delle feature (testuali e contestuali), addestramento e valutazione.

---

## Dataset

Il dataset utilizzato è il sottoinsieme **PolicyCorpusXL** di HaSpeeDe3, composto da 7.000 tweet italiani su temi politici, raccolti tramite snowball sampling a partire dagli hashtag `#dpcm`, `#legge`, `#leggedibilancio`.

| Split    | Hate Speech | Non-Hate | Totale |
|----------|-------------|----------|--------|
| Training | 2.144       | 3.456    | 5.600  |
| Test     | 1.187       | 3.213    | 4.400  |

Ogni tweet è accompagnato da metadati **testuali** (`anonymized_text`) e **contestuali** (`retweet_count`, `followers_count`, `is_reply`, ecc.).

> ⚠️ I file del dataset (`training_textual.csv`, `test_textual_gold.csv`, `training_contextual.csv`, `test_contextual.csv`) **non sono inclusi** in questo repository. È possibile ottenerli dal repository ufficiale dei dataset di EVALITA 2023.

---

## Riferimenti

- **Paper del task:** Lai et al. (2023). *HaSpeeDe3 at EVALITA 2023: Overview of the Political and Religious Hate Speech Detection task.* CEUR-WS. [📄 PDF](https://ceur-ws.org/Vol-3473/paper22.pdf)
- **Repository ufficiale del task:** [mirkolai/EVALITA2023-HaSpeeDe3](https://github.com/mirkolai/EVALITA2023-HaSpeeDe3)
- **Dataset ufficiali:** [evalita2023/datasets](https://github.com/evalita2023/datasets)
- **EVALITA 2023:** [evalita.it/campaigns/evalita-2023](https://www.evalita.it/campaigns/evalita-2023/)

---

## Autore

**Teresa Staropoli** - Progetto d'esame universitario — corso di **NLP, Foundation Models e IA Generativa**

Basato sul task HaSpeeDe3 © EVALITA 2023.

---

## Mascotte della repo

![Paperino Gramsci](https://www.storiedipaperi.com/wp-content/uploads/2023/10/PioveBrutta.jpg)

