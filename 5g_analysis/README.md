# 5G Quality of Service : Data-Driven Insights and EDA 5G Coverage WW

## Directory Structure

```
├── 5g_analysis
│   ├── 5g_coverage_analysis
│   │   ├── 5g_coverage_analysis.ipynb
│   │   └── README.md
│   ├── 5g_qos_data_insights
│   │   └── 5g_qos_data_insights.ipynb
│   │   └── README.md
│   └── dataset
│       ├── 5G_qos_insights.csv
│       └── 5g_coverage.csv
```

## Installation

### Clone the Repository

```sh
git clone https://github.com/R300-AI/jetson_orin_examples.git
cd jetson_orin_examples
```

### General Installation

1. Create a virtual environment:

    ```sh
    virtualenv .venv
    ```

2. Activate the virtual environment:
    - Windows:

        ```sh
        .\.venv\Scripts\activate
        ```

    - macOS and Linux:

        ```sh
        source .venv/bin/activate
        ```

3. Install the necessary dependencies:

    ```sh
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```

4. Ensure you are in the `jetson_orin_examples` directory.

### Notebook Installation

#### Jupyter Notebook

1. Ensure you have Jupyter Notebook or Jupyter Lab installed. If not, run the following command:

    ```sh
    pip install notebook
    ```

2. Start Jupyter Notebook:

    ```sh
    jupyter notebook
    ```

3. Open the `5G_qos_data_insights.ipynb` or `5g_coverage_analysis.ipynb` file in Jupyter Notebook to start the analysis.

#### Using Jupyter Notebook in VSCode

1. Ensure you have Visual Studio Code installed. If not, download and install it from [here](https://code.visualstudio.com/).

2. Install the Python and Jupyter extensions:
    - Open VSCode
    - Go to the Extensions Marketplace
    - Search for and install the Python extension
    - Search for and install the Jupyter extension

<img src="https://github.com/R300-AI/jetson_orin_examples/5g_analysis/src/images/python_extension.png" width="450px"></img>

<img src="https://github.com/R300-AI/jetson_orin_examples/5g_analysis/src/images/python_extension.png" width="450px"></img>

1. Open your project folder in VSCode:

    ```sh
    cd path/to/your/jetson_orin_examples
    ```

2. Open the `5G_qos_data_insights.ipynb` or `5g_coverage_analysis.ipynb` file:
    - In the VSCode file explorer, find and open the `5G_qos_data_insights.ipynb` or `5g_coverage_analysis.ipynb` file
    - VSCode will automatically recognize and open the notebook interface

3. Start running the notebook:
    - You can execute the code cells one by one in the opened notebook in VSCode