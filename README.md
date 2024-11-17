# sleep-analysis-project
This repository contains the MATLAB code which was used to analyze periodic rhythms (weekly and annual) in sleep duration and sensitivity to periodicity while accounting for age and gender. The project was conducted as part of a Master Thesis by Isaac Schrofer.

Overview
The primary aim of this project is to investigate whether:
-Weekly periodicity (e.g., weekday vs weekend) affects sleep duration.
-Annual periodicity (e.g., seasonal rhythms) impacts sleep duration.
-There is a measurable sensitivity to periodic rhythms in sleep duration that correlates with individual traits like age and gender.

Code Structure
Main Script
-Data Preparation:
  Loads participant-specific sleep data.
  Cleans and preprocesses data by handling missing values (e.g., replacing missing sleep durations by the participant's mean).
  Identifies valid participants with at least 365 days of sleep data. 
-Visualizations:
  Generates polar plots to visualize sleep duration over the week (Monday–Sunday) and year (January–December).
  Produces scatter plots and box plots for sensitivity analysis.
-Statistical Tests:
  Performs circular correlation to examine periodicity effects on sleep duration.
  Executes paired t-tests to compare weekday vs weekend sleep durations.
  Conducts regression analyses to evaluate sensitivity scores in relation to age and gender.

Output Folders
The code creates a structured directory for outputs:
/output: Main output folder.
/polarplots: Stores polar plots for individual participants.
/results: Saves .mat files for hypothesis test results (e.g., H1a, H1b, sensitivity analysis).
/visuals: Stores scatter plots, box plots, and combined visualizations.

Pre-requisites: MATLAB with the required Circular Statistics Toolbox (e.g., circ_corrcl for circular correlation).
Ensure your data is formatted as follows:
    Each participant has a struct named ContSleep_<participantID> with:
      dx: Array of sleep duration data (in hours or minutes) for each day.
      ddayutc: Corresponding date vector for each day in MATLAB datetime format.

Execution
1. Add your data files to the MATLAB workspace.
2. Make sure Gender and Age variables are replaced by real data
3. Change the ...
4. Run the script. It will:
      Preprocess the data.
      Generate and save visualizations.
      Perform statistical analyses and save the results.

Key Assumptions and Limitations
  -Sleep data must span at least 365 days for participants to be included in the analysis.
  -Missing sleep data (NaN values) is replaced with the participant’s mean sleep duration.
  -The gender variable is binary (1 = Male, 2 = Female).
  
Outputs
  Generated Files
  Polar Plots: Weekly and annual sleep duration plots for each participant.
  Results: .mat files with:
    - Weekday vs weekend sleep analysis (H1a).
    - Annual periodicity analysis (H1b).
    - Sensitivity scores for periodicity (H2).
    - Regression outputs (e.g., sensitivity vs age/gender).
    - Visuals: Combined plots for regression, sensitivity, and periodic effects.
    
! Important Notes !
 - Age Sensitivity Analysis: Sensitivity to periodicity is computed as the sum of absolute correlations for weekly and annual rhythms.
 - Custom Adjustments: Modify the script if your data structure differs (e.g., variable names or file paths).
 - Polar Plots: Ensure your data covers an entire week/year for meaningful circular plots.
 - Techniquely the analysis that do not entail annual data, but only weekday data can be run with the variable 'all_participants'   
   containing all participants. For simplicity this was not done here.
   
Example Outputs
-Visualization	Description
-Polar Plot (Week)	Shows sleep duration distributed over days of the week (Monday–Sunday).
-Polar Plot (Year)	Highlights sleep duration distributed over months (January–December).
-Scatter Plot (Sensitivity)	Visualizes sensitivity scores against age and gender.

Citation: If you use this code for your research, please credit Isaac Schrofer, Master Thesis Project (2024), Leiden University.
