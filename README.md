Data Visualization (Matplot + Pandas) using Python (Jupyter NoteBook)


<img width="640" alt="image" src="https://github.com/user-attachments/assets/31e9bae9-b8ae-4a8b-b567-ae7837bf59f2" />



Jupyter : 
Jupyter is an open-source, web-based interactive computing platform that allows you to create and share documents containing live code, equations, visualizations, and narrative text. It's widely used for data analysis, scientific research, and machine learning tasks.jupyter.org

Source : https://github.com/jayamoorthi/JupiterPython

Key Features of Jupyter:

Interactive Notebooks: Combine code execution, text, and visualizations in a single document.

Support for Multiple Languages: While primarily used with Python, Jupyter also supports languages like R, Julia, and Scala through the use of different kernels.

Extensibility: Enhance functionality with a wide range of plugins and extensions.



Getting Started with Jupyter:

To begin using Jupyter, you can choose from the following installation methods:

Using Anaconda:

What is Anaconda? Anaconda is a free, open-source distribution of Python and R for scientific computing and data science. It simplifies package management and deployment. Installation Steps: Installation Steps: 

Download the Anaconda installer suitable for your operating system from the Anaconda Distribution page.

Run the installer and follow the on-screen instructions.

After installation, open the Anaconda Prompt (Windows) or terminal (macOS/Linux).

Launch Jupyter Notebook by typing:

Terminal 

jupyter notebook
This command will start the Jupyter Notebook server and open the notebook interface in your default web browser.

2.  Using pip:  Installation Steps: 

Ensure that Python and pip are installed on your system. You can download Python from the official Python website.

Open your terminal or command prompt.

Install Jupyter Notebook using pip:

After installation, start the Jupyter Notebook server by typing

jupyter notebook
Jupyter Server running and redirect to Home Page.  http://localhost:8888/tree



Minimize image
Edit image
Delete image


Let 's start to create new project folder for Data Visualization 

Setting up Jupyter Notebook within Visual Studio Code (VS Code) using a virtual environment is an excellent way to manage project dependencies and maintain an organized development environment. Here's a step-by-step guide to help you through the process:​claudia-nikel.com

Step 1: Create a New Project Folder in VS Code
Open VS Code: Launch Visual Studio Code on your computer.

Create a New Folder: In the VS Code menu, click on File > Open Folder....​ Choose a location on your system and create a new folder for your project.​ Open this folder in VS Code.​claudia-nikel.com

Step 2: Set Up a Virtual Environment
Open the Terminal: In VS Code, open the integrated terminal by selecting Terminal > New Terminal from the menu.​

Create the Virtual Environment: In the terminal, run the following command to create a virtual environment named myenv:​

python3 -m venv myenv
3. Activate the Virtual Environment: 
Activate the virtual environment using the appropriate command for your operating system:​ Windows:

.\myenv\Scripts\activate

Minimize image
Edit image
Delete image


After activation, your terminal prompt should change to indicate that you're now working within the myenv environment.

Step 3: Install Jupyter Notebook  Using (Method 2) Using pip Installation 
Install Jupyter: With the virtual environment activated, install Jupyter Notebook by running:

pip install notebook

After installation, start the Jupyter Notebook server by typing



Minimize image
Edit image
Delete image


Jupyter server running redirect broswer  



Minimize image
Edit image
Delete image


This command will start the server and automatically open the Jupyter Notebook interface in your default web browser, typically accessible at http://localhost:8888/tree.

Step 5: Create and Manage Notebooks in VS Code
Create a New Jupyter Notebook: In the VS Code interface:​ Click on the View menu, then select Command Palette.... Type Jupyter: Create New Blank Notebook and select it. Choose the Python interpreter associated with your myenv virtual environment when prompted.

Rename the Notebook: Click on the notebook's name at the top (e.g., "Untitled.ipynb") to rename it as desired.​



Minimize image
Edit image
Delete image


Step 6: Install Additional Libraries (e.g., pandas)
Install pandas: Within the Jupyter notebook, in a new cell, run:​

pip install pandas numpy



Minimize image
Edit image
Delete image

Click play button to run code and below the code see output for library running files
7. Create as Dataset as csv file and Save using numpy for Data Analytics

import pandas as pd
import numpy as np
import random

#set number of rows 
num_rows = 1000
state_list =['TamilNamu', 'Karanadaka', 'Kerala', 'Andra', 'Delhi', 'Uthrapradsash', 'Maharastra']
# generate data
np.random.seed(42)
ids = np.arange(1, num_rows+1)
ages = np.random.randint(18, 80, size=num_rows)
incomes = np.random.normal(loc=50000, scale=15000, size=num_rows).astype(int)
credit_scores = np.random.randint(300, 850, size=num_rows)
loan_amounts = (incomes *0.2).astype(int)
states =  random.choice(state_list)


# create dataframe
df = pd.DataFrame({
    'ID': ids,
    'Ages': ages,
    'Income': incomes,
    'Credit_Score': credit_scores,
    'Loan_Amount': loan_amounts,
    'State': states
})

# Save to CSV
df.to_csv('synthetic_data.csv', index=False)
print('dataset created and saved as synthetic_data.csv successfully')
Running above code "dataset created and saved as synthetic_data.csv successfully"

 Load CSV data from file and Print : 
# Step5 : Load CSV data from file and print it
df =pd.read_csv('synthetic_data.csv')

print(df);



Minimize image
Edit image
Delete image


#step 9: Data Analysis Group 
grouped = df.groupby('Ages')['Loan_Amount'].sum()
print(grouped)
# step 10:   Data visualization using matplot 
pip install matplotlib


Create data visualization using line chart
import matplotlib.pyplot as plt
import numpy as np

# Group by 'Ages' and sum 'Loan_Amount'
grouped = df.groupby('Ages')['Loan_Amount'].sum()


# Plot the grouped data as a line chart
grouped.plot(kind='line', marker='o', linestyle='-', color='b', title='Loan Amount by Age Group')

# Set labels for the axes
plt.xlabel('Ages')
plt.ylabel('Total Loan Amount')

# Display the plot
plt.show()


<img width="665" alt="image" src="https://github.com/user-attachments/assets/92dcbce7-7705-48e8-89e3-43cd0a6916d8" />





 Create data visualization using pie chart :

import matplotlib.pyplot as plt
import numpy as np

# Group by 'Ages' and sum 'Loan_Amount'
grouped = df.groupby('Ages')['Loan_Amount'].sum()

# Plot the grouped data as a pie chart
grouped.plot(kind='pie', autopct='%1.1f%%', startangle=90, figsize=(8, 8))

# Add a title to the pie chart
plt.title('Total Loan Amount by Age Group')

# Display the plot
plt.show()



<img width="842" alt="image" src="https://github.com/user-attachments/assets/5267ff45-2d0e-4e03-84cb-6f926a25525c" />






Conclusion : 
Data Visualization Libraries:

In the realm of data visualization, several libraries and tools cater to diverse needs:​

Matplotlib: A versatile Python library for creating static, animated, and interactive 2D plots. It's known for its flexibility and extensive customization options. ​reflex.dev

Seaborn: Built on top of Matplotlib, Seaborn simplifies the creation of informative and attractive statistical graphics, offering a high-level interface for drawing attractive statistical graphics. ​reflex.dev

Tableau: A powerful data visualization tool that enables users to create interactive and shareable dashboards. It's known for its user-friendly interface and ability to handle large datasets efficiently. ​codesuite.org

Power BI: Developed by Microsoft, Power BI is a business analytics tool that provides interactive visualizations and business intelligence capabilities with an interface simple enough for end users to create their own reports and dashboards. ​

Learning Outcomes:

Library Installation: Utilizing Jupyter Notebook's capabilities to install essential libraries like pandas for data manipulation and analysis. ​

Data Creation and Loading: Generating synthetic data and loading it into pandas DataFrames for structured analysis.​

Data Analysis: Performing grouping and aggregation operations to derive meaningful insights from the data.​

Data Visualization: Employing Matplotlib to create various plots, enhancing the interpretability of data insights.​

This integrated approach demonstrates the effectiveness of using Jupyter Notebook alongside powerful libraries and tools to conduct comprehensive data analysis and visualization tasks.

Thanks to visit my post, see you bye bye next week. 
