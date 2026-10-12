# CV plotting with Codex

A classroom project for learning to describe a plotting task in the Codex desktop interface. Students give natural-language instructions; Codex writes and runs the plotting code using the Python environment available for the course.

## Download and open the project

1. On this repository's GitHub page, click **Code → Download ZIP**.
2. **Windows:** right-click the downloaded ZIP, choose **Extract All...**, and extract it to a local folder. **Mac:** double-click the ZIP in Finder.
3. Open the extracted repository folder as a **local project in Codex**. Choose the folder containing this README, `SOURCE_DATA.json`, `manifest.csv`, and the ten data folders.
4. Start a new chat. Send the prompts in [PROMPTS.txt](PROMPTS.txt) one at a time and inspect the result before continuing.

GitHub adds the repository name and branch to the extracted folder name. Students can download this public repository without a GitHub account or a Git command. Installation is covered in the workshop presentation.

## What is included

**1,000 unchanged source-data exports:** original filename indices **1–100** from each folder.

| Folder | Files | Numerical cycle-2 candidates |
|---|---:|---:|
| CE | 100 | 100 |
| DISP | 100 | 100 |
| E | 100 | 100 |
| EC | 100 | 100 |
| EC_cat_k | 100 | 58 |
| EC_cat_kd | 100 | 64 |
| EC_cat_ks | 100 | 78 |
| ECE | 100 | 100 |
| SR | 100 | 100 |
| T | 100 | 100 |

Original filenames and export bytes are preserved. Folder labels identify the source folders; they do not independently validate a mechanism or establish why traces differ.

- [SOURCE_DATA.json](SOURCE_DATA.json): per-file provenance, units, row counts, cycle evidence, and matching source-model evidence.
- [manifest.csv](manifest.csv): one row per export, with relative path, SHA256, units, and a suggested cycle from numerical screening.
- [PROMPTS.txt](PROMPTS.txt): guided plotting, a style revision, a small batch pilot, and independent practice.

Source COMSOL models, generator scripts, and parameter ledgers are referenced in the provenance audit but are not included. No simulations were rerun to prepare this dataset. Provenance paths are portable source-project identifiers; students do not need the instructor's original computer paths.

## Guided demo

Ask Codex to inspect the metadata first, then plot **`E/Table_4_E.txt`, cycle 2**, using all **667 original rows**. The documented axes are **electric potential (V)** and **total current (A)**. Potential uses the model reference; an experimental reference electrode identity is not supplied.

Save a PNG and PDF under `outputs/`, ask Codex to run the code and show the figure, then request one specific style change. Preserve the selected rows and their values when changing appearance. The full copy-and-paste instructions are in [PROMPTS.txt](PROMPTS.txt).

## Independent practice and batch plotting

For practice, inspect and plot **`SR/Table_4_SR.txt`, cycle 2**, with **1,600 original rows**. SR has hash-comment lines and a named tab-separated header; most other exports have percent-comment lines and whitespace-delimited numeric triples.

For a small batch pilot, inspect files in numerical filename-index order and choose the first five with adequate complete-cycle evidence from each folder. Write one PNG and PDF per chosen file, plus a `source_index.csv` and a `skipped_files.csv`. Review the pilot before expanding to all 100 files per folder.

**900 files have a numerical cycle-2 candidate. The remaining 100 catalyst exports need review:** 42 in EC_cat_k, 36 in EC_cat_kd, and 22 in EC_cat_ks. Numerical screening checks the sampled sweep; it is not scientific validation of a model or mechanism. Inspect each file's cycle evidence and skip/report ambiguous selections rather than forcing a complete cycle.

## Plotting rules

- Keep every raw export unchanged.
- Preserve row order within the chosen cycle. **Never sort a CV by potential.**
- Preserve exported current signs and all selected points.
- Do not invent, smooth, interpolate, resample, normalize, subtract a baseline, or shift potential.
- Potential **V** and current **A** are verified for all 1,000 exports. SR explicitly labels these units; the other files have a byte-identical generator-output match and audited source-model evidence for `tcd.Itot_es1` in A.
- Use the per-file metadata for axis labels and cycle selection. Compare folders only after checking their model metadata.

Submit the final practice PNG, the prompt used, and the source filename and cycle. Generated outputs belong in `outputs/`, which is excluded from version control.


