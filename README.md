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

* [Sleep in mammals: ecological and constitutional correlates](https://pubmed.ncbi.nlm.nih.gov/982039/)
* [A quantitative, theoretical framework for understanding mammalian sleep](https://pubmed.ncbi.nlm.nih.gov/17215372/)
