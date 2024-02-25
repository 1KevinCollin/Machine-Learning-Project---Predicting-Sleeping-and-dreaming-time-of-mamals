# Machine Learning Porject - Sleeping and dreaming time prediction for mamals
A machine learning project to predict the sleeping and dreaming time of mamals.

## Installation (local)

* Install requirements for Sleeping time prediction
```
pip install -r requirements-Sleeping_time_prediction.txt
```
* Install requirements for Dreaming Time prediction
```
pip install -r requirements-Dreaming-time-prediction.txt
```
* Install requirements for Other correlations explanation
```
pip install -r requirements-Other_correlations_explanation.txt
```
---

* Start the service in the virtual environment using the command
```
python app.py
```


## Functionality

This project is plit in 4 repositories parts :
* Data : The used dataset
* Sleeping time prediction : three programs that predict the sleeping time of a mammal, based on three different methods to fill the missing values
* Dreaming Time prediction : one program that predict the dreaming time of a mammal
* Other correlations explanation : one program that study the relations between general, ecological biological and sleep attributes of a mamal

The data at our disposal to make predictions are from two scientific papers :
* Allison T, Cicchetti DV. Sleep in mammals: ecological and constitutional correlates. Science. 1976 Nov 12;194(4266):732-4. doi: 10.1126/science.982039. PMID: 982039.
* Savage VM, West GB. A quantitative, theoretical framework for understanding mammalian sleep. Proc Natl Acad Sci U S A. 2007 Jan 16;104(3):1051-6. doi: 10.1073/pnas.0610080104. Epub 2007 Jan 10. PMID: 17215372; PMCID: PMC1783362.

Below, the list of the used attributes used to apply machine learning algorythms:
* Species: name of the species
* Order: lower taxonomic rank
* Genus: higher taxonomic rank
* Vore: Is it carnivore, omnivore, or herbivore?
* Conservation: the conservation status of the mammal in the International Union for
* Conservation: of Nature categories
* BodyWt: body weight (kg)
* BrainWt: brain weight (g)
* LifeSpan: maximum life span (years)
* Gestation: gestation time (days)
* Predation: predation index (1-5) 
* Exposure:  sleep exposure index (1-5) 
* Danger:  overall danger index (1-5) 
* TotalSleep: total sleep, sum of slow wave and paradoxical sleep (hrs/day)
* Awake: amount of time spent awake (hrs/day, Awake=24-TotalSleep)
* NonDreaming: slow wave ("nondreaming") sleep (hrs/day)
* Dreaming: paradoxical ("dreaming") sleep (hrs/day) 

To enhance this dataset, we decided to add the family from the taxonomy for each mamal.



## Enhancements

* If the scientific community were to create a larger and more robust dataset in the future, we could improve our predictions of TotalSleep or Dreaming, by adding more mamals.
* We could also enhance the process of filling in missing values using libraries from scikit-learn, such as sklearn.impute.SimpleImputer or sklearn.impute.KNNImputer, to obtain a more robust dataset. 


## References

* [Fine-tuning with custom datasets](https://huggingface.co/transformers/custom_datasets.html)
* [Hugging Face on Amazon SageMaker Workshop](https://github.com/C24IO/SageMaker-HuggingFace-Workshop)
* [Turning Machine Learning Models into APIs in Python](https://www.datacamp.com/community/tutorials/machine-learning-models-api-python)
* [Know your Intent : Intent Classification Datasets](https://github.com/kumar-shridhar/Know-Your-Intent/blob/master/datasets/NLU-Evaluation-Corpora/AskUbuntuCorpus.json)
