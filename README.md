# datsci_project
Data Science Project (Uniprot Subcellular)

This project is to train a classfier to read a protein sequence (one letter codes), and to classify specific subcellular locations where the protein that the sequence codes for is found. This is done using SKLearn libraries and the Uniprot Online Database as the data source. Overall, the classifier sucks, scoring a ROC of 0.58 (chance being 0.5). Issues thoughout the project included an inability to download data from Uniprot (thus a table of raw data is included in this repo), issues with the classifier not liking the multiclass output (multiclass output vs multioutput continuous error), and similar problems with the graphing (leading to no iteratirative graph possible, please attempt yourself as I have spent hours trying to do it). The confusion matrix shows that the classifier classifies everything as amembrane, this is because the uniport database sometimes specifies things as “membrane” and sometimes as a more specific element (“cell membrane”) or even more specifically “inner cell membrane”. In hindsight, a model organism with a better filled out database (three quarters of entries were “unknown”) would have been better to write this program about, and perhaps the classifier would have scored something approaching acceptable. I have spent several days’ work devoted to trying to get this to work however.

Files located in this repository:
  - Data_Sci_project.ipynb
  - 83332.tsv (the dataset)

This project is pipelined from within the notebook file.

The dataframe cleaning process is CPU intensive as I could not find an acceptable regex solution, due to the inconsisent way subcellular locations are documented within Uniprot. On a 8GB RAM laptop, it takes about 3 minutes to run.

Ngram explanation: As a machine learning neural network does not naturally associate neighbouring residues as interacting and thus clusters of nearby residues being significant, ngram-vectorisation was used instead. This allows the network some crude insight into potentially significant regions in the sequence by forcing it to group all nearby residues together naively. From these extended strings, it is hoped that the network can derive important patterns based not only on amino acid content but also the local environment of amino acid residues.  

All the best Tristan, hopefully you can give me credit for the strech-goal.
