# Workflow

Describe your overall workflow here.

Discuss (in detail) the processes of

* Getting the data
* Cleaning/altering the data
* Visualizing the data

	The author chose to analyze the emails of Hillary Clinton released by WikiLeaks out of a desire to work on a project that possessed political dimensions. The author received a copy of the emails from Prof. David J. Thomas, in both a CSV and TXT format. While Prof. Thomas sent all the emails from WikiLeaks (roughly eighteen thousand) to this author, the author’s computer was unable to process such a large dataset in Orange 3, which forced him to reduce the CSV file to approximately three thousand emails. The author used Orange 3 to analyze the data because it gave him the ability to use hierarchical clustering for text analysis - a technical description of the technique can be found [here](https://docs.orange.biolab.si/3/data-mining-library/reference/clustering.hierarchical.html) – which was useful given the large amount of emails (Orange, n.d.). Finally, the author reduced the TXT file to 2,000 emails so he could use Voyant-tools, a text analysis tool that divides a corpus into groups to aid analysis of large datasets [(Voyant Tools, n.d.)](https://voyant-tools.org/docs/#!/guide/about). 
	
	Once the author reduced the size of the files, he used Orange 3 and Voyant-tools to analyze them. In Orange, the author used a “Corpus” widget to view the CSV, ran it through “Preprocess Text” to clean up the file, then put it into “Bag of Words” so it would have a numerical value. After putting Clinton’s emails through the “Bag of Words” widget, the author put it in “Distances,” so it would group emails with similar words together, and then ran it through “Hierarchical Clustering” to make the email clusters visible to the author.


What you need to cover: Talk about every step in your process, talk about how and why you made the decisions that you did. Why did you pick the website that you did? Did you download every record, or just some? Did you download the data directly from the website, or did you use a tool like Webscraper.io? Did you use OpenRefine to change the raw data in some form, and if so, why did you change it the way you did? What program(s) or techniques did you decide on to visualize or analyze it? Why did you feel those programs (e.g. Tableau or Gephi) were better than other options, given your research interest? Did you have to do anything to the data inside Tableau?

To make elegant workflow charts, use [LucidChart](https://lucidchart.com)

Take plenty of screenshots to document your process...
    * **Mac** press 'command' + 'shift' + '4' and then drag a rectangle to take a screenshot of whatever you select... On
    * **Windows**, click the 'Start' button then type 'Snipping' and select Snipping Tool, then click 'New' and drag a rectangle to take a screenshot of whatever you select.
