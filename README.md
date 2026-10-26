# html_javascript_subvention_data_extraction
Use HTML Javascript to extract key subvention data from mock FIN excel templates

## Tool

`approved_budget_disbursement.html` – a single, dependency-free HTML page (step 1 of the process flow, *Approved Budget and Disbursement*). Open it in Microsoft Edge or Chrome 103+.

1. Choose the funding stream: **Output GST**, **Disallowed GST**, **MAF** or **MAF Plus** (all Annex B1 streams).
2. Select one or more GBP papers, the SuSy disbursement file, the PHI name mapping and, optionally, the MAF Standalone Budget file. Each GBP's cluster (NHG / NUHS / SHS) is read from its sheet or file name and selects the SuSy tab (`<Cluster>_Report`) automatically.
3. **Run extraction & checks** – GBP amounts (header row = first row with `Funding Period` in column A; columns G onwards) and SuSy amounts (`Total Approved Budget for FY`, PHI identified by the single value in G to the column before `Total`) are mapped to PHI official names and compared.
4. **Download output (.xlsx)** – one `Output` sheet; mismatches, duplicates and unmapped names are listed in `Remarks`.

Funding streams, header rows and column positions are set in the configuration block at the top of the script.

## Files

| Path | Contents |
|---|---|
| `01 Global Budget Paper/` | Mock GBP papers (Annex B1 NHG / NUHS / SHS, Annex B2 PGMG) and MAF Standalone Budget input |
| `02 SuSy Disbursement File/` | Mock SuSy disbursement spreadsheet (`NHG_Report`) |
| `PHI Name Mapping.xlsx` | Maps GBP and SuSy PHI names to official names (by FY and cluster) |
| `Sample Output - Mock.xlsx` | Example of the output layout |
| `funding-process-flow(3)(2).drawio` | Process flow diagram |

All workbooks contain **mock data only** – no real financial figures.
