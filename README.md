# What is the doggest dog? Examination of typicality perception in ImageNet-trained networks

All of the provided method can be used to examine the deep learning models from the perspective of the Prototype Theory. We consider 43 heterogeneous models from different neural network architectures (CNNs, ViTs, hierarchical ViTs, CNN-ViT hybrids and "refreshed" CNNs - ConvNeXts).

## Content of the files in this repository.

Jupyter notebooks with functions, instructions and examples on how to use our methods to determine prototypes and anti-prototypes for a given basic-level category:
* **CODE\strategy_1_example.ipynb**
* **CODE\strategy_2_example.ipynb**
* **CODE\strategy_3_example.ipynb**

Also, in notebook **CODE\strategy_2_experiments.ipynb**, we show our results generation procedures (for all 42 models and strategy 2). Strategy 1 and 3 have been run with the same models and saved to the analogous data structures (we used the same mechanisms). We also provide the csv files (in folder results_csv_files) with our detailed results for all the methods (results per network, and not aggregated as in the paper - based on these results, we computed the values in Tables 2-4 in our paper). In strategy 3, whose results depend on a random initialization, we run experiments 500 times per each (network, basic-level category). For reproducibility, we use numbers generated with numpy.random.randint(0, 5000, size=500) with seed numpy.random.seed(55). We also provide the list of generated numbers (With lenght 500) in file **CODE\random_nums.txt**.   

In **CODE\strategy_3_visualization.ipynb**, we reproduce the graphical results given in the paper. We use there Multidimensional Scaling (single run) to obtain the graphical representation of the typicality with a given category. We use 3 networks: ConvNeXt-S (with category bird), InceptionV3 and SwinV2-S-p4-w16-256 (with category fish). For reproducibility, we use MDS' parameter random_state=77 for the category fish (in both the examined cases), and random_state=55 for the category bird. Figures obtained for all the other models can be found in folder **ADDITIONAL_FIGURES**.

We used methods from file **CODE\counting_model_parameters.ipynb** to compute the number of model parameters.

In folder **DATASET** we include the per-network prototype and anti-prototype datsets that can be used for further analysis in the field of cognitive psychology (e.g. examination of the impact of architectural choices on typicality perception).


## We use the following versions of the Python libraries vital for our work:
* tensorflow (2.12.0)
* torch (2.0.0)
* transformers (4.27.4)
* numpy (1.24.2)
* pandas (2.0.0)
* nltk (3.8.1)
* scikit-learn (1.2.2)
* matplotlib (3.7.1)
* seaborn (0.12.2)