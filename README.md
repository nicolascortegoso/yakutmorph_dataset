# A Morphologically Annotated Dataset of Yakut Constructions

The dataset contains sentences, clauses, and multi-word expressions compiled from established descriptive studies and standardized under a unified annotation schema.

Morphological annotation is performed at the token level and includes root identification and ordered affix segmentation.

------------------------------------------------------------------------

## Dataset Organization

The dataset is organized into folders, each containing a collection of Yakut constructions compiled from a specific source.

Within each folder, three subfolders represent successive stages in the processing pipeline:

- `source`: compiled unprocessed Yakut constructions
- `pending`: automatically annotated Yakut constructions
- `processed`: manually disambiguated Yakut constructions

### Stage 1: Compiled Unprocessed Yakut Constructions (`source` folder)

The `source` folder contains files in JSON format (JavaScript Object Notation) with the following fields:

- `source`: Reference to the original work on Yakut morphology.
- `page`: Page number in the source.
- `section`: Section identifier in the source.
- `chapter`: General aspect of Yakut morphology under discussion.
- `topic`: Specific aspect of Yakut morphology under discussion.
- `notes`: Explanations and observations provided by the authors relevant to the analysis.
- `sah`: The original sentence in Yakut as it appears in the source.
- `ru`: The corresponding Russian gloss or translation provided in the source.

Each file typically corresponds to a single topic, part of a chapter, or a specific section of the source material.

### Stage 2: Automatically Annotated Yakut Constructions (`pending` folder)

The `pending` folder contains JSON files derived from the `source` folder after processing through the morphological analyzer.

At this stage, the raw output of the morphological pipeline is preserved without manual correction. This level functions as a diagnostic and evaluation layer, allowing systematic inspection of whether the analyzer produces the linguistically expected analysis among the set of possible interpretations.

Stage 2 reflects the recall and ambiguity profile of the morphological system: it exposes multiple candidate parses, unresolved ambiguities, and cases of analysis failure. As such, it enables assessment of coverage, overgeneration, and structural accuracy before manual disambiguation.

To preserve this information, `parses`, is added to each sample. This field contains the raw output produced by the morphological pipeline. The output may include:

- Multiple interpretations of the same token (morphological ambiguity).
- Tokens that the pipeline failed to analyze.

Each analyzed token contains the following fields:

- `pos`: Position of the token in the sequence.
- `text`: Surface form of the token as it appears in the sequence.
- `type`: Category of the token (e.g., word, punctuation).
- `fst`: The morphological transducer used for the analysis.
- `root`: Lexical root of the token.
- `affixes`: Ordered list of affixes attached to the lexical root.


### Stage 3: Manually Disambiguated Yakut Constructions (`processed` folder)

The `processed` folder contains JSON files that have been manually disambiguated, ensuring that each token has exactly one selected analysis.

This stage resolves the ambiguities and unresolved cases identified in Stage 2. The resulting annotations represent a validated morphological interpretation of each construction and constitute the final version of the dataset.

While the `pending` folder preserves the raw output of the morphological analyzer for evaluation purposes, the `processed` folder provides curated, linguistically verified annotations suitable for downstream analysis.

------------------------------------------------------------------------

## Content Summarization

- [Annotation progress](docs/annotation_progress.md)
- [Annotated data by chapter (in Russian)](docs/annotated_chapters.md)
- [Annotated data by topic (in Russian)](docs/annotated_topics.md)
- [Word form distribution](docs/wordform_distribution.md)
- [Lexical root distribution](docs/root_distribution.md)
- [Affix distribution](docs/affix_distribution.md)

------------------------------------------------------------------------

## Conventions and Guidelines for Organizing Samples

### 1. Aggregation by Source

- Samples are grouped primarily by source rather than distributed across multiple sources.
- The goal is to collect multiple examples related to a specific topic within a given work rather than isolated examples from different works.
- Consequently, the `source` field is identical for all samples within a folder.

### 2. File Organization

- Within each folder, samples are organized into files.
- Each file typically contains samples illustrating a particular topic within the current work on Yakut morphology.
- Therefore, the `chapter`, `topic`, and `section` fields must be consistent across all samples in a file.
- However, the `page` and `notes` fields are sample-specific and may vary within the same file.
