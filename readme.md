# Input data for manufacturing resource sharing

This repository provides the source records and derived input tables used in the case study of cloud-edge collaborative manufacturing resource sharing. It documents the data construction described in Section 7.1 and the inputs to the equipment replay, double auction, and repeated bidding experiments.

## Repository contents

| Directory | Contents | Paper connection |
|---|---|---|
| [01_sources](01_sources/README.md) | Original PIADE equipment records, the TORQ order extract, and economic conversion tables. | Data sources and input construction, Section 7.1. |
| [02_equipment_replay](02_equipment_replay/README.md) | Six S1 input tables and links to the original equipment intervals. | Equipment-state replay, Section 7.2. |
| [03_double_auction](03_double_auction/README.md) | Sampled auction inputs and populations for the MD/MP scale analysis. | Allocation efficiency and incentive properties, Section 7.3. |
| [04_repeated_bidding](04_repeated_bidding/README.md) | Thirty market sequences with fixed seeds and common random draws. | Adaptive bidding and participation, Section 7.4. |
| [05_parameter_sensitivity](05_parameter_sensitivity/README.md) | Parameter settings, ten supplementary learning input sequences, and retained sensitivity tables. | Section 7.5 and supplementary parameter analysis. |

## Data origins and traceability

**Equipment states** come from the [PIADE dataset](https://doi.org/10.5281/zenodo.7071747), which records five industrial packaging machines. The S1 tables preserve source chronology and describe 37 eligible eight-hour windows. Their lineage table identifies the original records contributing to each equipment slot.

**Auction and learning inputs** use the TORQ financial order extract released by the authors of [MUDA](https://doi.org/10.1609/aaai.v32i1.11450). Source prices and quantities are converted using the supplied calibration and category mapping. Every sampled participant retains a `SourceOrderID`, linking it to the cleaned source table and the corresponding original order.

Observed records and scenario assumptions are identified separately. External requests, release fractions, manufacturing categories, economic conversions, and participation draws are experimental settings. The mapped valuations and costs are model inputs, rather than measured factory accounts.

Each directory README explains the CSV structure and conversion rules. These files support inspection of the experimental inputs; the study combines observed source data with declared manufacturing scenarios and does not report a deployed industrial trial. Original source attribution and license information are retained in `01_sources/`.
