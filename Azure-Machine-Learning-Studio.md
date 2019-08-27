## Integrating with Azure Machine Learning Studio

Sesam provides a powerful operational pattern for Machine Learning. This example integrates with Azure Machine Learning Studio for both providing training data, and also operationationalising models via a webservice.

# About Azure Machine Learning Studio (AMLS)
- [Azure Machine Learning Studio](https://studio.azureml.net/?selectAccess=true&o=1#)

# Overview of the pattern
Sesam enables organisations to integrate systems using data driven architecture. The entity datasets created by this process are rich in context and contain both the state of an entity in each system, and a defined master record. The data is strongly namespaced yet schemaless so as to maintain the original state of the data entity along with the merged and shaped version. This setup lends itself very well to the requirements for both training and operationalizing Machine Learning.

![Sesam AMLS](https://github.com/sesam-community/wiki/raw/master/pictures/Sesam%20-%20Azure%20Machine%20Learning%20Studio.png "Sesam Azure Machine Learning Architecture")

# Training Data
A training data set can be provided by re-using a global dataset or perhaps combining some datasets. A Sesam pipe is setup to do shaping task, and is provided by a publisher endpoint to the machine learning system. In this example we use AMLS, and provide data to it using the CSV published endpoint.

Once we have the data sets inside AMLS, the work required to train the scoring models can be completed, tested and evaluated.

At this stage, usually some iterations are required both with the modelling and also with the training data feature sets. Using Sesam to provide the data enables easy continuous improvement of the dataset, and as it is defined in code it is easy to roll forward and back the changes made.

# Operationalising ML
Once the models are ready to be productionized, it is easy with Sesam to enable the pattern where data is sent to the AMLS webservice for processing, with the results placed back into the data hub.

Using the already defined pipe configuration from the training set, we can pipe both the initial load, and from then on the incremental changes to the AMLS web service, quickly and easily. As the global data sets usually merge all the data from each system pertaining to an entity, we use the same pattern with the results from the ML web service. This provides the mechanism and therefore the data flow to propagate and share out the results of ML out to all other systems that may possibly have use for it.

[Sesam microservice for AMLS web services](https://github.com/sesam-community/azure-ml-service)