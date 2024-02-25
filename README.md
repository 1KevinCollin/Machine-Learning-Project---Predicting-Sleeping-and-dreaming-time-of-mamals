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

Tha API has 2 endpoints:
    
    /train
This is the request to perform training on a chatbot. To invoke this service navigate to: _localhost:12345/train_.

Mandatory parameters are:
* **bot_id:** string representation of the chatbot identifier.
* **model_name:** string name of classification model. For this version, HuggingFace models have been considered but are easily extensible to other machine or deep learning models. 
* **sentences:** a list of objects containing natural language text and its corresponding intent. This will constitute the dataset that will be split into training and test sets within the service in a seamless way for the user. The data is also resampled prior to splitting to ensure every intent is represented in both splits.

The API returns an error if any one of these parameters is missing.

The service is designed in a generic manner to cater for different models based on the name (similarly to the HuggingFace API) and can be extended to fall back on default models.

If the training is successful, a message is returned indicating the training is successfully completef. A resource is also created on the server where the model is stored for the specific chatbot. That model can be loaded and used for predictions.

Here is a sample run in Postman. The sample data used is _data/sample_train.json_.

![](./figs/training.png)

    /predict
This is the request to perform prediction on new data. The input is a natural language text and the prediction is an intent. To invoke this service navigate to: _localhost:12345/predict_.

Mandatory parameters are:
* **bot_id:** string representation of the chatbot identifier.
* **model_name:** string name of classification model. For this version, HuggingFace models have been considered but are easily extensible to other machine or deep learning models. 
* **sentences:** a list of objects containing natural language text that needs to be classified as intent.

The API returns an error if any one of these parameters is missing.

If the model doesn't exist, the service will return an error message stating that no such model can be found. This case requires making a **/train** request before performing predictions.

If the prediction is successful, the service returns a message contaaining the list of predicted intents for the input texts.

Here is a sample run in Postman. The sample data used is _data/sample_predict.json_.

![](./figs/prediction.png)

## Enhancements

This version is designed as a proof-of-concept and has been tested on a sample run using very small datasets because of hardware memory constraints. It is by no means a finalized version of the service yet it contains the major components to scale it. Some interesting enhancements may be:
* Packaging the service (using Docker) for easier deployment.
* Extending the available models.
* Adding a GUI for easier dataset upload.
* Extending to more datasets.
* Catering for different models using a cloud repository (ElasticSearch, AWS) or a dedicated database to avoid managing many resource directories on the cloud.
* Tackling data imbalance: the present version undersamples to the least represented intent, but other methods can be implemented before the training/test split.
* Tackling encoding issues: normalizing the datasets since the input text is received in natural language.

## References

* [Fine-tuning with custom datasets](https://huggingface.co/transformers/custom_datasets.html)
* [Hugging Face on Amazon SageMaker Workshop](https://github.com/C24IO/SageMaker-HuggingFace-Workshop)
* [Turning Machine Learning Models into APIs in Python](https://www.datacamp.com/community/tutorials/machine-learning-models-api-python)
* [Know your Intent : Intent Classification Datasets](https://github.com/kumar-shridhar/Know-Your-Intent/blob/master/datasets/NLU-Evaluation-Corpora/AskUbuntuCorpus.json)
