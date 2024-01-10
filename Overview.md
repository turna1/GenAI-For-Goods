**Reasons for Lack of  Datasets**:
   - **Time-Intensive Data Collection**: Particularly when manual annotation is needed.
   - **Privacy Concerns**: Difficulty in sharing raw data containing sensitive personal information.

 **Solution: Generating Synthetic Data**
   - **Advances in Generative Models**: Recent progress allows for the creation of realistic synthetic data that mimics complex real data.
   - **Applications**:
     - **Augmenting Training Data**: Useful when there's a shortage of labeled data, helping to prevent overfitting.
     - **Privacy Protection**: Sharing synthetic data instead of original data, maintaining utility while ensuring privacy.
     - 
**Challenges in Synthetic Data Generation**
   - Despite its benefits, creating high-quality synthetic data is a complex, ongoing technical challenge.
    - limited data availability and privacy concern
    - ensuring quality and fairness

 **"What Makes Good Synthetic Data?":**

- **Evaluating Synthetic Data \(\mathcal{E}(D_{synth}, D_{real})\)
  1. **Fidelity**: Concerns the quality of synthetic samples. It assesses how realistic the generated samples appear. (by precision)
  2. **Diversity**: Examines if the generative model can produce a wide variety of realistic samples rather than a limited set of high-quality ones.
  3. **Overfitting**: Checks if the model has simply memorized the training data, which can result in seemingly high fidelity and diversity but actually indicates a lack of true learning. Overfitting is also a concern for privacy in medical applications.
 
**Synthetic Data Evaluation":**
1. Build Data representation (Reconstructed Image)- learn embedding that will facilitate the evaluation
2. Compare Data Representation ( Reconstructed VS Original)- metrics that measure  Fidelity, Diversity and Overfitting.

- **Order of Evaluation**:
  First 2 then 1.

- **3D Score: \(\mathcal{E} = \mathcal{E}(Precision (P), Coverage (C), Memorization (M))\)**
  - **Fidelity** maps to **Precision**: Measures the fraction of synthetic samples that look real. (e.g., 98% data look like real data)
  - **Diversity** corresponds to **Coverage**: Assesses the fraction of real samples the generative model can create. (e.g., 98% of real data was possible to generate)
  - **Overfitting** relates to **Memorization**: Evaluates the fraction of synthetic samples that are repeats of the training data, indicating the model has memorized the data rather than learned to generalize. (e.g., real data has synthetic support, and synthetic data has real support)

**Paper text:**
One of the reasons for the lack of rich datasets is the substantial amount of time needed for data collection, especially when manual annotation is required. Another reason is the need for protecting privacy, whenever raw data contains sensitive information about individuals and hence cannot be shared directly. A powerful solution that can address both of these challenging scenarios is generating synthetic data. Thanks to the recent advances in generative models, it is possible to create realistic synthetic samples that closely match the distribution of complex, real data. In the case of limited labeled data, synthetic data can be used to augment training data to mitigate overfitting. In the case of protecting privacy, data curators can share the synthetic data instead of the original data, where the utility of the original data is preserved but privacy is protected. Despite the substantial benefits from using synthetic data, the process of synthetic data generation is still an ongoing technical challenge. Although the two scenarios of limited data and privacy concerns share similar technical challenges such as quality and fairness, they are often studied separately. 


Source: https://iclr.cc/virtual/2021/workshop/2125#collapse3711


**Overfitting Challenges:**

![image](https://github.com/turna1/GenAI-For-Goods/assets/11919436/8928e8d8-00b1-4a13-87e2-36844e8c16b5)

Proposed Solution:  Handle Overfitting while training by
Outlier detection (e.g., regularizing Overweighting )
**Quality Issue**

Solution: Must pass a threshold

Source: 


**Privacy Challenges**
**Data transfer Issue** from Data  holder (Railway, Hospital, School) to Data user  (ML community)

![image](https://github.com/turna1/GenAI-For-Goods/assets/11919436/f17c987b-b074-4be3-98e1-9f79b32c92c8)

**"Differential Privacy Issue in Existing Generative Models"**
Model memorizes the original data to learn the difference between fake and original data. {source: https://www.nist.gov/blogs/cybersecurity-insights/differential-privacy-privacy-preserving-data-analysis-introduction-our]

Solution : Indistinguishability: bounded ratio of probability; K-annomaly detection
**Distributional Privacy**:
https://openreview.net/pdf?id=6oVAzFsHLFK
Minimize the privacy metric; so that the latent information in the generated data is different than the original one.
[source: https://arxiv.org/pdf/2301.07573v1.pdf]


Papers: 
1. **Beyond Privacy: Navigating the Opportunities and
Challenges of Synthetic Data**
https://arxiv.org/pdf/2304.03722.pdf
2. **Synthetic data for privacy-preserving clinical risk
prediction**
https://www.medrxiv.org/content/10.1101/2023.05.18.23290114v1.full.pdf
