# Box Office Mojo RPA Data Extraction And Power BI Dashboard

A comprehensive UiPath RPA workflow for automated data extraction from Box Office Mojo's weekend box office data by country, enhanced with OMDB API integration for enriched movie metadata and advanced data preprocessing.

## 📋 Project Overview

This RPA solution automates the complete data pipeline for box office analytics:
1. **Data Extraction**: Scrapes box office data from Box Office Mojo's website
2. **Data Enrichment**: Integrates with OMDB API to fetch additional movie metadata
3. **Data Processing**: Comprehensive preprocessing and cleaning for analysis-ready datasets
4. **Export & Visualization**: Outputs clean data for Power BI dashboard integration

## 🖼️ Workflow Screenshot

![UiPath Workflow](RPA_UIPATH_DATA_EXTRACTION.PNG)

*Box Office Mojo RPA Data Extraction Workflow*

## 🎯 Features

### Core RPA Features
- **Automated Web Navigation**: Opens and navigates to Box Office Mojo weekend data pages
- **Dynamic Data Extraction**: Extracts table data from multiple country-specific pages
- **Country-Specific Scraping**: Handles data extraction for multiple countries

### Enhanced Data Processing
- **OMDB API Integration**: Enriches data with runtime, genre, IMDb ID, and budget information
- **Date Standardization**: Converts dates to YYYY-MM-DD format for compatibility
- **Data Cleaning**: Handles missing values, percentage conversions, and currency formatting
- **Data Validation**: Quality checks and preprocessing for analysis readiness

### Output & Analytics
- **CSV Export**: Automatically appends processed data to CSV files
- **Power BI Ready**: Structured data optimized for dashboard creation
- **Multi-format Support**: Flexible export options for various analytics tools

## 🛠️ Technical Requirements

### Software Dependencies
- **UiPath Studio** (Latest version recommended)
- **UiPath Robot** for execution
- **Modern web browser** (Chrome/Edge recommended)
- **Python** (for OMDB API integration and data preprocessing)

### UiPath Packages Required
- `UiPath.WebAPI.Activities`
- `UiPath.Excel.Activities`
- `UiPath.System.Activities`
- `UiPath.UIAutomation.Activities`

### Python Dependencies
```python
pip install pandas numpy requests tqdm
```

### API Requirements
- **OMDB API Key**: Register at [OMDB API](http://www.omdbapi.com/) for movie metadata access

## 📁 Project Structure

```
BoxOfficeMojo_RPA/
├── Main.xaml                 # Main UiPath workflow file
├── Data/
│   ├── MOJO_ALL.csv         # Raw extracted data
│   ├── processed_data.csv   # Cleaned and enriched data
├── Scripts/
│   ├── data_preprocessing.py # Data cleaning and OMDB integration
│   ├── omdb_api.py          # OMDB API helper functions
├── Screenshots/             # Workflow screenshots
├── Config/
│   ├── config.json          # API keys and configuration
└── README.md               # This file
```

## 🔧 Complete Workflow Process

### Phase 1: RPA Data Extraction
1. **Start** - Initialize the automation process
2. **Use Browser** - Opens browser and navigates to Box Office Mojo URL
3. **Extract Table** - Scrapes table data and stores in `ExtractedDataTable` variable
4. **Append to CSV** - Exports the raw data to CSV file

### Phase 2: Data Preprocessing
1. **Date Formatting** - Standardize dates to YYYY-MM-DD format
2. **Basic Cleaning** - Remove unnecessary characters and format consistency
3. **Data Validation** - Check for data integrity and completeness

### Phase 3: OMDB API Integration
1. **API Setup** - Configure OMDB API credentials
2. **Movie Metadata Extraction** - Fetch additional data for each movie:
   ```python
   df[['OMDB_Runtime', 'OMDB_Genre', 'OMDB_imdbID', 'OMDB_Budget']] = df['#1 Release'].progress_apply(fetch_omdb_data)
   ```
3. **Data Merging** - Integrate OMDB data with Box Office Mojo dataset

### Phase 4: Advanced Data Processing
1. **Column Management** - Drop unnecessary columns
2. **Missing Value Handling** - Apply appropriate imputation techniques
3. **Data Type Conversion**:
   - Convert percentage values to float
   - Convert currency values to float
   - Standardize numeric formats
4. **Final Validation** - Ensure data quality for analytics

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

## 📈 Analytics Integration

### Power BI Dashboard Features
The processed data supports:
- **Revenue Trends**: Time-series analysis of box office performance
- **Genre Analysis**: Performance breakdown by movie genres
- **Budget vs. Revenue**: ROI analysis using OMDB budget data
- **Geographic Performance**: Country-wise box office comparison
- **Runtime Impact**: Analysis of movie duration vs. performance

### Dashboard Components
1. **Executive Summary**: Key metrics and KPIs
2. **Trend Analysis**: Historical performance visualization
3. **Comparative Analysis**: Movie and genre comparisons
4. **Geographic Insights**: Regional performance mapping

## 🔄 Maintenance & Updates

### Regular Maintenance
- **API Key Management**: Monitor OMDB API usage limits
- **Selector Updates**: Maintain web scraping reliability
- **Data Quality Monitoring**: Regular validation checks
- **Performance Optimization**: Monitor processing times

### Data Quality Assurance
- Automated data validation rules
- Missing value monitoring
- Outlier detection and handling
- Cross-reference validation with external sources

## 📝 Future Enhancements

### Planned Improvements
1. **Additional APIs**: Integration with TMDb, Rotten Tomatoes
2. **Real-time Processing**: Live data streaming capabilities
3. **Machine Learning**: Predictive analytics for box office performance
4. **Advanced Visualization**: Interactive dashboard components
5. **Cloud Integration**: Azure/AWS deployment options

### Scalability Considerations
- Database integration for large datasets
- Distributed processing for multiple countries
- API rate limiting and optimization
- Error recovery and resilience mechanisms

## 🤝 Contributing

### Development Guidelines
1. Fork the repository
2. Create feature branch for new functionality
3. Test with sample datasets
4. Document API changes and new features
5. Submit pull request with comprehensive testing

### Code Standards
- Follow PEP 8 for Python code
- Include error handling and logging
- Add unit tests for new functions
- Update documentation for changes

## 📄 License & Compliance

This project is for educational and research purposes. Ensure compliance with:
- Box Office Mojo's terms of service
- OMDB API usage policies
- Data privacy regulations
- Fair use guidelines for commercial applications

---

**Maintained by**: snowflakelogic  
**Last Updated**: June 2025  
**Version**: 2.0 - Enhanced with OMDB Integration
