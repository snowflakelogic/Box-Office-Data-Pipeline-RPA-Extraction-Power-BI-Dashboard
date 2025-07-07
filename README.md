# 🎬 Integrated Streaming & Box Office Analytics Dashboard

A comprehensive multi-platform analytics solution that combines theatrical box office performance, streaming platform metrics, and public search interest to provide unprecedented insights into movie performance across the modern entertainment ecosystem.
## 📷 Sample Dashboard Visuals

### 🎯 Main Dashboard
![Cross-Platform Performance](Screenshot%202025-06-22%20200814.png)

### 🎭 OTT Platforms (Netflix, Amazon Prime Video)
![Genre Comparison](Screenshot%202025-06-22%20200820.png)

### 🌍 Box Office Collection (Box-Office Mojo + OMDB API + Google Trends)
![Geo Interest Map](Screenshot%202025-06-22%20200832.png)


## 📊 Project Overview

This advanced analytics dashboard integrates data from multiple sources to deliver deep insights into:
- **Cross-Platform Performance**: How movies perform in theaters vs streaming platforms
- **Genre Preference Analysis**: Rating patterns and categorization across Netflix and Amazon Prime
- **Public Interest Correlation**: Search trends and their relationship to movie performance
- **Unified Analytics View**: Complete movie lifecycle analysis from theater to streaming

## 🎯 Key Features

### 🎭 Multi-Platform Data Integration
- **Theatrical Performance**: Box office data with custom temporal modeling
- **Streaming Platforms**: Netflix and Amazon Prime content analysis with IMDB ratings
- **Search Trends**: Google Trends integration for 20+ strategically selected movies
- **Geographic Analysis**: Regional interest patterns and global appeal metrics

### 🔄 Advanced Data Processing
- **Automated RPA Pipeline**: UiPath workflow for Box Office Mojo data extraction
- **OMDB API Integration**: Enhanced movie metadata including runtime, genre, and budget
- **Comprehensive Data Cleaning**: Python/Pandas preprocessing for streaming datasets
- **Genre Explosion**: Granular analysis with expanded genre categorization

### 📈 Interactive Analytics
- **Dynamic Filtering**: Movie-based slicers that filter across all connected datasets
- **Temporal Analysis**: Time-series search trends (May 16 - June 16 analysis period)
- **Cross-Platform Correlation**: Relationship analysis between box office, streaming ratings, and search interest
- **Geographic Visualization**: Regional preference mapping and international appeal insights

## 🛠️ Technical Architecture

### Data Sources
- **Box Office Mojo**: Automated RPA extraction using UiPath
- **Netflix Dataset**: Comprehensive streaming catalog with ratings
- **Amazon Prime Dataset**: Complete movie and TV show metadata
- **Google Trends**: Geo-interest and time-series search data
- **OMDB API**: Enhanced movie metadata integration

### Technology Stack
- **RPA Automation**: UiPath Studio for web scraping
- **Data Processing**: Python (Pandas, NumPy) for cleaning and transformation
- **Visualization**: Power BI with custom DAX measures
- **API Integration**: OMDB API for movie metadata enrichment

### Data Architecture
```
📦 Data Relationships
├── Theater Data ↔ Month Table (1:Many) - Chronological analysis
├── Movie Table ↔ Geo-Interest Dataset (1:Many) - Regional patterns
├── Movie Table ↔ Time Series Dataset (1:Many) - Temporal trends
└── Streaming Data ↔ Genre Explosion (1:Many) - Granular categorization
```

## 🔧 RPA Automation Workflow

### UiPath Box Office Mojo Extraction
![UiPath Workflow](RPA_UIPATH_DATA_EXTRACTION.PNG)

**Automated Process:**
1. **Data Extraction**: Scrapes weekend box office data by country
2. **OMDB Integration**: Enriches data with runtime, genre, IMDb ID, and budget
3. **Data Preprocessing**: Comprehensive cleaning and standardization
4. **Export**: Analysis-ready CSV output for Power BI integration

### Key RPA Features
- **Multi-Country Scraping**: Automated extraction across different regions
- **Dynamic Navigation**: Handles website structure changes
- **Data Validation**: Quality checks and preprocessing
- **API Integration**: Seamless OMDB metadata enrichment

## 📊 Data Processing Pipeline

### Streaming Data Cleaning (Netflix & Amazon Prime)
```python
# Data Quality Assessment
- Netflix: 731 missing titles, 1820 missing ratings resolved
- Amazon Prime: 1,777 missing titles, 9,205 missing ratings cleaned

# Processing Steps
1. Remove entries without titles (primary identifiers)
2. Eliminate records without IMDB ratings
3. Drop entries lacking genre information
4. Genre explosion: Split comma-separated genres into individual rows
5. Data validation: Ensure complete data integrity
```

### Enhanced Movie Selection Strategy
- **Geographic Scope**: Selected movies released in 4+ countries
- **Performance Range**: From minimum to maximum international coverage
- **Trend Analysis**: Manual collection of geo-interest and time-series data

## 📈 Key Insights & Analytics

### Cross-Platform Performance Metrics
- **Rating Correlation**: IMDB ratings distribution across platforms
- **Genre Performance**: Top-performing genres by platform
- **Content Volume**: Comparative catalog analysis

### Geographic & Temporal Intelligence
- **Regional Preferences**: Country-specific movie interest patterns
- **Search Evolution**: Temporal trend analysis and spike correlation
- **Release Impact**: Box office vs streaming performance relationships

### Business Intelligence Applications
- **Content Strategy**: Genre performance insights for creators
- **Acquisition Decisions**: Data-driven content licensing
- **Marketing Optimization**: Geographic targeting and timing strategies

## 🚀 Setup & Installation

### Prerequisites
```bash
# Software Requirements
- UiPath Studio (Latest version)
- Python 3.8+
- Power BI Desktop
- OMDB API Key
```

### Python Dependencies
```bash
pip install pandas numpy requests tqdm
```

### UiPath Packages
- `UiPath.WebAPI.Activities`
- `UiPath.Excel.Activities`
- `UiPath.System.Activities`
- `UiPath.UIAutomation.Activities`

## 📁 Project Structure

```
StreamingAnalytics_Dashboard/
├── 📊 Data/
│   ├── CLEANED_NETFLIX.csv
│   ├── CLEANED_AMAZON.csv
│   ├── EXPLODED_NETFLIX.csv
│   ├── EXPLODED_AMAZON.csv
├── 🤖 RPA_Automation/
│   ├── Main.xaml (UiPath Workflow)
│   ├── data_preprocessing.py
│   └── omdb_integration.py
|   └── GoogleTrends_Data/ 
├── 📈 PowerBI_Dashboard/
│   ├── StreamingAnalytics.pbix
│   └── DAX_Measures/
├── 🔧 Data_Processing/
│   └── AMAZON_NETFLIX_CLEANING_DATASET.ipynb
└── 📋 Documentation/
```

## 💼 Business Value

###🌍 For Content Creators
- **Genre Strategy**: Platform-specific performance insights
- **Release Optimization**: Data-driven timing and distribution decisions
- **Audience Targeting**: Geographic and demographic intelligence

###🎬 For Streaming Platforms
- **Content Acquisition**: Evidence-based licensing strategies
- **Competitive Analysis**: Cross-platform performance benchmarking
- **User Engagement**: Predictive analytics for viewer behavior

###💰 Revenue Growth Opportunities
- **Precision Marketing**: Enables regional and time-specific ad targeting using search interest data.
- **Smarter Budget Allocation**: Informs marketing spend and promotional timing for maximum ROI.
- **Viewer Engagement**: Streaming platforms can emphasize genres that drive higher engagement and ratings.

###📊 For Market Analysts
- **Industry Trends**: Comprehensive entertainment ecosystem view
- **Consumer Behavior**: Multi-dimensional audience analysis
- **Performance Forecasting**: Advanced predictive modeling foundation

### 🧠 Operational Efficiency
- **Automated Data Workflows**: Saves analyst time using RPA for scraping and preprocessing, enabling regular refreshes without manual work.
- **Unified Analytics Platform**: Combines multiple datasets into a single, interactive Power BI view for quicker insight generation.

  
## 📊 Dashboard Highlights

- **Interactive Movie Selection**: Dynamic filtering across all data sources
- **Multi-Platform Comparison**: Side-by-side performance analysis
- **Geographic Heat Maps**: Regional interest visualization
- **Temporal Trend Lines**: Search pattern evolution tracking
- **Genre Performance Matrix**: Cross-platform genre analysis

## 🔮 Future Enhancements

- **Real-time Data Integration**: Live streaming platform APIs
- **Social Media Sentiment**: Twitter/Reddit sentiment analysis integration
- **Predictive Modeling**: ML models for performance forecasting
- **International Expansion**: Additional streaming platforms and regions


## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request or open an Issue for discussion.

## 📞 Contact
For questions or collaboration opportunities, feel free to reach out!

LinkedIn: [snowflakelogic](https://www.linkedin.com/in/nikshita-c-75370a292/)

---
*Built with ❤️ for the entertainment analytics community*

## 🚀 Setup Instructions

### 1. Environment Setup
```bash
# Install UiPath Studio
# Install Python and required packages
pip install pandas numpy requests tqdm

# Set up browser automation
# Verify internet connectivity
```

### 2. API Configuration
1. Register for OMDB API key at http://www.omdbapi.com/
2. Create `Config/config.json`:
```json
{
    "omdb_api_key": "your_api_key_here",
    "output_path": "Data/",
    "delay_between_requests": 1
}
```

### 3. Project Configuration
1. Clone or download the project files
2. Open `Main.xaml` in UiPath Studio
3. Update the target URL if needed
4. Configure output file paths
5. Set up Python script paths in UiPath workflow

## ▶️ Execution Steps

### Complete Pipeline Execution
1. **Run RPA Extraction**:
   - Open UiPath Studio
   - Load `Main.xaml` workflow
   - Execute data extraction process

2. **Run Data Processing**:
   ```bash
   python Scripts/data_preprocessing.py
   ```

3. **Verify Output**:
   - Check `processed_data.csv` for enriched dataset
   - Validate data quality and completeness

### Automated Execution
1. Create batch script combining RPA and Python processing
2. Schedule via UiPath Orchestrator or system scheduler
3. Set up monitoring and error notifications

## 📊 Data Output

### Enhanced Dataset Structure
The processed dataset includes:

#### Original Box Office Data
- Movie titles, rankings, revenue figures
- Weekend performance metrics
- Country-specific data

#### OMDB Enriched Data
- **OMDB_Runtime**: Movie duration in minutes
- **OMDB_Genre**: Movie genres (comma-separated)
- **OMDB_imdbID**: IMDb identifier for cross-referencing
- **OMDB_Budget**: Production budget information

#### Processed Fields
- **Standardized Dates**: YYYY-MM-DD format
- **Numeric Values**: Clean float representations of percentages and currency
- **Quality Indicators**: Data completeness and validation flags

### File Outputs
- **Raw Data**: `Data/MOJO_ALL.csv`
- **Processed Data**: `Data/processed_data.csv`
- **Processing Log**: `Data/processing_log.txt`

## 🔍 Troubleshooting

### RPA Issues
**Browser Not Opening**
- Verify browser installation and UiPath extensions
- Update browser drivers

**Data Not Extracting**
- Check website structure changes
- Update CSS selectors

### API Issues
**OMDB API Errors**
- Verify API key validity
- Check rate limiting (1000 requests/day for free tier)
- Implement retry mechanisms for failed requests

**Data Processing Errors**
- Check Python dependencies
- Verify data format consistency
- Review error logs for specific issues

### Performance Optimization
- Implement caching for OMDB requests
- Use batch processing for large datasets
- Add progress tracking for long-running operations

## Internship Project
Data Analytics Intern at [AIExecute](https://aiexecute.in/) | Mentored by [Dev Karprasad](https://www.linkedin.com/in/devkarprasad/)

## 🤝 Contributing

### Development Guidelines
1. Fork the repository
2. Create feature branch for new functionality
3. Test with sample datasets
4. Document API changes and new features
5. Submit pull request with comprehensive testing

## 📄 License & Compliance

This project is for educational and research purposes. Ensure compliance with:
- Box Office Mojo's terms of service
- OMDB API usage policies
- Data privacy regulations
- Fair use guidelines for commercial applications

---

**Maintained by**: snowflakelogic  
**Last Updated**: June 2025  
**Version**: 3.0 - Enhanced with Dashboard Building
