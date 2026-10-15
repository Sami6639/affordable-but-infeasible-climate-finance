# Affordable but Infeasible: Climate-Finance Advances under Reporting Uncertainty

Replication package aligned with the JCMS submission checked on 15 October 2026. Start here for this article's analyses, Tables 1–5 and A1, and Figures 1–4.

This snapshot combines the original bounded-expenditure calculations with the later matched-contract and independent implementation checks. The paper studies hypothetical contract-design scenarios informed by public programme documents; it does not estimate UEFA's reporting-error distribution or recipient liquidity shortfalls.

## Reproduce the analyses

Use Python 3.12 and the pinned dependencies:

```sh
python -m venv .venv
.venv/bin/pip install -r revision-2026-10-12/requirements-lock.txt
.venv/bin/python revision-2026-10-12/run_all.py
```

On Windows, use `.venv\Scripts\python` and `.venv\Scripts\pip`. After installing dependencies, the analysis does not need network access. The runner verifies the 27 baseline files, reproduces the numerical outputs and figures in a separate working folder, and runs the independent implementation checks. It preserves the deposited baseline.

The runner passed again on 15 October 2026: all 17 scientific-output comparisons passed. See [the current execution record](jcms/reproduction_2026-10-15.json). The 540 uniform, 32 ceiling, 36 Gaussian and 20 constructive baseline checks are supplemented by 154 uniform matched-ramp cases, 36 Gaussian comparisons, 14 domain checks and 18 advance-maximisation cases.

## Article to data and code map

| Article item | Data or result | Calculation or provenance |
| --- | --- | --- |
| Table 1 Parameter and evidence register | [Table 1 CSV](jcms/table1_parameter_evidence_register.csv) | Transcribed from the supplied manuscript, including mathematical text; [parameters](revision-2026-10-07/data/parameters.json) and [source register](revision-2026-10-07/data/source_register.csv) distinguish reported anchors and assumptions. |
| Table 2 Independent constraint failures | [Table 2 CSV](revision-2026-10-07/results/table2_constraint_failures.csv) | [reproduce.py](revision-2026-10-07/code/reproduce.py), exact-spending and ceiling cases. |
| Table 3 Maximum financeable advances | [Table 3 CSV](revision-2026-10-07/results/table3_advances.csv) | Same script, cap ratios and donor-cost scenarios. |
| Table 4 Programme-to-cash decision worksheet | [Table 4 CSV](jcms/table4_programme_cash_worksheet.csv) | Manuscript transcription; [institutional claim register](revision-2026-10-12/sources/institutional_claim_register.csv). It is a documentary worksheet, not an estimated dataset. |
| Table 5 Reporting-dispersion sensitivity | [Table 5 CSV](revision-2026-10-07/results/table5_dispersion.csv) | Same baseline script; equality decisions use unrounded thresholds. |
| Table A1 Analytical antecedents | [Table A1 CSV](jcms/tableA1_analytical_antecedents.csv) | Manuscript transcription of the literature comparison; no new priority or source-verification claim is made. |
| Figure 1 Exact spending and available funding | [PNG](revision-2026-10-07/results/figure1.png), [series](revision-2026-10-07/results/figure1_series.csv) | Baseline script, uniform maximum under the two budget interpretations. |
| Figure 2 Advance finance and maximum donor exposure | [PNG](revision-2026-10-07/results/figure2.png), [series](revision-2026-10-07/results/figure2_series.csv) | Baseline script, exposure-cap and cost scenarios. |
| Figure 3 Fixed ledger under different cash schedules | [PNG](revision-2026-10-07/results/figure3.png), [series](revision-2026-10-07/results/figure3_series.csv) | Baseline script; alternative hypothetical payment orders for the same reported project ledger. |
| Figure 4 Distribution-specific bounded obligations | [PNG](revision-2026-10-07/results/figure4.png), [series](revision-2026-10-07/results/figure4_series.csv) | Baseline script, uniform and Gaussian frontiers at matched variance. |
| Central numerical results | [central_results.json](revision-2026-10-07/results/central_results.json) | Baseline script; maximum advance EUR 6,659,096.18, or 84.0264502%. |
| Matched-contract results and financial remedies | [new_analysis_summary.json](revision-2026-10-12/analysis/new_analysis_summary.json) | [independent_analysis.py](revision-2026-10-12/analysis/independent_analysis.py); additional cap authority or advance reduction EUR 473,403.82. |
| Appendix mathematical sensitivity | [separate mathematical audit](revision-2026-10-12/math/independent_math_audit_v1.py) | An additional implementation, separate from the main runner and its reported check counts. |

## Alignment with the submitted manuscript

[The alignment record](jcms/manuscript_alignment.json) identifies the supplied manuscript by SHA-256 and records 134 passing checks: table and figure counts, three table row counts, all 121 displayed body cells of Tables 2, 3 and 5, byte-identical embedded Figures 1–4, and four reported-result strings. Numerical table comparisons use the manuscript's displayed rounding. Tables 1, 4 and A1 are transcribed rather than treated as independently verified numerical outputs. This audit is an implementation and document-alignment check, not peer review or a fresh verification of every theoretical or bibliographic claim.

To check another local copy of this same manuscript, install `python-docx` and run:

```sh
python verify_article.py /path/to/manuscript.docx
```

The audit does not upload the Word document. Full manuscript and title-page files are not deposited here. The separately mentioned Supplementary Information Word file was not supplied for this alignment check; its complete table and figure inventory is therefore not certified by this record.

## Version and reuse

This article-specific snapshot derives from parent commit `6c2ee0e4258a9ece79541545011a9fb9c4986b0b`. The two preserved revision folders retain historical README titles and execution records; those historical labels are not alternative titles for the current article. The root README and the `jcms/` alignment files identify the current submission. Root-level outputs of the older, different analysis are excluded from this snapshot.

The original software licence is [MIT](revision-2026-10-12/LICENSE), subject to the [software-only scope and third-party exclusions](revision-2026-10-12/THIRD_PARTY_DATA.md). Public source documents are linked, not redistributed. No archival DOI is claimed. The repository is public and identifies its author; this link belongs on the separate title page during double-blind review.
