## **Challenge: Imputing Missing Resource Usage Data with Custom Time Intervals**

### **Problem Statement:**

You are tasked with analyzing resource usage data from a supercomputer, recorded in the FRESCO data set. For each time stamp, this data set captures the following:
- Host ID
- Job ID
- Event type:
  - cpuuser: CPU user mode average percentage 
  - block: Data transfer rate to/from block devices 
  - memused: Total physical memory usage by the OS 
  - memused_minus_diskcache: Physical memory usage excluding caches 
  - gpu_usage: GPU active time average percentage (only for GPU jobs)
  - nfs: Data transfer rate over NFS mounts
- Value
- Units

However, the data time intervals are irregular. Certain time periods have data recorded every second, while others have gaps of several seconds between data points. 

Your goal is to develop a method to **impute the missing values** at a **specific time interval**, which will be provided. The challenge is to accurately fill in these gaps, ensuring a consistent time series for further analysis.

### **Objectives:**

1. **Data Resampling**:
   - Resample the data at the given time interval (e.g., 1 second, 5 seconds, etc.), filling in gaps where data is missing. The time interval will be provided during the challenge.

2. **Imputation Techniques**:
   - Use at least two different methods to fill the missing values. You can choose from techniques such as:
     - Forward/Backward Fill
     - Linear Interpolation
     - Spline Interpolation
     - Advanced methods like ARIMA or LSTM

3. **Evaluation of Imputation**:
   - Simulate missing data in a portion of the data set where the actual values are known. Then, apply your imputation techniques to fill these gaps and compare the filled-in values with the actual data.
   - Compute a **score** to measure the accuracy of your imputations using the **Root Mean Squared Error (RMSE)**.

4. **Handling Larger Gaps**:
   - When faced with larger gaps (e.g., 10+ seconds), simple interpolation may not suffice. Explore an advanced time-series forecasting model, such as ARIMA or LSTM, to handle these gaps. Evaluate how well this method performs compared to simpler approaches.

### **Expected Deliverables**:

1. **Code Implementation**:
   - Python code that resamples the data set at the provided interval and imputes missing values using at least two different techniques.

2. **Score Calculation**:
   - A function or method that calculates the **RMSE** to evaluate the accuracy of the imputed values compared to known values.

3. **Visualization**:
   - Visual plots showing the original data, the gaps, and how each method fills them. Include visual comparisons between imputed and actual data for artificially introduced gaps.

4. **Report**:
   - A summary report explaining your methods, the strengths and weaknesses of each, and the results of your evaluations. Include your RMSE to demonstrate how well each imputation method performed.

### **Guidelines**:

- The time interval for resampling will be provided when the challenge starts. It will be consistent across all data sets you work with.
- You can use libraries such as **Pandas**, **Polars**, **Statsmodels**, and **TensorFlow/Keras** for the machine learning part.
- Clearly document your code to explain your thought process and allow others to test different imputation methods.

### **Evaluation Criteria**:

- **Imputation Accuracy (70%)**:
   - Participants will be ranked based on the **Root Mean Squared Error (RMSE)**. The lower the RMSE, the better the performance. This score will be calculated by comparing the imputed values against the actual values in the data set where gaps were artificially introduced.

- **Methodology and Creativity (20%)**:
   - Teams that apply more advanced techniques (such as hybrid approaches combining simpler and advanced models) or come up with novel methods will receive higher marks for creativity and methodology.

- **Efficiency and Documentation (10%)**:
   - Solutions that are well-documented, computationally efficient, and modular will receive additional points.

### **data set**:
- You will be provided with the data set containing resource usage metrics, with irregular timestamps and missing values. The exact time interval for resampling will be provided at the start of the challenge.
