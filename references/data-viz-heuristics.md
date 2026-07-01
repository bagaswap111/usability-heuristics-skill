# Data Visualization Heuristics

Apply when the UI displays data to users — charts, graphs, KPIs, data tables, status indicators, progress bars, sparklines, gauges, or any dashboard-style layout. These supplement (not replace) the core 10 heuristics.

---

## DV-1 Control Ordering Follows Cognitive Flow

Controls that configure data queries should be ordered by their semantic weight — from broadest scope to narrowest detail.

### Checklist
- Are global controls (affecting multiple panels) positioned before local controls?
- Does the control order follow "what data → what time range → how granular → how to display"?
- Are controls that change data semantics (e.g. metric type, aggregation mode) placed before controls that change presentation (chart type, color)?

---

## DV-2 Interdependent Controls Are Visually and Logically Linked

When one control constrains another's valid options, this relationship must be perceivable.

### Checklist
- Are interdependent controls adjacent or visually grouped?
- When a parent control changes, do dependent controls update their options automatically?
- If a previously valid selection becomes invalid, does the UI auto-select a reasonable default and indicate the change?
- Is subtle visual grouping used (proximity, spacing) rather than heavy separators?

---

## DV-3 Chart Type Matches Data Semantics

The visualization type should be appropriate for the data being displayed.

### Checklist
- Are time series shown with line or area charts (not pie charts)?
- Are part-to-whole relationships shown with stacked charts or treemaps?
- Are comparisons shown with bar charts?
- Are flow/process relationships shown with Sankey or flow diagrams?
- Does the chart type selection (if user-configurable) exclude inappropriate options?

---

## DV-4 Data Density Is Appropriate

The amount of data shown should match the display space and user task.

### Checklist
- Is the granularity appropriate for the selected time window? (not 5-minute bars for a 90-day view)
- Are there too many series to distinguish visually? (more than 6-8 colors becomes unreadable)
- Is the "Others" / aggregation category used when there are many small items?
- Are axes scaled appropriately? (no misleading truncation or excessive whitespace)

---

## DV-5 Filter and Display Controls Are Distinguishable

Users should understand which controls change the data query and which change only the presentation.

### Checklist
- Can the user tell which controls trigger a data reload vs. a client-side re-render?
- Are data-query controls (time range, metric selection) given more visual weight or positioned first?
- Are pure display controls (chart type, sort order, show/hide legend) clearly secondary?

---

## DV-6 Empty and Edge States Are Handled

Dashboards must gracefully handle missing, zero, or unexpected data.

### Checklist
- What happens when no data exists for the selected time range? (empty chart with message, not a blank area)
- How are zero values displayed? (not confused with missing data)
- What happens at extreme selections? (very short time range, very fine granularity)
- Are loading states shown while data is being fetched or recalculated?
