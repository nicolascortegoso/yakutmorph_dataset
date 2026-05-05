# A Morphologically Annotated Dataset of Yakut Constructions

This dataset contains sentences, clauses, and multi-word expressions compiled from established descriptive studies of Yakut and standardized under a unified machine-readable annotation schema.

Morphological annotation is performed at the token level and includes lexical root identification and ordered affix segmentation.

The morphological annotations were generated using the pipeline described in:

N. C. Vissio and M. V. Khokhlova, “A Three-Stage Morphological Pipeline for Word Form Analysis in Yakut,” 2024 IEEE 3rd International Conference on Problems of Informatics, Electronics and Radio Engineering (PIERE), Novosibirsk, Russian Federation, 2024, pp. 1860–1864. https://doi.org/10.1109/PIERE62470.2024.10805022

[Annotation labels reference](docs/labels_reference.md)

------------------------------------------------------------------------

## Dataset Organization

The dataset is organized into folders corresponding to individual source works. Each folder contains Yakut constructions extracted from a single descriptive study.

The table below lists the folder for each source work and the percentage of the annotation work that has been completed for that folder.

| Folder | Content | Total samples | Processed samples | Annotation progress | Source |
|:---|:---|:---|:---|:---|:---|
| 001 | General grammar | 4813 | 4315 | 89.65% | Грамматика современного якутского литературного языка : [в 2 томах] / Акад. наук СССР, Сиб. отд- ние, Якут. фил., Ин-т яз. лит.и истории; [редкол.: Е. И. Убрятова (отв. ред.), Е. И. Коркина, Л. Н. Харитонов, Н. Е. Петров]. – Москва : Наука, 1982-1995. Т. 1: Фонетика и морфология / [Л. Н. Харитонов, Н. Д. Дьячковский, С. А. Иванов и др.]. – Москва: Наука, 1982. – 495 с. |
| 003 | Participles | 1832 | 1259 | 68.72% | Коркина Е.И. Деепричастия в якутском языке / Е. И. Коркина; отв. ред. к. филол. н. Н. Е. Петров; Акад. наук СССР, Сиб. отд-ние, Якут. фил., Ин-т яз., лит. и истории. – Новосибирск : Наука, Сибирское отделение, 1985. – 203 с. |
| 004 | Verb voice | 497 | 460 | 92.56% | Харитонов Л.Н. Залоговые формы глагола в якутском языке / Л. Н. Харитонов; Акад. наук СССР, Якут. фил. Сиб. отд-ния, Ин-т яз., лит. и истории. – Москва; Ленинград: Изд-во АН СССР, 1963. – 123 с. |
| 005 | Immutable words | 1038 | 953 | 91.81% | Харитонов Л.Н. Неизменяемые слова в якутском языке : пособие для учителей / Л. Н. Харитонов ; Нар. комиссариат просвещения ЯАССР. – Якутск : Государственное издательство ЯАССР, 1943. – 82 с. |
| 008 | General morphology | 753 | 730 | 96.95% | Харитонов, Лука Никифорович. Современный якутский язык = Саха билигиҥҥи тыла / Науч.-исслед. ин-т яз., лит. и истории ЯАССР ; под ред. проф. Н. К. Дмитриева. - Якутск : Госиздат ЯАССР, 1947. |
| 009 | General morphology | 298 | 275 | 92.28% | Данилова, Надежда Ивановна. Курс якутской грамматики: система морфологических категорий и синтаксических конструкций : учеб. пособие для студентов филол. фак. ЯГУ / Н. И. Данилова, Н. И. Попова, Н. Н. Ефремов ; Акад. наук Респ. Саха (Якутия), Ин-т гуманитар. исслед . - Якутск : ИГИ АН РС(Я), 2004. - 195, с. |
| 012 | Verb voice | 18 | 16 | 88.89% | Данилова Н.И. Якутские залоговые конструкции: к проблеме многозначности // Вестник НГУ. Серия: Лингвистика и межкультурная коммуникация. 2018. №4. |
| 013 | Verb voice | 12 | 11 | 91.67% | Винокурова Л.В., Ефимова А.Д., Иванова В.И. Категории залога якутского и французского языков // Современное Педагогическое Образование Учредители: Общество с Ограниченной Ответственностью Издательство Кнорус. – №. 12. – С. 199-203. |
| 015 | Postpositions | 16 | 16 | 100.00% | Большой толковый словарь якутского языка = Саха тылын быһаарыылаах улахан тылдьыта Т. 13. (Буква Х) = (Х буукуба) / Академия наук Республики Саха (Якутия), Институт гуманитарных исследований ; под общей редакцией П. А. Слепцова. - Новосибирск : Наука, 2004. |
| 019 | Function words and postpositions | 57 | 57 | 100.00% | Петров, Николай Егорович. Служебные имена и послелоги в якутском языке : автореферат диссертации на соискание ученой степени кандидата филологических наук / Н. Е. Петров ; Акад. наук СССР, Ленингр. отд-ние Ин-та языкознания. - Ленинград : [б. и.], 1963. - 16, с. |
| 021 | Verbal moods | 71 | 69 | 97.18% | Винокурова Н.И., Винокуров И.П. Наклонения в якутском и английском языках: сравнительный анализ. Северо-Восточный гуманитарный вестник. – 2012. – N 2 (5). – С. 98-107. |
|  | TOTAL | 9405 | 8161 | 86.77% |  |


Within each folder, three subfolders represent successive stages of a reproducible morphological processing pipeline:

- `source`: compiled, unprocessed Yakut constructions
- `pending`: automatically annotated constructions (raw analyzer output)
- `processed`: manually disambiguated constructions (gold-standard annotations)

This structure enables systematic comparison between automatic analyses and manually validated interpretations.

### Stage 1: Compiled Unprocessed Yakut Constructions (`source` folder)

The `source` folder contains JSON files with structured metadata and textual data. Each sample includes:

- `source`: Bibliographic reference.
- `page`: Page number in the source.
- `section`: Section identifier.
- `chapter`: Broad morphological domain.
- `topic`: Specific morphological phenomenon.
- `notes`: Author-provided commentary relevant to the example.
- `sah`: Original Yakut sentence.
- `ru`: Russian gloss or translation.

Each file typically groups examples illustrating a specific topic within a chapter. At this stage, no automatic morphological analysis has been applied.

### Stage 2: Automatically Annotated Yakut Constructions (`pending` folder)

The `pending` contains JSON files generated by processing the `source` data through the morphological analyzer.

This stage preserves the raw output of the morphological pipeline that has not been manually disambiguated. It functions as an evaluation layer that exposes:

- Morphological ambiguity (via multiple candidate parses)
- Overgeneration patterns
- Coverage gaps (unanalyzed tokens)

A `parses` field is added to each sample, storing the analyzer output. Each token-level analysis includes:

- `pos`: Position of the token in the sequence
- `text`: Surface form
- `type`: Token category (e.g., word, punctuation)
- `fst`: Morphological transducer responsible for the analysis
- `root`: Lexical root
- `affixes`: Ordered list of affixes

As soon as a construction is disambiguated, it is removed from the `pending` folder.


### Stage 3: Manually Disambiguated Yakut Constructions (`processed` folder)

The `processed` folder contains manually disambiguated JSON files in which each token is assigned exactly one validated morphological analysis.

This stage resolves ambiguities and analysis failures identified in Stage 2. The resulting annotations constitute the gold-standard version of the dataset.

While the `pending` folder preserves full analyzer output for diagnostic and benchmarking purposes, the `processed` folder provides curated, linguistically verified annotations suitable for:

- Training and evaluating morphological disambiguation models
- Studying Yakut morphotactic patterns
- Quantitative corpus analysis
- Downstream NLP tasks

------------------------------------------------------------------------

## Conventions and Guidelines for Organizing Samples

### 1. Aggregation by Source

- Samples are grouped by source to preserve internal coherence within descriptive works.
- Multiple examples illustrating a single phenomenon are collected within the same folder.
- The `source` field is therefore constant within each folder.

### 2. File Organization

- Each file typically corresponds to a specific topic within a chapter.
- The `chapter`, `topic`, and `section` fields must remain consistent within a file.
- However, the `page` and `notes` fields may vary across individual samples.

This design ensures structured metadata alignment while maintaining compatibility with corpus-level processing pipelines.

------------------------------------------------------------------------

## Content Summarization

These sections provide structured summaries of the dataset’s internal composition, organized by grammatical chapters and topics. They function as metadata indices reflecting the thematic distribution of annotated constructions.

- [Annotated data by chapter (in Russian)](docs/annotated_chapters.md)
- [Annotated data by topic (in Russian)](docs/annotated_topics.md)

------------------------------------------------------------------------

## Distributions

These sections present corpus-level frequency statistics derived from the annotated data:

- [Word form distribution](docs/wordform_distribution.md)
- [Lexical root distribution](docs/root_distribution.md)
- [Affix distribution](docs/affix_distribution.md)

These statistics support quantitative morphological analysis and computational modeling. The same frequency data are also provided in machine-readable JSON format in the [reports](reports/) folder.

## In Memoriam

This project was developed in collaboration with **Victor Pavlovich Zakharov**
(1947–2024). His mentorship and insight were fundamental to the development of this work.

Although he is no longer with us, his influence remains present throughout
this project.