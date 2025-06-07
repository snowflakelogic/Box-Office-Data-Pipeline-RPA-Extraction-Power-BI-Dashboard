# Box Office Mojo RPA Data Extraction

A UiPath RPA workflow for automated data extraction from Box Office Mojo's weekend box office data by country.

## 📋 Project Overview

This RPA solution automates the process of scraping box office data from Box Office Mojo's website, specifically targeting weekend box office performance data across different countries. The workflow extracts tabular data and exports it to CSV format for further analysis.
## 🖼️ Workflow Screenshot

![UiPath Workflow](RPA_UIPATH_DATA_EXTRACTION.PNG)

*Box Office Mojo RPA Data Extraction Workflow*

## 🎯 Features

- **Automated Web Navigation**: Opens and navigates to Box Office Mojo weekend data pages
- **Dynamic Data Extraction**: Extracts table data from multiple country-specific pages
- **Data Processing**: Processes and structures extracted data into a standardized format
- **CSV Export**: Automatically appends data to CSV files for easy analysis
- **Country-Specific Scraping**: Handles data extraction for multiple countries

## 🛠️ Technical Requirements

### Software Dependencies
- **UiPath Studio** (Latest version recommended)
- **UiPath Robot** for execution
- **Modern web browser** (Chrome/Edge recommended)

### UiPath Packages Required
- `UiPath.WebAPI.Activities`
- `UiPath.Excel.Activities`
- `UiPath.System.Activities`
- `UiPath.UIAutomation.Activities`

## 📁 Project Structure

```
BoxOfficeMojo_RPA/
├── Main.xaml                 # Main workflow file
├── Data/
│   ├── MOJO_ALL.csv    # Output CSV file
├── Screenshots/             # Workflow screenshots
└── README.md               # This file
```

## 🔧 Workflow Components

The UiPath workflow follows this simple sequence:

### Workflow Steps:
1. **Start** - Initialize the automation process
2. **Use Browser** - Opens browser and navigates to Box Office Mojo URL
3. **Extract Table** - Scrapes table data and stores in `ExtractedDataTable` variable
4. **Append to CSV** - Exports the `ExtractedDataTable` data to CSV file
5. **End** - Completes the automation process

### Key Activities:
- **Use Browser**: Browser automation for web navigation
- **Extract Table Data**: Data scraping activity for table extraction
- **Append to CSV**: File output activity for data export

## 🚀 Setup Instructions

### 1. Environment Setup
```bash
# Ensure UiPath Studio is installed
# Install required browser (Chrome recommended)
# Verify internet connectivity
```

### 2. Project Configuration
1. Clone or download the project files
2. Open `Main.xaml` in UiPath Studio
3. Update the target URL if needed
4. Configure output file path in the "Append to CSV" activity

### 3. Country List Setup
1. Create a list of countries to scrape
2. Update the workflow to iterate through country-specific URLs
3. Modify selectors if website structure changes

## ▶️ Execution Steps

### Manual Execution
1. Open UiPath Studio
2. Load the `Main.xaml` workflow
3. Click **Run** to start the automation
4. Monitor the browser automation process
5. Check the output CSV file for extracted data

### Scheduled Execution
1. Publish the workflow to UiPath Orchestrator
2. Create a scheduled job for regular data extraction
3. Set up error handling and notifications

## 📊 Data Output

### CSV Structure
The extracted data from Box Office Mojo tables is saved to CSV format with all scraped columns preserved.

### File Location
- **Default Path**: `Data/MOJO_ALL.csv`
- **Format**: CSV
- **Delimiter**: Comma (,)

## 🔍 Troubleshooting

### Common Issues

**Browser Not Opening**
- Verify browser installation
- Check UiPath browser extension
- Update browser drivers

**Data Not Extracting**
- Website structure may have changed
- Update CSS selectors in data scraping activity
- Check internet connectivity

**CSV File Errors**
- Verify file permissions
- Check available disk space
- Ensure output directory exists

### Error Handling
The workflow includes:
- Try-catch blocks for web automation
- Retry mechanisms for failed extractions
- Logging for debugging purposes

## 🔄 Maintenance

### Regular Updates Needed
- **Selector Maintenance**: Update selectors if website changes
- **URL Updates**: Monitor for URL structure changes
- **Data Validation**: Verify data quality and completeness

### Performance Optimization
- Implement delays for stable execution
- Use reliable selectors (avoid dynamic IDs)
- Add data validation checks

## 📈 Potential Enhancements

### Future Improvements
1. **Multi-Country Support**: Automated iteration through country lists
2. **Data Validation**: Quality checks for extracted data
3. **Database Integration**: Direct database storage option
4. **Email Notifications**: Success/failure email alerts
5. **Dashboard Integration**: Real-time data visualization

### Scalability Options
- **Parallel Processing**: Multiple country extractions simultaneously
- **Cloud Deployment**: UiPath Cloud Robot execution
- **API Integration**: Direct API calls where available

## 📝 Notes

- **Data Accuracy**: Box Office Mojo data updates regularly; ensure timely extraction
- **Rate Limiting**: Implement delays to avoid overwhelming the website
- **Legal Compliance**: Ensure scraping activities comply with website terms of service
- **Manual Updates**: Country names and specific data points may require manual verification

## 🤝 Contributing

To contribute to this project:
1. Fork the repository
2. Create a feature branch
3. Test thoroughly with sample data
4. Submit a pull request with detailed changes

## 📄 License

This project is for educational and research purposes. Ensure compliance with Box Office Mojo's terms of service and data usage policies.

---
Maintained by: snowflakelogic
