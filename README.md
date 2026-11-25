# Workforce Attrition & Retention Analytics

An independent Power BI practice project exploring historical employee attrition patterns in the IBM HR Analytics Employee Attrition dataset. The analysis is descriptive and diagnostic; it does not predict future exits or establish causes. This is not a client engagement.

## Project files

- [Power BI report](powerbi/HR_Analytics_Dashboard.pbix)
- [Project presentation](presentations/Workforce_Attrition_Retention_Analytics_Presentation.pptx)
- [Repository license](LICENSE)
- Dashboard screenshots: [Workforce overview](screenshots/workforce-overview.png), [Workforce insights](screenshots/workforce-insights.png), [Satisfaction and performance](screenshots/satisfaction-performance.png), [Employee details](screenshots/employee-details.png), and [Executive insights](screenshots/executive-insights.png)
- [Data folder](data/)
- [Data dictionary file](documentation/data-dictionary.md)

## Dataset and provenance

The project README identifies the dataset as IBM HR Analytics Employee Attrition from Kaggle. The source CSV is not included in this repository, and the data folder README and data dictionary file are currently empty. The repository does not provide the exact Kaggle listing URL or a data license citation.

Because the source data and a completed data dictionary are absent, dataset counts, reported attrition metrics, segment comparisons, and Key Influencers values previously described in this README are not independently reproducible from the repository. They are omitted here until the source and calculations can be checked.

## Dashboard scope

The existing README describes a five-page Power BI report covering workforce overview, attrition segmentation, satisfaction and performance, employee-level details, and executive insights. The report file and five corresponding screenshot files are present. I have not independently validated the report model, DAX measures, Power Query steps, or numerical outputs.

The project is presented as descriptive analysis of a historical dataset. Segment differences should be interpreted with group sizes in mind, and observed associations should not be treated as causal effects or measured business impact.

## View the report

1. Download the PBIX from the link above and open it in Power BI Desktop.
2. To refresh the report, obtain the same source dataset from its original provider and reconnect the data source as needed. The source CSV is not bundled here, so refresh instructions cannot be verified from a clean checkout.
3. Use the screenshot links above for a static preview.

## Validation still needed

- Add a precise dataset source link and license/usage attribution.
- Decide whether the source CSV can be included; if not, document a reproducible download process.
- Complete the data dictionary.
- Reconcile the dashboard KPIs and reported associations against the source data and PBIX before publishing numerical findings.
- Document the Power BI model and refresh steps after checking them in Power BI Desktop.

## Tools represented in the repository

Power BI Desktop, Power Query, and DAX are described in the project documentation. The PBIX is the primary analytical artifact; no Python or SQL implementation is claimed for this project.
