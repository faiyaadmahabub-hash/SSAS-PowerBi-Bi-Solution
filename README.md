# AdventureWorks Business Intelligence System

A comprehensive Business Intelligence solution developed for AdventureWorks bicycle manufacturing company to support global expansion strategy through data-driven insights and analytics.

## Table of Contents
- [Project Overview](#project-overview)
- [Company Profile](#company-profile)
- [Project Objectives](#project-objectives)
- [Methodology](#methodology)
- [System Architecture](#system-architecture)
- [Project Structure](#project-structure)
- [Data Model](#data-model)
- [Key Metrics & Calculations](#key-metrics--calculations)
- [Business Intelligence Reports](#business-intelligence-reports)
- [Prerequisites](#prerequisites)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
- [Key Findings](#key-findings)
- [Recommendations](#recommendations)
- [Technologies Used](#technologies-used)
- [Author](#author)

---

## Project Overview

This Business Intelligence (BI) solution transforms AdventureWorks' raw transactional data into actionable intelligence through a structured approach that includes data warehousing, multidimensional modeling (OLAP cube), interactive dashboards, and comprehensive executive reporting.

The system enables stakeholders to:
- Analyze sales performance across multiple dimensions (time, geography, product, customer)
- Track key performance indicators (KPIs) in real-time
- Identify market opportunities and risks
- Make data-driven decisions for global expansion

**Course**: CT122-3-2-BIS - Business Intelligence System
**Institution**: Asia Pacific University (APU)
**Cohort**: APU2F2411CS(DA)
**Submission Date**: July 25, 2025

---

## Company Profile

**AdventureWorks** is a leading global bicycle manufacturer and Original Equipment Manufacturer (OEM) component supplier founded in 2002.

### Key Statistics:
- **Headquarters**: Bothell, Washington, USA
- **Annual Revenue**: ~RM 89.84 million (USD equivalent)
- **Market Share**: 55% of U.S. bicycle market
- **Employees**: 8,000
- **Production Facilities**: Portland (USA), Dortmund (Germany), and others
- **Markets**: North America, Europe, Asia-Pacific

### Distribution Channels:
- **50%** - Traditional retail partners
- **30%** - Direct-to-consumer e-commerce
- **20%** - Third-party distributors

---

## Project Objectives

### Aim
Transform AdventureWorks' raw data into actionable intelligence by executing a structured Business Intelligence process that encompasses data warehousing, multidimensional modeling, dashboard visualization, and executive reporting.

### Specific Objectives:
1. **Data Integration**: Stage and integrate all source data in SQL Server Management Studio (SSMS) to ensure a clean, consolidated enterprise data warehouse
2. **Multidimensional Modeling**: Design and deploy an SSAS cube that models critical measures alongside dimensions for rapid OLAP queries
3. **Interactive Dashboards**: Build Power BI dashboards that surface sales and customer insights through dynamic visuals
4. **Executive Reporting**: Compile a Business Performance Management (BPM) report with strategic recommendations for senior leadership

---

## Methodology

This project follows the **CRISP-DM (Cross-Industry Standard Process for Data Mining)** methodology, a proven framework for data mining and business intelligence projects.

### CRISP-DM Phases:

#### 1. Business Understanding
- **Goal**: Expand market presence from 55% US dominance to global reach
- **Focus**: Optimize performance between reseller and e-commerce channels
- **Objective**: Gain holistic view of sales performance, market trends, and customer preferences

#### 2. Data Understanding
- Data source: AdventureWorksDW2019 database in SQL Server
- Exploration of relevant tables and key attributes
- Data quality verification

#### 3. Data Preparation
- Data cleaning and validation
- Standardization of formats (currency, dates)
- Handling missing values
- Selection of appropriate data for visualizations

#### 4. Modeling
- Development of OLAP cube structure
- Creation of MDX queries for complex calculations
- Design of dimension hierarchies
- Implementation of KPIs

#### 5. Evaluation
- Validation against business objectives
- Stakeholder review of dashboards and reports
- Performance testing of queries

#### 6. Deployment
- Publication of dashboards
- Documentation and training
- Monitoring and maintenance setup

### Justification for CRISP-DM
CRISP-DM is well-suited for this project because it:
- Starts with clear business understanding
- Supports iterative feedback loops
- Maintains focus on business goals
- Delivers reliable and actionable insights

---

## System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    SQL Server Database                       │
│                  (AdventureWorksDW2019)                      │
│  ┌───────────────┐  ┌────────────────────────────────────┐  │
│  │  Fact Tables  │  │      Dimension Tables              │  │
│  │  - Internet   │  │  - DimCustomer                     │  │
│  │    Sales      │  │  - DimProduct                      │  │
│  │  - Reseller   │  │  - DimDate                         │  │
│  │    Sales      │  │  - DimSalesTerritory               │  │
│  └───────────────┘  │  - DimPromotion                    │  │
│                     │  - DimProductCategory              │  │
│                     │  - DimProductSubcategory           │  │
│                     └────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
                            ↓
┌─────────────────────────────────────────────────────────────┐
│        SQL Server Analysis Services (SSAS)                   │
│                  Visual Studio Project                       │
│  ┌─────────────────────────────────────────────────────┐    │
│  │        OLAP Cube: Adventure Works DW2019            │    │
│  │                                                      │    │
│  │  Measure Groups:                                    │    │
│  │  - FactInternetSales                                │    │
│  │  - FactResellerSales                                │    │
│  │                                                      │    │
│  │  Calculated Measures (MDX):                         │    │
│  │  - Total Sales Amount                               │    │
│  │  - Total Cost of Products                           │    │
│  │  - Internet GPM                                     │    │
│  │  - Reseller GPM                                     │    │
│  │  - Total GPM                                        │    │
│  │  - Cost Ratio                                       │    │
│  │  - Profit Margin                                    │    │
│  └─────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
                            ↓
┌─────────────────────────────────────────────────────────────┐
│                    Power BI Desktop                          │
│              Interactive Dashboards & Reports                │
│  ┌─────────────────────┐  ┌──────────────────────────┐      │
│  │ Overall Market      │  │ Financial Performance    │      │
│  │ Analysis Report     │  │ Report                   │      │
│  └─────────────────────┘  └──────────────────────────┘      │
└─────────────────────────────────────────────────────────────┘
```

---

## Project Structure

```
BIS Visual Studio/
│
├── BS 2411 Lab 2 Demo.sln              # Visual Studio Solution file
├── BS 2411 Lab 2 Demo.dwproj           # SSAS Data Warehouse Project
├── BS 2411 Lab 2 Demo.database         # Database configuration
│
├── Data Sources/
│   └── Adventure Works DW2019.ds       # Data source connection to SQL Server
│
├── Data Source Views/
│   └── Adventure Works DW2019.dsv      # Logical view of data warehouse
│
├── Cubes/
│   ├── Adventure Works DW2019.cube     # Main OLAP cube definition
│   └── Adventure Works DW2019.partitions # Cube partitioning configuration
│
├── Dimensions/
│   ├── Dim Customer.dim                # Customer dimension
│   ├── Dim Date.dim                    # Date/time dimension
│   ├── Dim Product.dim                 # Product dimension
│   ├── Dim Product Category.dim        # Product category dimension
│   ├── Dim Product Subcategory.dim     # Product subcategory dimension
│   ├── Dim Promotion.dim               # Promotion dimension
│   └── Dim Sales Territory.dim         # Geographic sales territory dimension
│
├── Power BI/
│   └── Business Intelligence Systems Assignment.pbix  # Power BI Dashboard
│
├── Documentation/
│   └── BIS Report - Faiyad Mahabub.docx  # Comprehensive project report
│
├── bin/                                # Build output directory
├── obj/                                # Object files directory
└── README.md                           # This file
```

---

## Data Model

### Fact Tables (Measure Groups)

#### 1. FactInternetSales
Captures direct-to-consumer online sales transactions.

**Measures**:
- Sales Amount
- Order Quantity
- Unit Price
- Extended Amount
- Discount Amount
- Product Standard Cost
- Total Product Cost
- Tax Amount
- Freight

#### 2. FactResellerSales
Captures B2B sales through retail partners and distributors.

**Measures**: (Same as FactInternetSales)

### Dimensions

#### 1. Customer Dimension
**Attributes**:
- Customer Key (Primary)
- First Name
- Gender
- Marital Status
- Education
- Yearly Income
- Commute Distance
- Geography Key (Foreign)

**Purpose**: Enables demographic analysis and customer segmentation

#### 2. Date Dimension
**Attributes**:
- Date Key (Primary)
- Calendar Year
- English Month Name
- Month Number of Year

**Purpose**: Supports time-based analysis and trend identification

#### 3. Product Dimension
**Attributes**:
- Product Key (Primary)
- Product Subcategory Key (Foreign)
- Product Category Key (Foreign)
- English Product Name
- English Product Category Name
- English Product Subcategory Name
- Model Name
- Color
- Standard Cost
- English Description

**Purpose**: Enables detailed product-level sales analysis and categorization

#### 4. Product Category Dimension
**Attributes**:
- Product Category Key (Primary)
- Product Category Alternate Key
- English Product Category Name
- Spanish Product Category Name
- French Product Category Name

**Purpose**: Top-level product classification

#### 5. Product Subcategory Dimension
**Attributes**:
- Product Subcategory Key (Primary)
- Product Subcategory Alternate Key
- English Product Subcategory Name
- Spanish Product Subcategory Name
- French Product Subcategory Name
- Product Category Key (Foreign)

**Purpose**: Mid-level product classification with hierarchy support

#### 6. Sales Territory Dimension
**Attributes**:
- Sales Territory Key (Primary)
- Sales Territory Country
- Sales Territory Region

**Purpose**: Geographic analysis and regional performance tracking

#### 7. Promotion Dimension
**Attributes**:
- Promotion Key (Primary)
- Discount Percentage
- English Promotion Name
- English Promotion Type
- English Promotion Category
- Start Date
- End Date

**Purpose**: Campaign effectiveness analysis

---

## Key Metrics & Calculations

All calculations are implemented using MDX (Multidimensional Expressions) in the SSAS cube.

### 1. Total Sales Amount
**Formula**: `[Internet Sales Amount] + [Reseller Sales Amount]`
**Format**: Currency
**Purpose**: Consolidated revenue across all sales channels

### 2. Total Cost of Products
**Formula**: `[Internet Total Product Cost] + [Reseller Total Product Cost]`
**Format**: Currency
**Purpose**: Total cost of goods sold across all channels

### 3. Internet GPM (Gross Profit Margin)
**Formula**: `([Internet Sales Amount] - [Internet Total Product Cost]) / [Internet Sales Amount]`
**Format**: Percentage
**Purpose**: Profitability analysis for e-commerce channel

### 4. Reseller GPM (Gross Profit Margin)
**Formula**: `([Reseller Sales Amount] - [Reseller Total Product Cost]) / [Reseller Sales Amount]`
**Format**: Percentage
**Purpose**: Profitability analysis for B2B channel

### 5. Total GPM (Gross Profit Margin)
**Formula**: `([Total Sales Amount] - [Total Cost of Products]) / [Total Sales Amount]`
**Format**: Percentage
**Purpose**: Overall company profitability metric

### 6. Cost Ratio
**Formula**: `[Total Cost of Products] / [Total Sales Amount]`
**Format**: Percentage
**Purpose**: Expense efficiency analysis

### 7. Profit Margin
**Formula**: `[Total Sales Amount] - [Total Cost of Products]`
**Format**: Currency
**Purpose**: Absolute profit value for financial analysis

---

## Business Intelligence Reports

### 1. Overall Market Analysis Report
**Focus**: Global market presence and performance
**Visualizations**:
- Global sales distribution map
- Regional sales growth trends
- Customer demographics breakdown

**Insights**:
- Identifies strongest markets
- Tracks market development over time
- Reveals customer base composition

### 2. Financial Performance Report
**Focus**: Profitability and channel performance
**Visualizations**:
- Sales trend analysis
- Channel performance by region
- Key profitability metrics (KPIs)
- Revenue by product category

**Insights**:
- Compares Internet vs. Reseller channel effectiveness
- Highlights most profitable products
- Shows seasonal patterns and trends

### 3. Global Sales Distribution
**Key Findings**:
- **Top Markets**: USA (RM 89.84M), Australia (RM 89.51M), UK (RM 83.84M)
- **Market Share**: 55% concentrated in United States
- **GPM Leaders**: USA (4.87%), Australia (4.64%)
- **Concerns**: Unknown segment (RM 80.45M) with low GPM (0.58%)

### 4. Regional Sales Growth Trends (2020-2024)
**Key Findings**:
- **Star Performer**: Southwest region (11.43K → 10.49M from 2020-2023)
- **Consistent Growth**: Canada (3.65M → 6.77M)
- **Critical Issue**: Sharp 99.6% revenue decline in 2024 across all territories
- **Growth Rate**: Northwest increased 132% from 2020-2023

### 5. Customer Demographics
**Key Findings**:
- **Gender Balance**: Female (RM 175.71M) vs. Male (RM 175.45M) - nearly equal
- **Marital Status**: Married (RM 176.09M) vs. Single (RM 175.07M)
- **Data Quality Issue**: RM 80.45M (18.6%) from incomplete demographic data

### 6. Sales Trend Analysis
**Key Findings**:
- **Peak Period**: December 2023 (RM 5.39M)
- **Seasonal Pattern**: Clear holiday season demand spike
- **Critical Drop**: 99.6% revenue collapse in January 2024

### 7. Channel Performance
**Key Findings**:
- **Internet GPM**: 41.15% (highly profitable)
- **Reseller GPM**: 0.58% (severely underperforming)
- **Total GPM**: 11.43%
- **Cost Ratio**: 88.57% (89% of revenue goes to costs)

### 8. Product Performance
**Key Findings**:
- **Top Products**: Mountain-200 series dominates (43.7% of revenue)
- **Revenue Concentration**: Top 5 products generate RM 18.98M
- **Portfolio Risk**: Heavy concentration in mountain bikes
- **Gap**: Limited urban/commuter bike offerings

---

## Prerequisites

### Software Requirements:
1. **SQL Server 2019** or later
   - Database Engine
   - Analysis Services (Multidimensional mode)
   - SQL Server Management Studio (SSMS)

2. **Visual Studio 2019** or later
   - Microsoft Analysis Services Projects extension
   - SQL Server Data Tools (SSDT)

3. **Power BI Desktop** (Latest version)

4. **.NET Framework 4.7.2** or later

### Database Requirements:
- **AdventureWorksDW2019** sample database installed on SQL Server
- Appropriate permissions to access and query the database

---

## Installation & Setup

### Step 1: Install AdventureWorksDW2019 Database
```sql
-- Download AdventureWorksDW2019 backup from Microsoft
-- Restore the database in SQL Server Management Studio
RESTORE DATABASE AdventureWorksDW2019
FROM DISK = 'C:\Path\To\AdventureWorksDW2019.bak'
WITH MOVE 'AdventureWorksDW2019_Data' TO 'C:\SQL\DATA\AdventureWorksDW2019.mdf',
     MOVE 'AdventureWorksDW2019_Log' TO 'C:\SQL\LOG\AdventureWorksDW2019.ldf'
GO
```

### Step 2: Configure Data Source Connection
1. Open the solution in Visual Studio: `BS 2411 Lab 2 Demo.sln`
2. Navigate to **Data Sources** → `Adventure Works DW2019.ds`
3. Update the connection string to match your SQL Server instance:
   ```
   Provider=SQLOLEDB.1;
   Data Source=YOUR_SERVER_NAME\INSTANCE_NAME;
   Integrated Security=SSPI;
   Initial Catalog=AdventureWorksDW2019
   ```
4. Test the connection

### Step 3: Build and Deploy SSAS Project
1. In Visual Studio, set the **Deployment Server** in project properties:
   - Right-click project → **Properties**
   - Set **Server** to your SSAS instance (e.g., `localhost\MSSQLSERVERNEW`)
   - Set **Database** to `BS 2411 Lab 2 Demo`
2. Build the solution: **Build** → **Build Solution** (Ctrl+Shift+B)
3. Deploy the cube: **Build** → **Deploy Solution** (F5)

### Step 4: Process the Cube
1. In SQL Server Management Studio, connect to Analysis Services
2. Navigate to **Databases** → `BS 2411 Lab 2 Demo` → **Cubes** → `Adventure Works DW2019`
3. Right-click the cube → **Process**
4. Select **Process Full** → **OK**
5. Wait for processing to complete

### Step 5: Open Power BI Dashboard
1. Open Power BI Desktop
2. Open file: `Business Intelligence Systems Assignment.pbix`
3. If prompted, update the data source connection to point to your SSAS server
4. Refresh the data

---

## Usage

### Querying the SSAS Cube

#### Using MDX in SQL Server Management Studio:
```mdx
-- Example: Top 10 Products by Total Sales
SELECT
  NON EMPTY {[Measures].[Total Sales Amount]} ON COLUMNS,
  NON EMPTY TOPCOUNT([Product].[English Product Name].[English Product Name].MEMBERS, 10, [Measures].[Total Sales Amount]) ON ROWS
FROM [Adventure Works DW2019]
```

#### Using Excel:
1. Open Excel
2. **Data** → **Get Data** → **From Database** → **From Analysis Services**
3. Connect to your SSAS instance
4. Select `Adventure Works DW2019` cube
5. Drag dimensions and measures to create PivotTables

### Exploring Power BI Dashboards

The Power BI file contains two main report pages:

#### 1. Overall Market Analysis Report
- **Global Sales Distribution**: Interactive map showing sales by country
- **Regional Sales Growth**: Line chart tracking year-over-year growth
- **Customer Demographics**: Bar charts for gender and marital status segmentation

**Interactivity**:
- Click on any country/region to filter other visuals
- Use year slicer to focus on specific time periods
- Hover over data points for detailed tooltips

#### 2. Financial Performance Report
- **Sales Trend Analysis**: Time series of monthly sales
- **Channel Performance by Region**: Stacked bar chart comparing Internet vs. Reseller
- **Key Profitability Metrics**: Card visuals showing GPM, Cost Ratio
- **Revenue by Product Category**: Tree map of top products

**Interactivity**:
- Cross-filter across all visuals
- Use channel filter to compare Internet vs. Reseller
- Drill down into product categories

---

## Key Findings

### Strengths:
1. **Market Leadership**: 55% market share in the US demonstrates strong competitive position
2. **Channel Diversity**: Balanced distribution across retail, e-commerce, and distributors
3. **Gender Equity**: Nearly perfect gender balance (50/50) in customer base
4. **Product Success**: Mountain-200 series shows strong market acceptance
5. **Internet Profitability**: 41.15% GPM on e-commerce channel is exceptional

### Weaknesses:
1. **Geographic Concentration**: Over-reliance on US market (55% of revenue)
2. **Channel Profitability Gap**: Reseller channel GPM (0.58%) is critically low
3. **High Cost Ratio**: 88.57% cost ratio limits expansion capital
4. **Product Concentration**: 43.7% revenue from top 5 products creates risk
5. **Data Quality**: 18.6% of revenue from customers with incomplete demographics

### Opportunities:
1. **Digital Expansion**: High Internet GPM (41.15%) supports digital-first strategy
2. **Underserved Markets**: Gaps in Asian and South American markets
3. **Urban Categories**: Limited presence in urban/commuter bike segments
4. **Seasonal Optimization**: Strong December sales (RM 5.39M) can be replicated

### Threats:
1. **Revenue Collapse**: 99.6% decline in early 2024 requires immediate investigation
2. **Market Disruption**: Unexplained drops across all territories in 2024
3. **Portfolio Risk**: Over-dependence on mountain bikes limits market flexibility
4. **Unknown Segment**: RM 80.45M from unclassified customers/markets

---

## Recommendations

### Immediate Actions (0-3 months):
1. **Investigate 2024 Decline**
   - Conduct root cause analysis for 99.6% revenue drop
   - Verify data accuracy and system integrity
   - Identify external factors (economic, supply chain, competitive)
   - **Priority**: CRITICAL - Delay expansion until resolved

2. **Improve Data Quality**
   - Implement mandatory demographic fields in customer forms
   - Launch targeted surveys to fill missing customer data
   - Classify the RM 80.45M "unknown" revenue segment
   - **Target**: Reduce incomplete data to <5%

3. **Fix Reseller Channel**
   - Analyze why Reseller GPM is only 0.58%
   - Review pricing structures and discount policies
   - Renegotiate distributor terms
   - **Target**: Achieve minimum 15% Reseller GPM

### Short-term Actions (3-6 months):
4. **Optimize Cost Structure**
   - Reduce 88.57% cost ratio through operational efficiency
   - Identify cost-saving opportunities in supply chain
   - Streamline production processes
   - **Target**: Achieve <85% cost ratio, 15% Total GPM

5. **Enhance Seasonal Planning**
   - Develop market-specific seasonal sales models
   - Increase production capacity by 40% for Q4/holiday season
   - Build inventory buffers for peak periods
   - **Target**: Capture 20% more holiday season revenue

6. **Channel Strategy Refinement**
   - Shift marketing spend toward high-GPM Internet channel
   - Implement Australia's successful channel mix (33.57% GPM) in new markets
   - Reduce reliance on low-margin reseller operations
   - **Target**: Increase Internet sales mix from 30% to 45%

### Medium-term Actions (6-12 months):
7. **Product Portfolio Diversification**
   - Develop urban/commuter bike lines for European and Asian markets
   - Create region-specific variants of successful 200-series products
   - Reduce concentration risk by expanding mid-tier offerings
   - **Target**: Reduce top-5 product concentration from 43.7% to <30%

8. **Geographic Expansion - Phase 1**
   - Focus on high-performing markets: Australia, Germany (balanced channel mix)
   - Conduct intensive market research in target Asian cities
   - Adapt product portfolio to local preferences and infrastructure
   - **Target**: Reduce US market concentration from 55% to 40%

### Long-term Actions (12+ months):
9. **Digital Transformation**
   - Implement digital-first expansion strategy leveraging 41.15% Internet GPM
   - Build localized e-commerce platforms for new markets
   - Invest in digital marketing and customer acquisition
   - **Target**: Achieve 50% of revenue from Internet channel

10. **Global Market Leadership**
    - Expand to underserved Asian and South American markets
    - Establish regional distribution centers
    - Build market-specific product portfolios
    - **Target**: Achieve true global presence with <30% concentration in any single country

---

## Technologies Used

### Database & Data Warehouse:
- **Microsoft SQL Server 2019** - Relational database management system
- **AdventureWorksDW2019** - Sample data warehouse database
- **T-SQL** - Query language for data manipulation

### Business Intelligence & Analytics:
- **SQL Server Analysis Services (SSAS)** - Multidimensional OLAP cube engine
- **MDX (Multidimensional Expressions)** - Query and calculation language for OLAP cubes
- **SQL Server Data Tools (SSDT)** - Development environment for BI solutions

### Visualization & Reporting:
- **Microsoft Power BI Desktop** - Interactive dashboard and visualization tool
- **Power Query** - Data transformation and preparation
- **DAX (Data Analysis Expressions)** - Formula language for Power BI calculations

### Development Tools:
- **Visual Studio 2019** - Integrated development environment (IDE)
- **Microsoft Analysis Services Projects Extension** - SSAS project template for Visual Studio
- **SQL Server Management Studio (SSMS)** - Database administration and query tool

### Methodology Framework:
- **CRISP-DM** - Cross-Industry Standard Process for Data Mining

---

## Author

**Faiyad Mahabub Tasin**
TP Number: TP077983
Cohort: APU2F2411CS(DA)
Course: CT122-3-2-BIS - Business Intelligence System
Institution: Asia Pacific University of Technology & Innovation (APU)
Lecturer: TS. Mohammad Namazee Bin Mohd Nizam

---

## Project Timeline

- **Hand Out Date**: May 2, 2025
- **Submission Date**: July 25, 2025
- **Project Duration**: ~3 months

---

## References

1. Chumbar, S. (2023, September 24). The CRISP-DM Process: A Comprehensive guide. Medium. https://medium.com/@shawn.chumbar/the-crisp-dm-process-a-comprehensive-guide-4d893aecb151

2. Definition — the Crisp-DM methodology. (n.d.). https://almirgouvea.github.io/The-Crisp-DM-Methodology/chapters/definition.html

3. Mercedes-Benz Group. (n.d.). The Board of Management of Mercedes-Benz Group AG. https://group.mercedes-benz.com/company/corporate-governance/board-of-management

4. Sharma, R. (2025, March 13). CRISP-DM explained: A proven data mining methodology. Udacity. https://www.udacity.com/blog/2025/03/crisp-dm-explained-a-proven-data-mining-methodology.html

---

## License

This project is an academic assignment submitted for educational purposes at Asia Pacific University. All rights reserved.

---

## Acknowledgments

- **AdventureWorks Sample Database** - Microsoft Corporation
- **Course Instructor** - TS. Mohammad Namazee Bin Mohd Nizam
- **Asia Pacific University** - For providing the learning platform and resources

---

## Contact & Support

For questions or clarifications about this project, please contact:
- **Student**: Faiyad Mahabub Tasin (TP077983)
- **Course**: CT122-3-2-BIS
- **Institution**: Asia Pacific University

---

**Note**: This README is part of an academic Business Intelligence project. The findings, recommendations, and analysis are based on the AdventureWorks sample dataset and are intended for educational purposes.

---

*Last Updated: February 16, 2026*
