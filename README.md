# Global Student Performance & Lifestyle Analysis 🌍📊

An end-to-end AWS data pipeline designed to analyze and visualize the lifestyle factors, AI tool adoption, and academic performance of 10,000 students globally.

## 🏗️ Project Architecture

The following diagram shows the serverless workflow used to process the `global.csv` dataset:

```mermaid
graph TD
    A[Raw Data: global.csv] -->|Upload| B(Amazon S3 Bucket)
    B -->|S3 Event / Manifest| C{Amazon QuickSight}
    C --> D[Data Transformation & SPICE]
    D --> E[Dashboard: Student Insights]
    
    subgraph Analysis_Modules
    E --> F[AI Usage vs GPA]
    E --> G[Stress & Sleep Analysis]
    E --> H[Global Demographic Trends]
    end

    style B fill:#FF9900,stroke:#232F3E,stroke-width:2px
    style C fill:#3B48CC,stroke:#232F3E,stroke-width:2px
    style E fill:#118111,stroke:#232F3E,stroke-width:2px

🚀 Overview
The goal of this project was to identify the key drivers of student success in a modern, AI-integrated learning environment. By using Amazon S3 and Amazon QuickSight, I built a dashboard that processes 10,000 records to reveal patterns between mental health, technology use, and academic results.

🛠️ Tech Stack
Cloud Provider: AWS

Storage: Amazon S3 (Object Storage)

Business Intelligence: Amazon QuickSight

Data Source: global.csv (10,000 rows, 27 features)

📈 Key Insights Explored
AI Integration: How many hours students spend on tools like Claude and Gemini and its impact on their final exam scores.

Health vs. Grades: The relationship between sleep hours, exercise, and GPA.

Stress Factors: Visualizing the link between internet quality, gaming hours, and reported mental stress levels.

📖 Implementation Steps
S3 Setup: Created an S3 bucket and uploaded global.csv.

Manifest Creation: Authored a manifest.json file to tell QuickSight where to find the data.

QuickSight Connection: Configured permissions to allow QuickSight to read from the S3 bucket.

Data Modeling: Identified and formatted fields (converting final_exam_score to integers and GPA to decimals).

Dashboard Design: Created a series of visualizations including Heatmaps, Bar Charts, and Scatter Plots.

📂 Repository Contents
data/manifest.json: Configuration for QuickSight.

global.csv: The primary dataset used for analysis.

screenshots/: Visuals of the finalized AWS QuickSight dashboard.

🌟 Acknowledgments
Project architecture inspired by AWS best practices for serverless data visualization.
