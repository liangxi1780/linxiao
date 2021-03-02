# Graph2GO
## Description
This is a graph-based representation learning method for predicting protein functions. We use both network information and node attributes to improve the performance. Protein-protein interaction (PPIs) networks and sequence similarity networks are used to construct graphs, which are used to propagate node attribtues, according to the definition of graph convolutional networks.

We use amino acid sequence (CT encoding), subcellular location (bag-of-words encoding) and protein domains (bag-of-words encoding) as the node attributes (initial feature representation).

The auto-encoder part of our model is improved based on the implementation by T. N. Kifp. You can find the source code here [Graph Auto-Encoders](https://github.com/tkipf/gae). 

## Usage
### Requirements
- Python 3.6
- TensorFlow
- Keras
- networkx
- scipy
- numpy
- pickle
- scikit-learn
- pandas

### Data
You can download the data of all six species from here  data . Please Download the datasets and put the data folder in the same path as thee src folder.

### Steps
#### Step1: decompress data files
> unzip data.zip

#### Step2: run the model
> cd src/Graph2GO     
> python main.py    
> **Note there are several parameters can be tuned: --ppi_attributes, --simi_attributes, --species, --thr_ppi, --thr_evalue, etc. Please refer to the main.py file for detailed description of all parameters**


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)