# Production Throughput Model & Root Cause Analysis

## **Project Overview**

**The Chaos on the Ground:** A high-volume beverage bottling line (CO-600) was bleeding 15% to 20% of its daily capacity to unexplained downtime. Operations believed operator speed was the bottleneck, but lacking a unified view of disparate machine logs, they couldn't confidently target interventions.
**The Solution:** I engineered a programmatic "Control Tower". Utilizing Excel Power Query for ETL processes, I merged unstandardized logs into a unified fact table, isolating root causes that directly impact inventory availability and operational throughput in a high-volume manufacturing environment.

## **Data Sources**

- **Manufacturing Execution System (MES) Exports:** Uncleaned shift production logs, machine downtime codes, and operator productivity metrics.
- **Data Dictionary:** A CSV defining 12 strict downtime categorization codes.

## **Process**

- **ETL Engineering (Power Query):** Replaced manual spreadsheet merging with automated Power Query unpivoting to transform 12 distinct downtime columns into a clean, analytical schema.
- **Downtime Segmentation Logic:** Partitioned downtime into "Operator-Controllable" vs "Systemic" to eliminate performance assessment bias and isolate hardware/supply chain failures.
- **Root Cause Identification:** Conducted Pareto analysis of manufacturing bottling line downtime to identify the primary drivers of production delays and inventory shortages, mathematically isolating the "Vital Few" factors contributing to 80% of lost time.

## **Key Findings**

- **Systemic Failure:** Identified that **Machine Adjustments** and **Inventory Shortages** accounted for the vast majority of lost time, completely debunking the "operator speed" hypothesis.
- **Product Line Volatility:** The **CO-600 product format** was pinpointed as the source of extreme line instability, causing disproportionate downtime spikes.
- **Temporal Friction:** Revealed that lost time clusters predictably around peak production hours (12 PM, 2 PM, 7 PM), highlighting shift-change vulnerabilities.

## **Recommendations (Operational Scripts)**

- **Preventative Maintenance Roadmap:** Shift immediately from reactive break-fix to a targeted preventative maintenance schedule focused exclusively on the CO-600 line equipment.
- **Supply Chain Calibration:** Launch a cross-functional investigation into the root cause of Inventory Shortages to align material planning with true logistics lead times.
- **Targeted Training:** Provide specific, time-of-day training interventions for operators focused on machine adjustment procedures, mapping to the identified temporal vulnerability windows.

## **Next Steps**

- **Proactive Maintenance Alerts:** Evolve the analysis into a daily tracking dashboard that alerts maintenance supervisors when CO-600 downtime deviates from standard control limits.
- **Golden Pipeline Iteration:** Fully automate the `Manufacturing_Line_Productivity_Analysis.xlsx` data flow via Python scripts to eliminate manual Power Query refresh cycles.
