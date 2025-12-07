# MSCS_634_ProjectDeliverable_3

In this deliverable I expanded my analysis of the Student Performance dataset by building classification models, clustering students into meaningful groups, and applying association rule mining to uncover hidden patterns. The goal was to move beyond prediction and understand how different characteristics relate to performance.

## Classification
I trained a tuned Decision Tree and a KNN classifier to predict whether a student passes or fails.  
- The **Decision Tree** performed best with ~91.5% accuracy and a strong AUC of 0.966.  
- The **KNN model** reached ~81.5% accuracy with an AUC of 0.901.  

The Decision Tree consistently outperformed KNN and handled the pass/fail separation much more effectively. Hyperparameter tuning helped me control model complexity and improve generalization.

## Clustering
Using KMeans (k=3), I grouped students based on study time, absences, alcohol use, and final grade.  
The clusters naturally separated into:
- Higher study time + higher grades  
- Middle-performing students  
- Lower study time + lower grades  

This gives a quick way to identify at-risk groups or high-performing students without using labels.

## Association Rule Mining
Using Apriori, I generated rules related to **high performance**.  
The most common patterns included:
- Attending **school_GP**  
- Wanting higher education (`wants_higher_edu`)  
- Certain family or lifestyle traits appearing in smaller subsets  

Lift values above 1 show these factors increase the likelihood of high performance, even if the relationships are not extremely strong.

## Key Insights
- Motivation and school environment matter: students at GP and those aiming for higher education show better outcomes.
- Study behavior strongly aligns with performance, which clustering made very clear.
- Simple models like Decision Trees can perform extremely well when the right features and tuning are applied.

## Challenges
The main challenges were handling class imbalance, selecting meaningful features for clustering, and choosing appropriate binary transformations for association rules. I addressed these by using stratified splits, testing multiple feature combinations, and tuning Apriori thresholds.
