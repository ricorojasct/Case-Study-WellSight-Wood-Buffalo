WellSight Wood Buffalo: Oil & Gas Well Health Analysis
Project Overview
WellSight Wood Buffalo is a comprehensive Power BI analytics solution that evaluates the operational integrity, production efficiency, and well health of oil and gas operations in Alberta's Wood Buffalo region. By integrating multiple datasets from the Petrinex Alberta Public Data Portal, this project provides data-driven insights for investment decisions, operational optimization, and sustainability planning.
Analysis Period: January - August 2025
Geographic Focus: Wood Buffalo Region, Alberta
Total Wells Analyzed: 180 wells across 22 active operators

Project Objectives
This analysis addresses five critical business questions:

Operator Excellence: Which operators maintain the healthiest and most productive well portfolios in Wood Buffalo?
Well Health Assessment: What is the overall health profile and lifecycle distribution of wells in the region?
Performance Correlation: How does production performance relate to well lifecycle and operational integrity?
Operational Patterns: How do production and injection patterns reflect operational integrity over time?
Investment Targeting: Are there geographic or operational trends that could guide future capital allocation?


📁 Data Sources
All data sourced from Petrinex Alberta Public Data Portal (publicly available):
DatasetPurposeKey FieldsVolumetric Data (Jan-Aug 2025)Tracks production, injection, and fluid movementProductionMonth, ActivityCode, ProductCode, VolumePRAFacilityIds.csvFacility metadata and locationFacilityCode, FacilityType, Location, OperationalStatusPRABAIdentifiers.csvOperator identificationBAName, BACode, CorpStatusPRAProductCodes.csvProduct definitionsProductCode, ProductNamePRAActivityCodes.csvActivity classificationActivityCode, ActivityName

🏗️ Data Architecture
Star Schema Design
The project implements a star schema for optimal query performance and analytical flexibility:
Fact Table:

Fact_Volume → Volumetric activity data (production, injection, losses)

Dimension Tables:

Dim_Facility → Facility location and operational status
Dim_Operator → Operator identity and corporate status
Dim_Product → Product categories (Oil, Gas, Water)
Dim_Activity → Activity types (PROD, INJ, FLARE, VENT)
Dim_Date → Calendar table for time intelligence
Dim_Region → Custom region mapping (Township/Range classification)
Dim_TRM → Township-Range-Meridian geographic hierarchy
Dim_FacilityStatusCurrent → Current operational status snapshot
Status_By_Month → Historical status tracking

Key Relationships:

FacilityCode → ReportingFacilityIdentifier
BACode → OperatorBAID
ProductCode → ProductID
ActivityCode → ActivityID


📏 Key Performance Indicators
Production Metrics

Total Oil Volume: 5.38M m³ (August 2025 MTD)
Total Gas Volume: Tracked across all operators
Average Well Productivity: 0.24M m³ per well
Month-over-Month Growth: 14.36%

Integrity & Efficiency Metrics

Injection:Production Ratio (I:P): 1.13 (healthy reservoir pressure maintenance)
Flare/Vent Rate: 0.06% (well below regulatory thresholds)
Volume Balancing: Tracked via IMBAL/DIFF calculations

Well Health Indicators

Active Wells: 93.46% (143 wells)
Suspended Wells: 6.54% (10 wells)
Total Well Count: 180 wells under management

Operator Performance Metrics

Top 5 Operators by Production: Identified and ranked
Operator Health Score: Composite metric based on I:P ratio, productivity, and well count
Investment Score: Calculated from multiple performance factors


📊 Dashboard Pages
1. Executive Dashboard
Purpose: High-level operational overview for stakeholders
Key Visuals:

KPI cards: Total Wells, Active Operators, Oil Volume MTD, MoM%, I:P Ratio
Production vs Injection Over Time (line chart)
Operator Leaderboard (horizontal bar chart)
Well Health Snapshot (stacked column chart by operator)

Key Insights:

180 wells managed by 22 active operators
Stable production trends with 14.36% month-over-month growth
Balanced I:P ratio of 1.13 indicates effective reservoir management
SUNCOR, CNOOC, and CENOVUS lead in total production volume

2. Operator Performance & Portfolio Quality
Purpose: Detailed operator-level analysis and benchmarking
Key Visuals:

Operator Scorecard (sortable table)
Top Operators comparison (bar chart)
Monthly Trend by Operator (small multiples line chart)

Key Insights:

SUNCOR ENERGY INC.: Largest producer (26.29M m³ oil, 6.88M m³ gas) with healthy I:P of 1.12
CNOOC PETROLEUM NORTH AMERICA: Strong balanced performance (10.41M m³ oil, I:P 0.72)
CENOVUS ENERGY INC.: Consistent production with optimal I:P of 1.70
Average well productivity ranges from 0.00M to 10.41M depending on operator scale

3. Well Health & Lifecycle
Purpose: Assess well status, lifecycle distribution, and environmental compliance
Key Visuals:

Flaring & Venting Trend (column chart)
Status Distribution Over Time (area chart)
Current Snapshot Well Status (pie chart)
Operator health table with I:P ratios

Key Insights:

Flare/vent rate of 0.06% demonstrates excellent emissions management
93.46% active well rate indicates productive portfolio
Stable status distribution over 8-month period
Major operators maintain I:P ratios between 1.70 and 3.99

4. Geography & Investment Targeting
Purpose: Spatial analysis and investment prioritization
Key Visuals:

Regional Well Activity Overview (geographic heat map)
Investment scoring table
Production Efficiency Over Time (line chart)

Key Insights:

Production concentrated in southwestern Wood Buffalo region (near Fort McMurray)
Top investment scores: CENOVUS (1,566.98), CNOOC (1,296.37), ATHABASCA (974.74)
Clear geographic clustering suggests infrastructure advantages
Production efficiency spike in June 2025 (1.2M peak) followed by normalization


🔍 Key Findings
Operational Excellence

Top Performers: SUNCOR, CNOOC, and CENOVUS demonstrate superior portfolio management
Efficiency Leader: CNOOC achieves highest average well productivity (10,410.44 m³)
Balanced Operations: Industry average I:P ratio of 1.13 indicates sustainable production practices

Well Health

Strong Portfolio: 93.46% active well rate significantly above industry benchmarks
Low Environmental Impact: 0.06% flare/vent rate demonstrates environmental stewardship
Stable Operations: Minimal status changes over 8-month period suggest operational maturity

Geographic Patterns

Core Production Zone: Southwestern Wood Buffalo shows highest well density
Infrastructure Advantage: Geographic clustering near Fort McMurray enables operational efficiencies
Investment Opportunities: Operators with high investment scores and balanced I:P ratios present lower risk profiles

Trend Analysis

Production Growth: 14.36% month-over-month increase in August 2025
Seasonal Variation: June 2025 efficiency peak suggests optimized summer operations
Consistent Performance: Major operators show stable production trends across analysis period


💡 Strategic Recommendations
For Investors

Target Operators: Focus on CENOVUS, CNOOC, and ATHABASCA based on investment scores
Portfolio Quality: Prioritize operators with I:P ratios between 1.0-2.0 and high active well percentages
Geographic Focus: Wells in the southwestern cluster show higher productivity and infrastructure access

For Operators

Best Practices: Benchmark against SUNCOR's balanced production-injection methodology
Efficiency Gains: Investigate CNOOC's high per-well productivity for operational insights
Environmental Leadership: Maintain or improve upon industry-leading 0.06% flare/vent rate

For Regulators

Monitoring: Current flare/vent rates demonstrate effective industry compliance
Well Status: High active well percentage suggests minimal orphan well risk
Regional Planning: Geographic clustering indicates mature development requiring infrastructure support


🛠️ Technical Implementation
Tools & Technologies

Power BI Desktop: Data modeling and visualization
Power Query: ETL processes and data transformation
DAX: Calculated columns, measures, and KPIs
Azure Maps: Geographic visualization

Calculated Measures (DAX Examples)
dax// Injection:Production Ratio
I:P Ratio = 
DIVIDE(
    [Total_Volume_Inj],
    [Total_Oil_Volume],
    BLANK()
)

// Average Well Productivity
Avg_Well_Productivity (Oil) = 
DIVIDE(
    [Total_Oil_Volume],
    [Total_Wells],
    0
)

// Investment Score
Investment_Score = 
    [Total_Oil_Volume] * 0.4 +
    [Avg_Well_Productivity (Oil)] * 0.3 +
    (2 - ABS([I:P Ratio] - 1.2)) * 100
Data Refresh

Source: Petrinex API (monthly updates)
Refresh Schedule: Monthly (recommended)
Data Volume: ~2,313 facility records, 180 wells, 22 operators


📈 Future Enhancements

Predictive Analytics: ML models for production forecasting and well failure prediction
Real-Time Monitoring: Integration with live SCADA data feeds
ESG Metrics: Expanded environmental impact tracking (GHG emissions, water usage)
Economic Analysis: NPV calculations and decline curve analysis
Comparative Regional Analysis: Expand to other Alberta basins for benchmarking


📝 Usage & Deployment
Prerequisites

Power BI Desktop (latest version)
Access to Petrinex Alberta Public Data Portal
Basic understanding of oil & gas operations

Setup Instructions

Clone this repository
Download datasets from Petrinex portal (links in documentation)
Open WellSight_WoodBuffalo.pbix in Power BI Desktop
Update data source connections in Power Query
Refresh all data sources
Publish to Power BI Service (if applicable)

File Structure
WellSight-Wood-Buffalo/
├── Data/
│   ├── Volumetric_Data_2025.csv
│   ├── PRAFacilityIds.csv
│   ├── PRABAIdentifiers.csv
│   ├── PRAProductCodes.csv
│   └── PRAActivityCodes.csv
├── Reports/
│   └── WellSight_WoodBuffalo.pbix
├── Documentation/
│   ├── Data_Dictionary.md
│   └── DAX_Measures.md
└── README.md

🤝 Contributing
Contributions are welcome! Areas for improvement:

Additional data source integrations
Enhanced DAX measure optimization
Alternative visualization approaches
Documentation improvements


📄 License
This project analyzes publicly available data from the Alberta Energy Regulator. Data usage complies with Petrinex terms of service.
