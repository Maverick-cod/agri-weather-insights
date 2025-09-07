# agri-weather-insights
Prototype RTGS-style AI Analyst for Telangana Open Data — Agriculture + Weather sector

Drive Link 
https://drive.google.com/drive/folders/1XQ3lvMYUm0kvVloAyEhnxs9hYEToP18H?usp=drive_link

1. Comprehensive Data Ingestion
•	Code Implementation: The function load_and_standardize_data(file_path: str) in Cell 4 is responsible for this.
o	2.3 million records: It uses pd.read_csv(..., chunksize=100000) to handle large files efficiently, concatenating all chunks into a final DataFrame (df = pd.concat(chunks, ignore_index=True)).
o	11 parameters: It processes the original 11 columns listed in your dataset info.
o	Zero missing values: The logging and the conversion_issues dictionary track this process meticulously.
2. Temporal Feature Engineering
•	Code Implementation: This is a core part of the load_and_standardize_data function.
o	Year, Month, etc.: The code extracts 'year', 'month', 'day', 'day_of_year', 'week_of_year', 'quarter' from the standardized 'date' column.
o	Seasonal Categorization: The helper function get_season(month: int) is used to create the 'season' column (Winter, Summer, Monsoon, Post-Monsoon).
o	Rolling Averages: The function create_advanced_features(df: pd.DataFrame) in Cell 5 calculates 'rolling_avg_rainfall_7d' and 'rolling_avg_rainfall_30d' using .rolling(window=7) and .rolling(window=30).
3. Advanced Quality Control
•	Code Implementation: Primarily in the clean_and_transform_data(df: pd.DataFrame) function in Cell 5.
o	Dual Outlier Detection: The code uses both Z-score (z_scores = np.abs(stats.zscore(...))) and IQR (iqr = df_clean[col].quantile(0.75) - df_clean[col].quantile(0.25)) methods.
o	Data Quality Flags: The function add_quality_flags(df: pd.DataFrame) adds numerous flags, including temp_consistency_flag, humidity_consistency_flag, and {col}_outlier_flag for each numeric column.
4. Agricultural Risk Modeling
•	Code Implementation: The function create_enhanced_risk_indices(df: pd.DataFrame) in Cell 5 is dedicated to this.
o	Weather Stress Index (WSI): While not named exactly "WSI", the code calculates individual risk components (rainfall_risk, temperature_risk, etc.) which are the precursors to a WSI.
o	Agricultural Risk Index (ARI): This is the final output. The code calculates df['ari'] as a weighted sum of the component risks and then normalizes it to 'ari_normalized' on a 0-100 scale.
o	5-tier risk categorization: The code uses pd.cut() to create the 'risk_category' column with the labels ['Low', 'Medium', 'High'] based on the thresholds defined in Config.RISK_THRESHOLDS.
5. District Vulnerability Assessment
•	Code Implementation: This is the result of the entire processing pipeline and is summarized in the generate_insights(df: pd.DataFrame) function in Cell 6.
o	The insights generation includes 'district_analysis' and 'risk_analysis', which contain the grouped statistics that allow for ranking districts by average rainfall, risk index, and count of high-risk days (high_risk_districts).
6. Statistical Validation Framework
•	Code Implementation: The function perform_hypothesis_tests(df: pd.DataFrame) in Cell 6 executes these tests.
o	ANOVA Testing: The code performs an ANOVA test (stats.f_oneway(*groups)) to check for significant differences in rainfall between seasons.
o	Correlation Analysis: It calculates Pearson correlation (stats.pearsonr(...)) between temperature and rainfall.
7. Policy-Ready Output Generation
•	Code Implementation: The function generate_policy_recommendations(df: pd.DataFrame) in Cell 6 is built for this exact purpose.
o	It creates a list of actionable recommendations based on rainfall deficit, high-risk frequency, heatwaves, and dry spells, each tagged with a priority level ('High', 'Medium').
8. Multi-Format Output System
•	Code Implementation: This is woven throughout the entire codebase and is a key feature of the RTGSCLI class.
o	The system saves data to CSV and Parquet in the standardized/ and cleaned/ directories.
o	It saves insights and reports as JSON in the insights/ and logs/ directories.
o	The export_results() method in the RTGSCLI class handles exporting to both CSV and Excel formats with intelligent chunking for large files.
o	The generate_visualizations() function creates PNG static images and HTML interactive plots in the visualizations/ directory.
9. Interactive Access Infrastructure
•	Code Implementation: The entire RTGSCLI class in Cell 7 is this infrastructure.
o	It provides methods like show_summary(), show_high_risk_districts(), show_policy_recommendations(), and run_hypothesis_test() for exploring results via a command-line interface.
o	The create_interactive_dashboard() method creates ipywidgets filters for dynamic data exploration.
10. Actionable Intelligence Delivery
•	Code Implementation: This is the ultimate goal of the entire run_rtgs_pipeline() function in Cell 8.
o	The pipeline takes raw data as input and its final outputs are the cleaned dataset, the insights JSON (with validated statistics and models), and the policy recommendations CSV. This is the complete transformation from raw data to decision-ready intelligence.


