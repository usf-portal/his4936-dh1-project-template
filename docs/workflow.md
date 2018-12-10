# Workflow



I chose to analyze the emails of Hillary Clinton released by WikiLeaks out of a desire to work on a project that possessed political dimensions. I received a copy of the emails from Prof. David J. Thomas, in both a CSV and TXT format. While Prof. Thomas sent all the emails from WikiLeaks (roughly eighteen thousand) to me, my computer was unable to process such a large dataset in Orange 3, which forced me to reduce the CSV file to approximately three thousand emails. I used Orange 3, a toolkit for Python, to analyze the data because it gave me the ability to use hierarchical clustering for text analysis - a technical description of the technique can be found [here](https://docs.orange.biolab.si/3/data-mining-library/reference/clustering.hierarchical.html) – which was useful given the large size of the dataset [(Demsar, et al., 2013]( https://orange.biolab.si/citation/) and [Orange, n.d.](https://docs.orange.biolab.si/3/data-mining-library/reference/clustering.hierarchical.html)).  
	
![Orange Worklfow](imgs/workflow.png)
	
	
Once I reduced the size of the files, I used Orange 3 to analyze them. In Orange, I used a “Corpus” widget to view the CSV, ran it through “Preprocess Text” to clean up the file, then put it into “Bag of Words” so it would have a numerical value [(Demsar, et al., 2013]( https://orange.biolab.si/citation/). After putting Clinton’s emails through the “Bag of Words” widget, I put it in “Distances,” to calculate how similar emails were to each other based on word use, and then ran it through “Hierarchical Clustering” to ensure Orange3 put emails with similar content in the same cluster [(Demsar, et al., 2013]( https://orange.biolab.si/citation/).
	
	
	


