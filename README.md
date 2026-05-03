# Drug-Likeness Prediction Model with Lipinski's Ro5

## Overview
An end-to-end data science project that predicts whether a compound 
can penetrate the blood-brain barrier (BBB) using Lipinski's Rule of 5 
and a Random Forest classifier.

## Dataset
- **Source:** B3DB (Blood-Brain Barrier Database)
- **Size:** 7,807 compounds
- **Label:** BBB+ (penetrates barrier) / BBB- (does not penetrate)

## Tools Used
- **Python** — pandas, numpy, matplotlib, seaborn, scikit-learn, RDKit
- **Power BI** — interactive dashboard
- **GitHub** — version control

## Key Results
- **Model:** Random Forest Classifier
- **Accuracy:** 86.75%
- **Most important feature:** LogP (fat solubility)
- **Insight:** BBB+ compounds are smaller, more fat soluble, and form fewer hydrogen bonds, which is why they penetrate the blood-brain barrier more easily.

## Dashboard Preview
![Dashboard](c:\Users\felip\drug-likeness-project\output\dashboardprev.png)

The Power BI dashboard presents an interactive summary of both the 
exploratory analysis and machine learning results across ten visuals. 
A class slicer allows filtering of all charts simultaneously by BBB+ 
or BBB- compounds, enabling dynamic exploration of the data.

The distribution pie chart reveals a moderate class imbalance in the 
dataset, with 63.48% of compounds classified as BBB+ and 36.52% as 
BBB-. This imbalance was accounted for during model training through 
stratified splitting. The average Lipinski feature charts show clear 
differences between the two classes — BBB+ compounds are on average 
lighter, more fat soluble, and form fewer hydrogen bonds than their 
BBB- counterparts, which aligns with the known biology of blood-brain 
barrier penetration.

The Lipinski compliance chart confirms that BBB+ compounds show 
significantly higher adherence across all four Ro5 parameters 
simultaneously, reinforcing that drug-likeness is a multidimensional 
property rather than a single threshold. The feature importance chart 
identifies LogP as the strongest predictor of BBB penetration, followed 
by molecular weight, which is consistent with the lipophilic nature of 
the blood-brain barrier membrane.

The model performance visuals show that the Random Forest classifier 
achieved 86.75% accuracy on unseen test data, correctly identifying 
920 out of 992 BBB+ compounds and 435 out of 570 BBB- compounds. The 
confusion matrix reveals that the model performs stronger on BBB+ 
classification, which is expected given the class imbalance in the 
dataset.

## Limitations & Future Work
This project uses Lipinski's Rule of Five (Ro5) as a foundational 
baseline for drug-likeness classification, which has previously been 
used as an initial screening stage in many drug discovery studies. 
Permeability is a crucial property in this context, as it is closely 
tied to adequate ADMET profiles (absorption, distribution, metabolism, 
excretion, and toxicology). Research highlights that Lipinski's Ro5 
thresholds were originally statistical observations rather than absolute 
rules, and their rigid application has historically led to the dismissal 
of viable drug candidates. This is evident in modern 
therapeutic areas such as protein-protein interaction inhibitors, 
PROTACs, and macrocycles, which by necessity require larger molecules. 
growing clinical success of drugs that exceed the 500 Da threshold. 
While modern drug discovery has evolved well beyond Ro5, it remains a 
widely used benchmark for the bioavailability of oral small molecule 
drugs. Future iterations of this project could incorporate ADMET 
property prediction or molecular fingerprint-based features using tools 
like DeepChem or RDKit's Morgan fingerprints for a more comprehensive 
drug-likeness assessment.

## References

1. Purushotham U. Enhanced Discussion on Reassessing Lipinski's Rule 
of Five in the Era of AI-Driven Drug Discovery. *Advanced 
Pharmaceutical Bulletin*. 2025;15(3):474-476. 
doi:10.34172/apb.2025.45948

