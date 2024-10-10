# Town Mice versus Country Mice: Urban Bias in Job Recommender Systems

The notebooks used to generate the results for both datasets can be found in their respective folders. No data is provided for the proprietary dataset. For the Zhaopin dataset, the [original data](https://tianchi.aliyun.com/dataset/31623) should be stored in `/zhaopin/source_data/`. 

All notebooks related to data pre-processing (both retrieving it from the datalake/dataset, as well as converting it into the proper formats) can be found in the `/data_processing` sub-folders of both datasets.

For both datasets, the order in which the notebooks should be run is then as follows:

- `kg_builder.ipynb` to convert the original data to a knowledge graph using a custom ontology
- `sub_graph_generator.ipynb` to split this single large knowledge graph into multiple candidate-vacancy sub-graphs that will be ranked by the models
- `graph_data_builder.ipynb` to convert these sub-graphs into a PyTorch dataloader
- `Baselines.ipynb` to train all of the baselines used in the paper
- `Okra.ipynb` to train our novel model, _OKRA_
- `Evaluation.ipynb` to evaluate the performance and fairness of the baselines and OKRA. The optimal hyperparameters are stored in the *_config dictionaries in this file.
