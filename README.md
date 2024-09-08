# Introduction
- Users who are active on social media tend to express their emotional distress on social media platforms. 
- Many individuals may not disclose their online expression of distress and suicidality to their physician (general doctor). 
- However, studies show a correlation of suicidal thoughts expressed online with psychometrically assessed suicidal risk. 
- Online self-expression can serve as a crucial warning sign, providing an opportunity for intervention and support.

# Objective
- Develop a tool to aid general healthcare professionals in identifying individuals at risk of suicidal tendencies.
- Enhance detection methods for suicidal inclinations among patients who may not consult mental health specialists (or psychiatrists).
- Bridge the gap between general healthcare and mental health services.

# Need of the Project

### Use Case 1
- While many people with suicidal tendencies visit doctors, not all reach out to mental health experts. 
- This gap stresses the importance of helping regular healthcare providers recognize signs of suicidal thoughts. 
- Our project aims to fill this need by creating a tool to assist general healthcare professionals in identifying individuals who may need to see mental health specialists.

### Use Case 2
- Mental health specialists may not always have the capacity to review patients' social media activity for signs of suicidal tendencies. 
- Our tool aims to complement their assessments by providing an analysis of social media posts for potential indicators of suicidal thoughts, thereby tailoring treatment approaches.

# Methodology
<div style="display: flex; gap: 10px;">
    <img src="https://github.com/Manojkumardamsalapudi/landslide-detection/assets/161069320/de77f45d-2e2c-406b-ad5a-1fb03ab99c89" alt="Screenshot 1" width="45%">
    <img src="https://github.com/Manojkumardamsalapudi/landslide-detection/assets/161069320/fdc9cfd6-1042-4b99-9037-c04d250afc35" alt="Screenshot 2" width="45%">
</div>

### Dataset Description
- Data was obtained from the Kaggle "suicide watch" dataset, comprising 1893 tweets and comments categorized into suicide and non-suicide categories by annotators and automated tools. 
- Human annotators meticulously reviewed individual posts, comments, or tweets to identify signs of suicidal ideation or mental health issues, following standardized annotation guidelines to ensure consistency. 
- Annotated data was validated against a standard or expert-labeled dataset and stored in a .csv file.

### Pre-Processing
- Pre-processing begins with data cleaning steps, filling missing values, and handling null entries. 
- Text preprocessing includes converting to lowercase, tokenization, and removal of stop words. 
- Additional preprocessing steps involve filtering based on word length, removal of non-English words, and lemmatization. N-gram techniques, specifically Count Vectorizer and TF-IDF Transformer, are applied for feature extraction. 
- The resulting TF-IDF representations are split into training and testing sets for model training.

### Model Training
- **LSTM1**: Embedding layer, Dropout layer, Bi LSTM layer, Dropout layer, Flatten layer, Dense layer (ReLU activation), Dropout layer, Dense layer (Softmax activation)
- **LSTM2**: Embedding layer, Dropout layer, Bi LSTM layer, Dropout layer, Bi LSTM layer, Dropout layer, Flatten layer, Dense layer (ReLU activation), Dropout layer, Dense layer (Softmax activation)
- **GRU**: Embedding layer, Dropout layer, GRU layer, Dropout layer, Dense layer (ReLU activation), Dense layer (Softmax activation)
- **CNN + LSTM**: Embedding layer, Dropout layer, Convolutional layer, MaxPooling layer, BiLSTM layer, Flatten layer, Dense layer (ReLU activation), Dropout layer, Dense layer (Softmax activation)

### Testing and Evaluation for Accuracy
![Screenshot 2024-06-03 201920](https://github.com/Manojkumardamsalapudi/landslide-detection/assets/161069320/059c3a5a-2eee-488b-af02-19d83c02ac1c)

### Making Prediction
- A username is given as input into a web application built with Streamlit. 
- This application utilizes the Twitter API to fetch the user's posts data from Twitter. 
- The fetched data undergoes preprocessing to prepare it for analysis. 
- The application iterates over each tweet and each model to make predictions on the tweet content using the four pre-trained models and takes the average of the four model predictions to give the final prediction. 
- Finally, the predictions are displayed on the web application, providing the user with insights into the analyzed content.

### Outcome Analysis
![Screenshot 2024-06-03 202101](https://github.com/Manojkumardamsalapudi/landslide-detection/assets/161069320/0ac0b871-661f-480d-9f5e-080603f30d4f)
![Screenshot 2024-06-03 202124](https://github.com/Manojkumardamsalapudi/landslide-detection/assets/161069320/0652a6d1-f261-4950-bb08-25ee15edd966)

# Conclusion
In conclusion, our project aims to bridge the gap in mental health care by providing a tool for general healthcare professionals to identify patients with suicidal tendencies using deep learning on their social media data, ensuring they receive timely and appropriate care from mental health professionals.

# Future Work
- Assigning higher weights to more recent user posts to enhance prediction.
- Implementing a feature for analyzing posts in multiple languages.
- Incorporating image analysis of user posts for more insights and enhanced prediction.
