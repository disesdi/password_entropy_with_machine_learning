# Password Entropy with Machine Learning

*a multi-class classifier for levels of password entropy*

this project implements the `XGBClassifier` from the `xgboost` library. model training was conducted in google `Colab`.

code is available [in this jupyter notebook](https://github.com/disesdi/password_entropy_with_machine_learning/blob/fd6708a7c33b39284cbc0a8a1269058d009b6c5f/assessing_password_security_with_machine_learning.ipynb)

dataset for this project can be found [here](https://github.com/disesdi/password_entropy_with_machine_learning/blob/fd6708a7c33b39284cbc0a8a1269058d009b6c5f/passwordDataset.csv)

this is a multi-class supervised learning problem, with 3 potential grades of password entropy, ranging from least to most.

because password analysis is often conducted at scale, this project was implemented using `sklearn` modules that are compatible with pipelines.

because passwords are effectively text files, natural language processing techniques are required to:

* split text into tokens

* vectorize

for vectorization, i chose TF-IDF for its effectiveness & ease of implementation within `sklearn` pipelines, using the `TfidfVectorizer` from the `sklearn.feature_extraction.text` module.

the `get_char_tokens` function takes as input a password string, and splits into individual character tokens.

**`Pipeline` in `sklearn`**

*pipeline steps:*

1. initialize `Pipeline`

2. split passwords to character tokens using the get_char_tokens function i created above

3. vectorize tokens using TfidfVectorizer from sklearn

4. train the classifier

*example:*

![image](https://user-images.githubusercontent.com/110150470/211313519-4eb9a750-8796-4e0c-bb44-8b4be48a364d.png)

*testing the classifier out on sample low-to-high entropy passwords:*

![image](https://user-images.githubusercontent.com/110150470/211314017-f4487097-0a34-4a60-811b-b69c600126ec.png)

the classifier performs as expected.
