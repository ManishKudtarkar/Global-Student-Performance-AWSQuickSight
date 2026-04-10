# Global Student Performance & Lifestyle Analysis 🌍📊

An end-to-end AWS data pipeline designed to analyze and visualize lifestyle factors, AI tool adoption, and academic performance data for 10,000 students globally.

## 🏗️ Project Architecture

The following diagram illustrates the serverless workflow used to process and visualize the `global.csv` dataset:

```mermaid
graph TD
    A["Raw Data: global.csv"] -->|Upload| B("Amazon S3 Bucket")
    B -->|S3 Event / Manifest| C{"Amazon QuickSight"}
    C --> D["Data Transformation & SPICE"]
    D --> E["Dashboard: Student Insights"]
    
    subgraph Analysis_Modules
    E --> F["AI Usage vs GPA"]
    E --> G["Stress & Sleep Analysis"]
    E --> H["Global Demographic Trends"]
    end

    style B fill:#FF9900,stroke:#232F3E,stroke-width:2px
    style C fill:#3B48CC,stroke:#232F3E,stroke-width:2px
    style E fill:#118111,stroke:#232F3E,stroke-width:2px
