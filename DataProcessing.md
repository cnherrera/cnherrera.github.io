---
layout: subpages2
title: BIG-MAP - WP5 - big data
description: Data processing
---
This platform is designed specifically for scientists, not necessarily experts in big data handing and analysis, aiming to assist you in your research journey and help you better exploit your data.

Data processing and analysis should always be tailored to the nature of the data at hand. In this context, we delve into three essential aspects of effectively managing both extensive datasets and low-quality (bad) data, all while offering practical examples and valuable tips. 


# 1. Scripting and optimizing scripts

In big data analysis, scripting with languages like Python is essential, thanks to its rich libraries. With numerous datasets to handle, scripting allows you to automate tasks across all datasets, saving you time and ensuring consistency in your analysis. The beauty of scripted algorithms lies in their adaptability; modifications can be made easily to meet changing data needs. Each step of your analysis process is meticulously documented, creating a robust framework that can be effortlessly applied to different datasets. 

We'll explore three key aspects to optimize your scripts and data analysis ahead.

### a. Parallel processing for uncorrelated data

Parallel processing is a good approach to optimize scripts. This implies breaking large datasets into smaller batches for simultaneous analysis. This approach boosts speed and efficiency, providing quicker insights. Ensure it's applied to independent datasets, as interdependencies may lead to bottlenecks. Various libraries, like Python's multiprocessing, distribute tasks across processors or machine clusters, maximizing computational power and reducing processing times.

{::options parse_block_html="true" /}
<details><summary markdown="span">**Press for an example of parallel processing**</summary>
```python
import numpy as np
import multiprocessing
from scipy.optimize import curve_fit

# Define a Pseudo-Voigt function
def pseudo_Voigt(x, A, x0, sigma, eta):
gaussian=(1-eta)*(A/(sigma*np.sqrt(2*np.pi)))*np.exp(-((x-x0)/(sigma*np.sqrt(2)))**2)
    lorentzian = eta * (A / (np.pi * (sigma**2 + (x - x0)**2)))
    return gaussian + lorentzian

def my_process(data):  
    # Initial guess
    initial_guess = [1.0, 5.0, 1.0, 0.5]

 # Function to be applied to data 
    try:
        params, _ = curve_fit(pseudo_Voigt, x, y, p0=initial_guess)
        return params
    except Exception as e:
        return None

# Reading the amount of available CPUs to be used
num_processes = multiprocessing.cpu_count()
# Initiating the pool
pool = multiprocessing.Pool(processes=num_processes)
# Apply my_process to a list of spectra.
processed_data = pool.map(my_process, spectra_list)

   

```
</details>
{::options parse_block_html="false" /}


### b. Object-Oriented Programming (OOP)

OOP offers organized, reusable code, making it easier to understand. OOP involves creating objects representing data structures or processing steps, each with unique attributes and methods. For instance, objects can be designed to load data, clean it, or run analyses.

{::options parse_block_html="true" /}
<details><summary markdown="span">**Press for an example of OOP**</summary>

We illustrate OOP with an example for efficient spectral data analysis, featuring general objects for loading and plotting data. Two more objects, XPS and XRD, inherit functionalities from the general ones, streamlining data loading and plotting. Each object has technique-specific analysis methods, promoting shared algorithms across diverse data analysis methods.

```python
import csv
import matplotlib.pyplot as plt

class Load:  # Create Load object.
    def __init__(self, data_file):
        self.data_file = data_file
        self.data = None
    
    def load_data(self): # create attribute to load data
        with open(self.data_file, 'r') as file:
            csv_reader = csv.reader(file)
            self.data = [row for row in csv_reader]

class Plot: # Create Plot object.
    def __init__(self, data, x_axis, y_axis):
        self.data = data
        self.x_axis = x_axis
        self.y_axis = y_axis
    
    def plot(self):
        x_values = [float(row[0]) for row in self.data]  # Assuming the x-values are in the first column
        y_values = [float(row[1]) for row in self.data]  # Assuming the y-values are in the second column
        plt.figure(figsize=(8, 6))
        plt.plot(x_values, y_values)
        plt.xlabel(self.x_axis)
        plt.ylabel(self.y_axis)
        plt.title("Data Plot")
        plt.show()

class XPS(Load, Plot): # XPS object to perform data analysis to XPS data. It inheritates the Load and Plot objects defined above.
    def __init__(self, data_file):
        super().__init__(data_file)
    
    def analyze(self):
        print(f"Performing XPS analysis on data: {self.data_file}")
        x_axis = "Binding Energy (eV)"
        y_axis = "Intensity"
        self.load_data()
        #### do data analysis
           analyzed_data = self.calculate_mean_intensity()
        return analyzed_data  # Return the analyzed data

def calculate_mean_intensity(self):
           # Example: Calculate the mean intensity
           intensity_values = [float(row[1]) for row in self.data]
           mean_intensity = sum(intensity_values) / len(intensity_values)
           return mean_intensity

class XPS(Load, Plot): # XPS object to perform data analysis to XPS data. It inheritates the Load and Plot objects defined above.
    def __init__(self, data_file):
        super().__init__(data_file)
    
    def analyze(self):
        print(f"Performing XPS analysis on data: {self.data_file}")
        x_axis = "Binding Energy (eV)"
        y_axis = "Intensity"
        self.load_data()
        #### do data analysis
           analyzed_data = self.calculate_mean_intensity()
        return analyzed_data  # Return the analyzed data

       def calculate_mean_intensity(self):
           # Example: Calculate the mean intensity
           intensity_values = [float(row[1]) for row in self.data]
           mean_intensity = sum(intensity_values) / len(intensity_values)
           return mean_intensity


class XRD(Load, Plot):
    def __init__(self, data_file):
        super().__init__(data_file)
    
    def analyze(self):
        print(f"Performing XRD analysis on data: {self.data_file}")
        x_axis = "Scattering Angle (degrees)"
        y_axis = "Intensity"
        self.load_data()
        # do some analysis
        # analyzed_data = some_analysis()
        return analyzed_data  # Return the loaded data

# Create instances of XPS and XRD
xps_data_file = "XPS_Data.csv"
xrd_data_file = ["XRD_Data1.csv","XRD_Data3.csv","XRD_Data2.csv"]

xps_analysis = XPS(xps_data_file)

for file in xrd_data_file:
    xrd_analysis = XRD(file)
       # Visualize the data with plot()
    xrd_analysis.plot()
       # Get the analyzed data with analyze()
    result = xrd_analysis.analyze()  # how to store “result” depends on the format
```
</details>
{::options parse_block_html="false" /}




### c. Identifying bad data

Identifying and handling bad data is critical in managing big data. The approach depends on the technique and data type. Defining what constitutes 'bad data' is essential. For example, imaging techniques may produce white pixels due to saturation or cosmic interference. While data visualization helps, it's impractical for large datasets. In such cases, statistical methods take the lead. Imaging and tomography software employ algorithms to clean data and reduce noise. 

{::options parse_block_html="true" /}
<details><summary markdown="span">**Press for an example to identify bad data in spectral data**</summary>

We present an example of bad data identification in spectral data, flagging outliers as data points significantly deviating from the mean.

We seek outliers in spectra by computing the mean value of intensities. Data points exceeding three times the standard deviation plus the mean value, and having consecutive points exceeding twice the standard deviation plus the mean value, are removed. This method ensures that peak points in certain patterns are not erroneously flagged as outliers. It's important to note that this example assumes a relatively linear baseline.

add the application of the ourliers, 2 options: interpolation or NaN

```python
# Iteratively compute mean after removing extreme points until convergence. This 
def compute_mean_without_extremes(y, threshold=3.0):
    while True:
        mean = np.mean(y)
        std = np.std(y)
        z_scores = np.abs((y - mean) / std)
        if not any(z_scores > threshold):
            break
        y = y[z_scores <= threshold]
    return np.mean(y)

# Detect outliers based on z-scores with the computed mean
def detect_outliers_zscore_with_neighbors(y, thr=3.0):
    mean = compute_mean_without_extremes(y, thr)
    std = np.std(y)
    z_scores = np.abs((y - mean) / std)
    outliers = np.abs(z_scores) > thr
    # Check if the point before and after exceeds half the threshold
    for i in range(1, len(outliers) - 1):
        if np.abs(z_scores[i - 1]) < thr / 2 and np.abs(z_scores[i + 1]) < thr/2:
            outliers[i] = False
    return outliers

# Set a z-score threshold for outlier detection
zscore_thr = 3.0

outliers = detect_outliers_zscore_with_neighbors(y_data, zscore_thr)
```
</details>
{::options parse_block_html="false" /}



# 2. Analytic Techniques

When it comes to exploring big data, a spectrum of analytical techniques awaits your exploration. From statistical analysis to data mining and the wonders of machine learning, these methods hold the power to unearth valuable insights and patterns within the vast landscape of big data. Here, we offer concise descriptions of these three approaches to help you navigate and analyze your data effectively.

###  Statistical analysis
Statistical models offer insights for big data analysis. Descriptive statistics (mean, median, variance, and standard deviation) provide an overview of data characteristics. Correlation analysis (e.g., Pearson coefficient) reveals relationships. Techniques like Principal Component Analysis (PCA) simplify data complexity. Bayesian models estimate probabilities and assess uncertainty. The Kolmogorov-Smirnov test checks for shared distributions in datasets.

{::options parse_block_html="true" /}
<details><summary markdown="span">**More about PCA**</summary>
The  Principal Component Analysis are used to reduce datasets complexity by lowering dimensionality
It is useful if we have a dataset with high dimension, where we know some dimensions may be correlated. Then we can use PCA to decrease the dimensionality of the data set to be able to better extract new information.

</details>
{::options parse_block_html="false" /}

{::options parse_block_html="true" /}
<details><summary markdown="span">**More about KS**</summary>
The Kolmorogov-Smirnov test proves useful in determining whether two datasets come from the same underlying distribution. Then, it is useful if we want to compare two datasets from the same technique.

It is easily accesible in Python, using the library scipy.

```python
add a short code showing this
```
</details>
{::options parse_block_html="false" /}

### ii. Data mining
Data mining uncovers patterns and associations within large datasets, aiding decision-making and anomaly detection. Techniques like clustering, which groups similar data points (e.g. using K-Means models), unveil relationships between variables and detect unusual patterns.

### iii. Machine Learning
Machine learning opens up a world of data-driven possibilities and is a rapidly evolving field. At its core, it's about crafting algorithms and models that learn from existing data to make predictions. Models come in various forms, including supervised learning (using labeled training data), unsupervised learning (like clustering methods), and reinforcement learning. Machine learning is applied in diverse domains, from image recognition in imaging techniques to spectral data classification, and more. One major challenge here is building extensive databases vital for training these models. Creating strong datasets is crucial for the success of a machine learning model, allowing to produce accurate predictions.


# 3. Data integration

While advanced algorithms excel at revealing patterns, correlations, anomalies, and predictions within your data, the critical step of data integration takes center stage in the data processing workflow, especially when dealing with the multifaceted world of big data. It's the process of bringing together data from various sources into a cohesive format, enabling comprehensive analysis and cross-referencing across diverse data types.

Data integration involves several key steps, including identifying relevant data sources and formats, transforming and cleansing data to ensure consistency, and ensuring data quality. A well-structured data organization and format promote uniformity and ease of use. Additionally, comprehensive metadata documentation detailing data origins and transformation processes is essential. This facilitates seamless access to data, fostering efficient collaboration.


* * * 


# Discussion

Add here any topic or question you would like to discuss.
Please modify the file: 
          <a href="https://github.com/cnherrera/cnherrera.github.io/blob/master/DataProcessing.md">Edit Data processinf</a>
    

## Topic 1
[Add topic here]


## Topic 2
[Add topic here]


[back](BIGMAP-bigdata.md)
