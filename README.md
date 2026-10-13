# ATAC-QC Explorer

A lightweight, browser-based QC viewer for comparing ATAC-seq metrics extracted from MultiQC HTML reports.

## Getting started

Open `index.html` in a modern desktop browser (or deploy the repository using GitHub Pages). Choose one or more MultiQC `.html` reports, or drag and drop them onto the import area.

- Metrics in sample-oriented HTML tables are matched to a curated list of ATAC-seq QC metrics.
- Simple metric/value HTML tables are also supported.
- Each recognized sample appears in the QC matrix.
- Select the metrics you wish to plot. Charts are sortable and filterable by sample.
- Export individual charts as editable SVG or all detected values as CSV.

Processing happens **entirely in the browser**, without uploading data to a server.

## Important limitations

MultiQC output varies by version and by constituent tools. Some reports generate tables dynamically from embedded JavaScript or JSON instead of exposing ordinary HTML `<table>` rows; these cannot yet be reliably extracted by this viewer. Reports without recognized table entries are reported as warnings rather than silently plotted.

Some metric names may require aliases. Verify units (especially percentages vs fractions) and provenance before interpreting cross-run comparisons; no automated QC pass/fail thresholds are imposed.

For production-scale or version-independent analysis, ingest the structured MultiQC data directory (`multiqc_data.json`, general statistics TSV, or module-specific data) rather than relying solely on rendered HTML.

## Development

This is a dependency-free single-page app implemented in plain HTML, CSS, and JavaScript. No build step is required.

## Validation checklist

- [ ] Test against real MultiQC HTML exports from the lab's pipeline
- [ ] Verify all expected sample IDs and metric values against MultiQC
- [ ] Exercise multi-report import and overlapping sample names
- [ ] Verify SVG export in Illustrator/Inkscape and CSV in Excel
- [ ] Check display on smaller screens
