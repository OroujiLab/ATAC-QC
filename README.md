# ATAC-QC

A lightweight, browser-based tool for comparing quality-control (QC) metrics across bulk ATAC-seq samples.

The viewer reads QC metrics from selected HTML reports and displays interactive bar charts to help assess sample-level data quality. Supported metrics include read mapping, duplication, library complexity (NRF/PBC), FRiP, TSS enrichment, peak counts, and other reported QC measures.

## Usage

1. Open [`index.html`](index.html) in a web browser.
2. Click **Select QC Files** and choose one or more bulk ATAC-seq QC reports in HTML format.
3. Select up to **six metrics** from the available options.
4. Compare values across samples in the resulting bar charts; hover over a bar to see its value.

Reports should contain metric names in HTML table-header cells (`<th>`) with numeric values in the adjacent table-data cells (`<td>`). Only metrics recognized by the viewer are shown, and available metrics depend on the input reports.

## Implementation

The tool is a standalone HTML page using [D3.js v6](https://d3js.org/) for visualization. Reports are read locally in the browser; no server setup or installation is required. An internet connection is needed to load D3.js from its CDN.

