Wind Turbine Anomaly Detection and Power Curve Analysis
Overview
This project processes wind turbine data to detect anomalies, generate power curves, and produce comprehensive reports for each site. The data consists of wind speed and turbine production values, which are used to create machine learning models (PKL files) for anomaly detection. For each turbine at each site, power curve charts are generated and combined into PDF reports.

The project involves:

Processing turbine data for wind speed and production values.
Applying machine learning models to detect anomalies.
Creating power curve charts for each turbine.
Generating a PDF report for each site with all power curves.
Combining anomaly points with normal data for further analysis.

Project Structure
.
├── OneVarDetection
│   ├── models/                 # Machine learning models (PKL files) for each turbine model
│   ├── output_png/             # PNG charts generated for each turbine
│   ├── output_png_merged/      # Combined PNG charts for each site
│   ├── Model info.xlsx         # Excel file containing site information, model names, and maximum power for each site
├── README.md                   # Project documentation
└── main.py                     # Main script for anomaly detection, power curve generation, and report creation


To install the required libraries, run:
pip install -r requirements.txt


Features
1. Data Processing
The script reads turbine data from various sites and applies filtering and adjustments to clean and preprocess the data for anomaly detection.

2. Anomaly Detection
A machine learning model is applied to the cleaned data to detect anomalies in power curves based on variables such as WindSpeed and RotorSpeed. Anomalies are detected using pre-trained models stored in PKL files, and thresholds are calculated using interquartile ranges (IQR).

3. Power Curve Generation
Power curve charts are generated using seaborn and matplotlib, displaying the relationship between wind speed and turbine power output. Anomalies are highlighted in the charts.

4. Report Generation
The script creates a PNG chart for each turbine at a site. These charts are combined into a single image and saved as a merged PNG file. A PDF report is generated for each site, containing all power curves.

Usage
Data Input
The turbine data is retrieved using the Bazefield_Measurement_Requesting_Library which requests turbine information and measurements for each site.

Running the Script
To process data, apply anomaly detection, generate charts, and create PDF reports for all turbines at all sites, run:


python main.py
Output
Individual power curve charts for each turbine are saved as PNG files in the output_png/ folder.
A merged PNG file for each site is saved in the output_png_merged/ folder.
A PDF report containing all power curves for a site is generated.
Machine Learning Models
The machine learning models are stored as PKL files in the models/ folder. These models are applied to the corresponding turbines based on their site and model type.

To add new models for different turbines, place the PKL files in the models/ folder, and ensure they are correctly referenced in the Model info.xlsx file.

Example
For example, if you want to process a site with a single turbine model, place the model PKL file in the models/ folder and the corresponding site data in the input folder. The script will apply the model, generate power curves, detect anomalies, and create a PDF report.

Conclusion
This project provides a complete pipeline for anomaly detection and power curve analysis of wind turbines, generating visual reports for each site. By integrating machine learning models, it identifies underperforming turbines and allows for further investigation into the causes of power loss or operational inefficiencies.
