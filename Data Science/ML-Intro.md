- AI, DL, ML, DS difference
- **AI** → create applications that perform on it's own without human intervention
- **ML** → machines learning from data.
- **DL** → ML using neural networks (deep layers).
- **DS** → working with data (may use ML/DL, but also stats, analysis, visualization, forecasting etc).
	AI (biggest)
	 └── ML (subset of AI)
	       └── DL (subset of ML)
	DS (overlaps with all, uses them for insights, analysis)
# ML Techniques
- 3 types
1. Supervised Ml
	- trains on both <mark style="background: #FFF3A3A6;">Independent features(input)</mark> and <mark style="background: #FFF3A3A6;">Depended features (output)</mark>
	- types
		1. Regression (Dependent features -> continuous)
		2. Classification (Dependent features -> Categorical)
			- only 2 categories -> Binary Classification
			- multiple categories -> Multiclass Classification
2. Unsupervised Ml
	-  trains only on Independent features (input) 
	- Goal is to find output -> to find clusters/ groups
		- ex:  gender based on shopping 
		- salary based on spending
3. Reinforcement Learning
	- Application will learn itself by Rewards
- ![[Pasted image 20250908164344.png]]
# Equation of Line, 3d plane and Hyperplane(n dimensions)
- PDF Notes- [D:\DS\Complete-Data-Science-With-Machine-Learning-And-NLP-2024-main\Complete-Data-Science-With-Machine-Learning-And-NLP-2024-main\2-Introduction\2.3- Equation Of a straight Line,Hyperplane.pdf](file:///d%3A/DS/Complete-Data-Science-With-Machine-Learning-And-NLP-2024-main/Complete-Data-Science-With-Machine-Learning-And-NLP-2024-main/2-Introduction/2.3-%20Equation%20Of%20a%20straight%20Line%2CHyperplane.pdf)
- equation of straight line (2d or nd(plane)) ![[Pasted image 20250916112156.png]]
- ![[Pasted image 20250916112221.png]] equation of nd plane / straight line
	![[Pasted image 20250916112258.png]]
- equation of plane passing through origin
	![[Pasted image 20250916112325.png]]   ![[Pasted image 20250916112402.png]]
- w is perpendicular to x (plane) and dot product of 'x' and 'w' is the plane equation
# Distance of point from Hyperplane
- to divide points into two categories we need to find a line than separates them well 
	![[Pasted image 20250916112053.png]]
- equation of plane ![[Pasted image 20250916112553.png]]
- consider two points s and s' on opposite sides of plane
	- ![[Pasted image 20250916112539.png]]
	- distance of point from plane ![[Pasted image 20250916112623.png]]
	- distance is +ve if cos is +ve (if w and the point or on same side)
		- w and s are on same side -> distance +ve
		- w and s' are on opposite side -> distance -ve
- to find a line exactly between two points, the sum of distances ~ 0
# Instance based learning vs Model Based Learning
- Instance based
	- model memorizes (by hearting)
- Model based
	- model generalizes (finds patterns)

| Usual/Conventional Machine Learning                                                | Instance Based Learning                                                                                   |
| ---------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Prepare the data for model training                                                | Prepare the data for model training. No difference here.                                                  |
| Train model from training data to estimate model parameters i.e. discover patterns | Do not train model. Pattern discovery postponed until scoring query received                              |
| Store the model in suitable form                                                   | There is no model to store                                                                                |
| Generalize the rules in form of model, even before scoring instance is seen        | No generalization before scoring. Only generalize for each scoring instance individually as and when seen |
| Predict for unseen scoring instance using model                                    | Predict for unseen scoring instance using training data directly                                          |
| Can throw away input/training data after model training                            | Input/training data must be kept since each query uses part or full set of training observations          |
| Requires a known model form                                                        | May not have explicit model form                                                                          |
| Storing models generally requires less storage                                     | Storing training data generally requires more storage                                                     |
| Scoring for new instance is generally fast                                         | Scoring for new instance may be slow                                                                      |
|                                                                                    | KNN,                                                                                                      |
 