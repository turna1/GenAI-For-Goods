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
    - limited data availability and privacy concerns
    - ensuring quality and fairness

 **"What Makes Good Synthetic Data?":**

- **Evaluating Synthetic Data \(\mathcal{E}(D_{synth}, D_{real})\)
  1. **Fidelity**: Concerns the quality of synthetic samples. It assesses how realistic the generated samples appear. (by precision)
  2. **Diversity**: Examines if the generative model can produce a wide variety of realistic samples rather than a limited set of high-quality ones.
  3. **Overfitting**: Checks if the model has simply memorized the training data, which can result in seemingly high fidelity and diversity but actually indicates a lack of true learning. Overfitting is also a concern for privacy in medical applications.

   #Synthetic Data Quality Evaluation#
To evaluate synthetic data quality, the three primary methods are:

1. **Machine Learning Utility**: This approach focuses on the practical usefulness of synthetic data in machine learning contexts. It involves training various classifiers with and without the synthetic data, then comparing their accuracy. The idea is to assess how well the synthetic data contributes to the performance of machine learning models. A key aspect of this method is ensuring that the classifiers are optimized for both the original and synthetic datasets.

2. **Statistical Similarity**: This method assesses whether synthetic data can serve as a viable substitute for original data by comparing their statistical properties. Tools such as Kullback-Leibler (KL) divergence, Jensen-Shannon (JS) divergence, Wasserstein distance, and Pairwise Correlation Difference (PCD) are used to measure how closely the synthetic data mimics the statistical characteristics of the original data. These measures help determine the extent to which the synthetic data retains the essential properties of the original dataset.

3. **Privacy Preservability**: The third method focuses on the privacy aspects of synthetic data. This is crucial when the original data contains sensitive information. Metrics such as Distance to Closest Record (DCR) and Nearest Neighbor Distance Ratio (NNDR) are used to evaluate how well the synthetic data preserves privacy. A high DCR value or a certain pattern in NNDR can indicate that the synthetic data maintains a good balance between being useful and not compromising the privacy of the individuals represented in the original dataset.

Together, these methods provide a comprehensive framework for evaluating synthetic data, ensuring that it is useful for machine learning applications, statistically representative of the original data, and respectful of privacy concerns.

 
**Synthetic Data Generation  Evaluation":**
1. Build Data representation (Reconstructed Image)- learn embedding that will facilitate the evaluation
2. Compare Data Representation ( Reconstructed VS Original)- metrics that measure  Fidelity, Diversity, and Overfitting.

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

Possible research questions:

1. How can the VAE based approach be modified to generate better examples to improve
classification accuracy?
2. How can algorithmic fairness be affected by generating synthetic data examples?

Papers: 
1. **Beyond Privacy: Navigating the Opportunities and
Challenges of Synthetic Data**
https://arxiv.org/pdf/2304.03722.pdf
2. **Synthetic data for privacy-preserving clinical risk
prediction**
https://www.medrxiv.org/content/10.1101/2023.05.18.23290114v1.full.pdf



Phd symposiums:

https://dl.acm.org/doi/10.1145/3581783.3613435


https://uwaterloo.ca/news/setting-standards-and-unlocking-potential-synthetic-data


https://tigerprints.clemson.edu/cgi/viewcontent.cgi?article=3958&context=all_dissertations


https://ucla-synthetic-data.github.io/

https://sites.google.com/g.ucla.edu/talkinfo/kn_1?authuser=0


https://theaisummer.com/iccv-2023/

Tackling scarce data: https://www.youtube.com/watch?v=XxVwvrfJS5s
Survey on scarce data: https://journalofbigdata.springeropen.com/articles/10.1186/s40537-023-00727-2
Data scarcity and Synthetic data: https://www.infoq.com/articles/overcoming-privacy-challenges-synthetic-data/
Syn Data: https://www.vanderschaar-lab.com/synthetic-data-breaking-the-data-logjam-in-machine-learning-for-healthcare/
