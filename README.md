# Google-News-Headlines-Sentimen-Analysis
Multiclass text classification using Word Embeding with LSTM and its varians.
Data is scraped from investing.com using Selenium Python, utilizing website HTML structure, from Januari 2010 until July 2021.

This project is done in order to complete my Thesis : "Google Company Sentiment Analysis using Bi-directional Long Short Term Memory for Imbalanced Data"

Overview
========
<h3>About the data: </h3>
Data, that is used, contains list of Google News Headlines from Januari 2010 until June 2021. <br/>
Data is collected using Web Scraping technique on Investing.com. <br/>
Web Scraping is done by collecting sentences on tag class='title' and class='date' from the HTML structure.<br/>

![image](https://user-images.githubusercontent.com/67742339/144521808-f54fe61e-a4c4-4e25-9aa9-8427811ea83d.png)

<h3>Preprocessing Data :</h3>

* Case Folding
* Deleting Stopwords
* Stemming
* Cleaning Duplicate Data

<h3>Labeling Sentiment Class</h3>

* Sentiment Class is labelled using VADER (Valence Aware Dictionary for Sentimen Reasoning).
* Sentiment score is calculated by totalling intensity score of every words in the sentence.
* The score is ranging from -1 to 1.

<br/>
Creating Data Training, Data Validation and Data Testing.<br/>

![image](https://user-images.githubusercontent.com/67742339/144522295-5e13d850-4b99-4a44-9ebb-ba0533d146ec.png)

Data Training Sentiment Classes Plot : <br/>

![image](https://user-images.githubusercontent.com/67742339/144522229-244d9fbe-835a-4f02-9222-df9fcde3077c.png)

The graph shows that there are imbalanced classes in data training. Therefore, Random Oversampling Technique will be applied to the data training to make the dataset balanced. <br/>
<h3>Word Embedding</h3>

* input_dim = 1000
* input_length = 25
* output_dim = 16 and 32

<h3>Parameters that is used in data modelling</h3>

![image](https://user-images.githubusercontent.com/67742339/144522936-c4019c2e-676f-470e-a18a-dcb69b6c8298.png)

*For Stacked LSTM and Stacked BiLSTM
</br>

<h3>Overall Model's Perfomance</h3>

![image](https://user-images.githubusercontent.com/67742339/144523267-6ff6ae91-51f6-48ad-84e8-50df91da9657.png)

</br>

![image](https://user-images.githubusercontent.com/67742339/144523271-0f0ea06a-daac-4661-8093-57546974d155.png)

</br>
<h3>Applying Dropout</h3>

![image](https://user-images.githubusercontent.com/67742339/144523282-56c094d6-977c-4030-a9d5-732422a2cf8f.png)

<h3>The Best Model</h3>

![image](https://user-images.githubusercontent.com/67742339/144523288-c38ab392-ed4c-4478-9dda-3a52ed658af0.png)

</br>
It can be seen from the table above that model Stacked_BiLSTM_5_Bal has the highest F1-Score Micro, Macro and Weighted. Thus, it can be concluded that it is the best model for classifying Google News Headlines Sentiment data. Confusion Matrix, based on data test, of the best model is shown below. </br>

![image](https://user-images.githubusercontent.com/67742339/144523477-4f5ad5d7-b550-49ee-9a21-5ae9e20b28f5.png)

<br/>
Model's architecture is shown below : <br/>

![image](https://user-images.githubusercontent.com/67742339/144523410-bde7d7a0-5464-4a3b-b54c-fa5dbd335282.png)


