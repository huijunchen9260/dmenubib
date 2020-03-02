# Dmenubib

A simple bibliography manager using dmenu

- Minimal (*only require **POSIX compliant shell** and coreutils*)
- Automatically **rename** and **update metadata** for your pdf files.

## Dependency

- `dmenu`, `exiftool`, `pdftotext`
- `grep`, `awk`, `sed`, `eval`, `tail`x, `curl`
- `printf`, `echo`, `xclip / xsel`

## Installation

Move all the files to `$PATH`.

## Usage

Need to set two environment variables:

- `$BIB` for `.bib` file
- `$BIB_PDF_PATH` for directory to store pdf files.

### `SER` to Search BibTeX on Internet:

Two ways to search: `Text` or `PDF`.

`Text`:

- Type doi and directly generate bibtex
- Type text related to paper to search on [Crossref](https://search.crossref.org/), and copy doi to generate bibtex.
    - If you cannot find doi in crossref, copy any text other than doi, and then `dmenubib` will search on [Google scholar](https://scholar.google.com/). Copy bibtex to store it in `$BIB`.

`PDF`:

- Choose pdf file in `$BIB_PDF_PATH`.
- If the metadata contain doi, then generate bibtex.
- If the metadata contain title or can extract some text, then search on [Crossref](https://search.crossref.org/), and copy doi to generate bibtex.
    - If you cannot find doi in crossref, copy any text other than doi, and then `dmenubib` will search on [Google scholar](https://scholar.google.com/). Copy bibtex to store it in `$BIB`.

### `REF` to Get BibTeX label for reference

Choose the criterion to search in `$BIB`. Copy the label of chosen bibtex to clipboard.

### `OPN` to open corresponding pdf file

Choose the criterion to search in `$BIB`. Open the corresponding pdf in `$BIB_PDF_PATH`.

### `PDF` to Manually Rename and encode metadata into pdf

Choose pdf files, and choose which bibtex entry to generate metadata.

PDF will be renamed as bibtex label, and attached with Title, Author, and doi metadata.

### `AUO` to Automatically rename and encode metadata into pdf

Automatically go through all pdf files in `$BIB_PDF_PATH`, check whether correctly named. `Dmenubib` will generate a list of unmatched pdf files, and allow manual rename and encode metadata using `PDF` function.

**Caveat: `AUO` update pdf based on pdf filename. So if you update your bibtex and want to update metadata, use `PDF` instead.**

