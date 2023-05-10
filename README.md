# Stock Price Prediction and Sentiment Analysis

# About Project
This project combines LSTM-based stock price prediction with sentiment analysis on web page content. It predicts stock prices using historical data and employs a two-layer LSTM neural network. The sentiment analysis function extracts text from web pages, cleans it, and determines sentiment using the TextBlob library. By integrating these components, the project enables accurate stock price forecasting and provides insights into market sentiment.

# Why is it Useful?
The project is useful for several reasons:
1. Accurate Stock Price Prediction: By incorporating LSTM-based modeling techniques, the project improves the accuracy of stock price predictions. This can be valuable for investors, traders, and financial analysts who rely on accurate forecasts to make informed decisions and optimize their investment strategies.

2. Market Sentiment Analysis: The sentiment analysis component allows for the assessment of market sentiment based on web page content. Understanding sentiment can provide insights into the market's perception of a company, industry, or financial event. This information can be used to gauge market sentiment trends, identify potential market shifts, and make more informed investment decisions.
3. Integration of Multiple Data Sources: Unlike conventional approaches that often rely solely on historical stock data or social media sentiment, this project incorporates a diverse range of data sources. By scraping financial news from reputable websites, it captures a broader spectrum of information that can influence stock prices and market sentiment. This holistic approach enhances the reliability and robustness of the predictions and analyses.
4. Efficient Data Retrieval: The project's approach of storing and indexing scraped financial news data in a database offers significant advantages in terms of speed and efficiency. By eliminating the need to repeatedly scrape data from websites, the retrieval process is expedited, allowing for faster analysis and more timely insights.
6. Decision-making Support: Overall, the project provides decision-making support for individuals and organizations operating in the financial markets. It empowers them with more accurate stock price predictions and a deeper understanding of market sentiment, enabling them to make more informed investment decisions, mitigate risks, and potentially improve financial performance.

# How to get started?
To get started with the project:
1. Set up the development environment with required dependencies.
2. Obtain the project code from the repository.
3. Install necessary dependencies.
4. Configure the environment based on project requirements.
5. Understand the project structure and organization.
6. Review the documentation for usage instructions.
7. Run the project using the provided command or script.
8. Explore the generated results and outputs.
These steps will help users quickly start using the project for stock price prediction and market sentiment analysis.

# IMPLEMENTATION

This project consists of two Python functions that perform stock price prediction and sentiment analysis on web pages.
# Stock Price Prediction
The run_model_company() function is used to predict stock prices of a company using the LSTM algorithm. The function takes an input index of a company and extracts the stock data associated with that index. The stock data is first plotted for visualization purposes and then preprocessed by scaling it to the range of 0 to 1 using MinMaxScaler. The scaled data is then divided into training and testing datasets in the ratio of 90:10. The training data is prepared by creating sliding windows of size 30, with the corresponding output as a single value (which is the 31st day's value). A 2-layered LSTM neural network architecture is created with each layer consisting of 128 nodes, followed by two Dense layers with 32 and 1 nodes, respectively. The model is compiled with Adam optimizer and Mean Squared Error loss function, and then trained on the training data with a batch size of 1 and for a single epoch.
After training the model, the testing data is prepared, and sliding windows of size 30 are created similarly to the training data. The trained model is then used to predict the stock prices for the testing dataset. The predicted values are unscaled using the MinMaxScaler object used earlier. The Root Mean Squared Error and Mean Absolute Error of the predicted values compared to the actual values are calculated. Finally, the predicted and actual stock prices are plotted using Matplotlib.
In summary, the function predicts stock prices of a given company using LSTM neural networks and sliding window technique. It preprocesses the data using MinMaxScaler and divides it into training and testing datasets. The model is trained on the training data and then tested on the testing data. The accuracy of the model is evaluated using Root Mean Squared Error and Mean Absolute Error, and the predicted and actual stock prices are plotted for visualization purposes. The function can be used to predict the stock prices of multiple companies by looping through each company's index and calling the function.
# Sentiment Analysis
The get_sentimental_analysis() function extracts the text content from a web page, performs text cleaning, and uses TextBlob library to perform sentiment analysis on the extracted text. The function takes a single argument, url, which is the web address of the page to be analyzed.
The function begins by using the requests module to retrieve the HTML content of the web page. The BeautifulSoup module is then used to extract the text content of the article from the HTML. The extracted text is cleaned by removing stop words, punctuation, and converting all letters to lowercase. The cleaned text is then analyzed using TextBlob, which returns two values: the polarity score and subjectivity score. The polarity score is a float value within the range of -1 to 1, where -1 is very negative, 0 is neutral, and 1 is very positive. The subjectivity score is a float value within the range of 0 to 1, where 0 is very objective, and 1 is very subjective.
In summary, the function extracts text content from a web page, performs text cleaning, and uses TextBlob library to perform sentiment analysis on the extracted text. The polarity score and subjectivity score of the text are returned for analysis.

