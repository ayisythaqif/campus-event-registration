### Specialized Technology: Machine Learning

Machine learning (ML) is a branch of artificial intelligence that enables a computer system to 
learn patterns from data and use those patterns to make predictions or classifications. 
For this project, machine learning is proposed as the main specialized technology for classifying suspicious URLs.

#### Fundamental Concepts

**1. Dataset and labels**

A dataset contains URL examples and their associated labels, such as phishing and legitimate. 
The dataset should be reviewed for quality, relevance, class imbalance, and possible duplicate records.

**2. Feature extraction**

Feature extraction converts a URL into information that a model can process. 
Possible features include URL length, the number of subdomains, the presence of an IP address in the hostname, and selected character patterns. 
No single feature automatically proves that a URL is malicious.

**3. Model training and classification**

A classification algorithm learns patterns from labelled training data. 
After training, the model can estimate the class of a previously unseen URL based on its extracted features.

**4. Model evaluation**

The model should be evaluated using a separate test dataset. Useful evaluation measures include precision, recall, F1-score, and a confusion matrix. 
These measures help identify false positives, where legitimate URLs are flagged, and false negatives, where phishing URLs are missed.

#### Proposed Workflow

Labelled URL dataset → Data preprocessing → Feature extraction → Model training → Testing and evaluation → Web interface → Risk assessment displayed to the user.

#### Models and Tools

- **Decision Tree:** Learns classification rules that can be relatively easy to interpret.
- **Random Forest:** Combines predictions from multiple decision trees.
- **Support Vector Machine (SVM):** Separates classes using a learned decision boundary.
- **Scikit-learn:** A Python machine-learning library that can be used to preprocess data, train models, and evaluate results.

These are candidate methods, not claims that all have been implemented. A final model should be selected based on experimental evaluation.

#### Suitability, Benefits and Limitations

Machine learning can identify patterns in URL data and may classify previously unseen URLs when their features resemble patterns learned during training.
However, performance depends on the quality and representativeness of the dataset. 
Models may produce false positives and false negatives, and their accuracy can decline as attack techniques change.

Phone-number checking should initially be treated as a separate lookup function using a reliable, authorized scam-report source. 
Its records may be incomplete or outdated, and the absence of a match does not demonstrate that a number is safe.

#### Alternative Approach

A blacklist or reputation lookup checks URLs against known threat records. 
This can be straightforward and useful for previously reported threats, but may miss new URLs that have not yet been recorded. 
Machine learning and reputation lookup could be compared or combined in a future implementation.
