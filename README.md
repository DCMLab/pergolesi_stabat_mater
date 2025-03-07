![Version](https://img.shields.io/github/v/release/DCMLab/pergolesi_stabat_mater?display_name=tag)
[![DOI](https://zenodo.org/badge/{{ zenodo_badge_id }}.svg)](https://doi.org/{{ concept_doi }})
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/pergolesi_stabat_mater)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/pergolesi_stabat_mater](https://github.com/DCMLab/pergolesi_stabat_mater) and the corresponding
* documentation page [https://dcmlab.github.io/pergolesi_stabat_mater](https://dcmlab.github.io/pergolesi_stabat_mater)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/pergolesi_stabat_mater/introduction).

# Giovanni Battista Pergolesi – Stabat Mater (1736)

The Stabat Mater is one of the few works that can be definitively attributed to Pergolesi. Written shortly before the
composer's untimely death, this work has since become ubiquitous for its innovative implementation of an accessible,
opera-like style within a sacred context. Our annotations highlight the poignant dissonances and tensions that enrich
the ostensibly simple vocabulary of this work.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/pergolesi_stabat_mater/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [pergolesi_stabat_mater.zip](https://github.com/DCMLab/pergolesi_stabat_mater/releases/latest/download/pergolesi_stabat_mater.zip)
  * [pergolesi_stabat_mater.datapackage.json](https://github.com/DCMLab/pergolesi_stabat_mater/releases/latest/download/pergolesi_stabat_mater.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/pergolesi_stabat_mater.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first section has the following files:

* `MS3/01. Stabat Mater dolorosa.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/01. Stabat Mater dolorosa.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/01. Stabat Mater dolorosa.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/01. Stabat Mater dolorosa.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/01. Stabat Mater dolorosa.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/01. Stabat Mater dolorosa.harmonies.tsv")
notes = ms3.load_tsv("notes/01. Stabat Mater dolorosa.notes.tsv"")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/pergolesi_stabat_mater/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/pergolesi_stabat_mater/issues) and/or feel free to fork and submit pull requests.

## Cite as

_Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Giovanni Battista Pergolesi – Stabat Mater (1736) [Data set]. Zenodo. https://doi.org/{{ concept_doi }}_

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## Overview
|           file_name            |measures|labels|standard|annotators |
|--------------------------------|-------:|-----:|--------|-----------|
|01. Stabat Mater dolorosa       |      47|   174|2.2.0   |Uli Kneisel|
|02. Cujus animam gementem       |     108|   228|2.2.0   |Uli Kneisel|
|03. O quam tristis et afflicta  |      26|    84|2.2.0   |Uli Kneisel|
|04. Quae moerebat et dolebat    |     103|   214|2.2.0   |Uli Kneisel|
|05. Quis est homo qui non fleret|      49|   122|2.2.0   |Uli Kneisel|
|06. Vidit suum dulcem natum     |      43|   153|2.2.0   |Uli Kneisel|
|07. Eja, Mater fons amois       |      94|   214|2.2.0   |Uli Kneisel|
|08. Fac ut ardeat cor meum      |      72|     0|        |           |
|09. Sancta mater, istud agas    |      84|     0|        |           |
|10. Fac ut portem Christi mortem|      26|     0|        |           |
|11. Inflammatus et accensus     |      52|     0|        |           |
|12. Quando corpus morietur      |      94|     0|        |           |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
