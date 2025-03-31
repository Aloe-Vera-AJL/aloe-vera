# aloe-vera
---

# Inclusive Dermatology AI
Build an inclusive machine learning model for dermatology that performs well across diverse skin tones.

### **👥 Team Members**

| GitHub Handle  | Contribution |
| -------------- | ----------- |
| Aleena Sultan  | Model Development, Data Exploration |
| Sara Wang      | Fairness Analysis, GitHub Write-Up |
| Thienkim Nguyen | Data Preprocessing, Augmentation, Model Evaluating |
| Trisha Chinnimeni | Data Preprocessing, Model Exploration|
| Journei Ferguson | N/A|

---

## **🎯 Project Highlights**

* Built a **CNN with transfer learning** using **data augmentation and fairness techniques** to solve the **Kaggle dermatology classification task**.
* Achieved an F1 score of **0.02498** 
* Used **Fairlearn** to interpret model decisions.
* Implemented **image flipping and rotation** to address skin tone representation in the dataset.

🔗 [Equitable AI for Dermatology | Kaggle Competition Page](https://www.kaggle.com/competitions/bttai-ajl-2025/overview)

---

## **👩🏽‍💻 Setup & Execution**

**Provide step-by-step instructions so someone else can run your code and reproduce your results. Depending on your setup, include:**

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/username/aloe-vera.git](https://github.com/Aloe-Vera-AJL/aloe-vera/tree/main)](https://github.com/Aloe-Vera-AJL)
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up the environment:**
   ```bash
   conda create --name aloe-vera python=3.8
   conda activate aloe-vera
   ```

4. **Access the dataset(s):**
   - Download the dataset from the Kaggle competition page and place it in the `data/` folder.

5. **Run the notebook or scripts:**
   ```bash
   jupyter notebook
   ```

---

## **🏗️ Project Overview**

The Kaggle competition, co-created by Break Through Tech and the Algorithmic Justice League (AJL), focuses on building an AI model for dermatology that can classify 21 different skin conditions across diverse skin tones. The challenge seeks to reduce health disparities in underserved communities by improving the performance of dermatology AI tools on individuals with darker skin tones.

Our work in this challenge aims to create an inclusive machine learning model, leveraging fairness techniques and AI explainability tools to ensure that our model performs well across all skin tones and minimizes harmful biases.

---

## **📊 Dataset Description**

The dataset is a subset of the FitzPatrick17k dataset, a labeled collection of about 17,000 images depicting a variety of serious (e.g., melanoma) and cosmetic (e.g., acne) dermatological conditions with a range of skin tones scored on the FitzPatrick skin tone scale (FST). About 4500 images are in this set, representing 21 skin conditions out of the 100+ in the full FitzPatrick set. We used a subset in order to create a more manageable and hopefully satisfying classification problem, while trying to maintain some of the representation issues surfaced by the full set.

The images in this dataset are sourced from two reputable dermatology websites, **DermaAmin** and **Atlas Dermatologico**. The dataset includes images of various skin conditions, including serious wounds, burns, scars, and other conditions that might be disturbing to some viewers. Please note that some images may be unsettling, and random exploration of images might display potentially disturbing content. If you are sensitive to such content, it may be best for another team member to inspect the images.

**Files:**
- `images.zip` - An archive file containing the images, split into `train` and `test` directories. The `train` directory is divided into subdirectories according to the image's label. The `test` directory contains unlabeled images for making the submission.
- `train.csv` - Full metadata about the images in the training set.
- `test.csv` - Metadata for the test set, with no labels for prediction.
- `sample_submission.csv` - A sample submission file showing the correct format for submissions. It contains only two columns: `md5hash` and `label`.

**Data Dictionary:**

| Column                  | Data Type | Description |
|-------------------------|-----------|-------------|
| `md5hash`               | Object    | An alphanumeric hash serving as a unique identifier; file name of an image without `.jpg` |
| `fitzpatrick_scale`     | int64     | Integer in the range [-1, 0) and [1, 6] indicating self-described FitzPatrick skin tone |
| `fitzpatrick_centaur`   | int64     | Integer in the range [-1, 0) and [1, 6] indicating FST assigned by Centaur Labs |
| `label`                 | Object    | String indicating the medical diagnosis (target for this competition) |
| `nine_partition_label`  | Object    | String indicating one of nine diagnostic categories |
| `three_partition_label` | Object    | String indicating one of three diagnostic categories |
| `qc`                    | Object    | Quality control check by a Board-certified dermatologist |
| `ddi_scale`             | int64     | Column used to reconcile this dataset with another dataset (may not be relevant) |

---

## **🧠 Model Development**

**Model(s) used:**
- We employed a **CNN model with transfer learning**. We fine-tuned the model on the competition dataset.

**Feature selection and hyperparameter tuning:**
- We focused on image features and used **data augmentation** to enhance model performance.
- Hyperparameters such as learning rate and batch size were tuned using grid search.

**Training setup:**
- **70% training data**, **15% validation data**, **15% test data**.
- We used **F1 score** as the evaluation metric.

---

## **📈 Results & Key Findings**

**Performance metrics:**
- Our model achieved an **F1 score of *0.02498* **

**Model performance across different skin tones:**
- The model performed better on lighter skin tones, but after applying augmentation, we saw improvements in the accuracy for darker skin tones as well.

**Insights from evaluating model fairness:**
- We used **Fairlearn** to highlight fairness gaps and identified areas where the model was less accurate for darker skin tones. Adjustments through data augmentation improved fairness across all groups.

**Potential visualizations to include:**
- Confusion matrix showing skin tone-specific performance.
- Precision-recall curve for evaluating model fairness.

---

## **🖼️ Impact Narrative**

**AJL challenge:**

1. **What steps did you take to address model fairness?**
   - We applied **data augmentation techniques** (flipping, rotation) to balance the dataset. Additionally, we used a **validation set** to assess performance across different skin tones and adjusted our model accordingly.

2. **What broader impact could your work have?**
   - By addressing biases in dermatology AI, our work can help ensure more equitable healthcare access, particularly for underserved communities. Our efforts aim to reduce diagnostic errors and health disparities for people with darker skin tones.

---

## **🚀 Next Steps & Future Improvements**

* **Limitations of our model:**
   - Did not subsribe well to the testing set despite reasonable performance on training/validation sets, and model needs more complexity.
* **What would you do differently with more time/resources?**
   - Explore more models, more testing and Kaggle attempts to try to figure out the large drop in validation a testing set.
   - Explored more of the data by creating visualizations to find patterns
   - Add more layers to the neural network
* **What additional datasets or techniques would you explore?**
   - Domain-Adversarial Neural Network.
   - Balancing classes

