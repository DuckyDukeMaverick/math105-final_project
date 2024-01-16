# What Drives Democratization?

This is my Final Project for the class MATH105: Introduction to Data Analysis at Fulbright University Vietnam, carried out in collaboration with three other sophomores at Fulbright University Vietnam in the Spring of 2023. My main responsibilities were data wrangling, and running linear regressions using Python (Pandas, numpy, scikit-learn).

### Project Description:
This project investigates the factors that influence the process of democratization. We downloaded, cleaned, and concatenated data from [GapMinder](https://www.gapminder.org/) to form a datasets with democracy scores, Internet usage, GDP, Import, etc. of 90 countries from 1990 to 2019. 

<p align="center">
<img src = "MATH105-Illustration\data distribution.png" width = 60% height = 60%>
</p>

We then carried out series of hypothesis testing methods (one-sample & two-sample T-test, Mann-Whitney U-test) to test if there is a difference between democratic and non-democratic country. We also ran 30 linear regressions (one for each of the year) to view the factors that have statistically significant impact on democracy score.


  <div id="df-9d27f077-94e7-455d-a570-e826f5c46fba" class="colab-df-container">
    <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Year</th>
      <th>Democracy Score</th>
      <th>Aid Received</th>
      <th>Line Phone</th>
      <th>Internet</th>
      <th>FDI</th>
      <th>Inequality</th>
      <th>Income</th>
      <th>GDP</th>
      <th>Import</th>
      <th>Export</th>
      <th>Trade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Albania</td>
      <td>1990</td>
      <td>0.000</td>
      <td>16300000.0</td>
      <td>1.22</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>26.9</td>
      <td>5020.0</td>
      <td>5.280000e+09</td>
      <td>24.0</td>
      <td>15.40</td>
      <td>2.080320e+11</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Albania</td>
      <td>1991</td>
      <td>0.764</td>
      <td>463000000.0</td>
      <td>1.27</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>27.0</td>
      <td>3650.0</td>
      <td>3.800000e+09</td>
      <td>28.6</td>
      <td>7.48</td>
      <td>1.371040e+11</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Albania</td>
      <td>1992</td>
      <td>0.922</td>
      <td>564000000.0</td>
      <td>1.38</td>
      <td>0.0</td>
      <td>3.07</td>
      <td>27.0</td>
      <td>3430.0</td>
      <td>3.530000e+09</td>
      <td>96.3</td>
      <td>12.50</td>
      <td>3.840640e+11</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Albania</td>
      <td>1993</td>
      <td>0.915</td>
      <td>404000000.0</td>
      <td>1.35</td>
      <td>0.0</td>
      <td>4.89</td>
      <td>27.0</td>
      <td>3770.0</td>
      <td>3.860000e+09</td>
      <td>64.5</td>
      <td>16.00</td>
      <td>3.107300e+11</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Albania</td>
      <td>1994</td>
      <td>8.000</td>
      <td>223000000.0</td>
      <td>1.32</td>
      <td>0.0</td>
      <td>2.82</td>
      <td>27.0</td>
      <td>4090.0</td>
      <td>4.190000e+09</td>
      <td>41.1</td>
      <td>12.00</td>
      <td>2.224890e+11</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-9d27f077-94e7-455d-a570-e826f5c46fba')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-9d27f077-94e7-455d-a570-e826f5c46fba button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-9d27f077-94e7-455d-a570-e826f5c46fba');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-aeb7974a-8330-4e98-8c21-5c2bcdec2707">
  <button class="colab-df-quickchart" onclick="quickchart('df-aeb7974a-8330-4e98-8c21-5c2bcdec2707')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-aeb7974a-8330-4e98-8c21-5c2bcdec2707 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>


 We found that use of Internet and line phone, along with inequality are the three statistically significant factors influencing democratization.






