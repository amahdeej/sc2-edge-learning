# Knowledge Distillation For Wireless Edge Learning
This repository contains the code for frame error prediction in an wireless edge learning framework. The node based dataset for 

Spectrum Challange 2 Dataset and Frame Error Prediction Code
Deep Learning for Frame Error Prediction using a DARPA Spectrum Collaboration Challenge (SC2) Dataset.

# Code
SC2-Nodes-Edge-Learning.ipynb contains the experiments. Analyze-Results.ipynb uses the results saved by the experiments to generate the plots and statistics. The paper contains more details.

# Dataset
The dataset is approved for public release, distribution unlimited.

The dataset contains information obtained from Software Radio Nodes(SRN) nodes from a Collaborative Intelligent Radio Network (CIRN), that participates in spectrum sharing with 4 other CIRNs in the Colosseum emulator. 

There are a total of 14 environments. Based on the channel allocation strategy, the dataset is divided in two files - scrimmage4_nodes_dataset.pickle and scrimmage5_nodes_dataset.pickle. In Scrimmage 4, the channel allocation decision parameters are randomized. There are a total of 25 matches in scrimmage 4 and 53 matches in scrimmage 5. Only nodes with more than 10000 transmitted frames are considered, resulting in 154 and 408 nodes for scrimmages 4 and 5, respectively. We also include the SMOTE generated synthetic training dataset we used to train the teacher network in the cloud. This dataset is produced using only the training data (50%) from the original dataset nodes, and hence contains same no of nodes.

The pickle files are stored as list of tuples, each list corresponding to a single node, and containing two elements. Each element a length equal to the number of frames in that node - it varies between node to node.
The first tuple is contains the paramenters -
1. Signal to Noise Ratio ('snr') - 1 element
2. The Modulation and Coding Scheme ('mcs') - 1 element
3. The center frequency of the link ('centerFreq') - 1 element
4. The bandwidth of the link ('bandwidth') - 1 element
5. The Power Spectral Density ('psd') - 16 elements
Thus the total width of each element of the first tuple for a link is 20.

The second tuple contains the success of transmission ('rxSuccess'). If it is 1, there is no frame error, if it is 0, there is a frame error.

Here are the links to the dataset files mentioned in the code (one pickle file for each scrimmage):

[Scrimmage 4 Edge Node Dataset](https://purdue0-my.sharepoint.com/:u:/g/personal/amahdeej_purdue_edu/EY7bz-bskWlKpXkOQ0cTIh8BsBqaQLMqMNiUjbaIg_hkNg) (573.7 MB) [Mirror](https://app.box.com/s/rpas6y19ret8mqbow558cyoawex0bb29)

[Scrimmage 5 Edge Node Dataset](https://purdue0-my.sharepoint.com/:u:/g/personal/amahdeej_purdue_edu/EW5CM_Q1tpdFoLmVp6L2D_kBt8BM6ME8AZOr7QKJr-IpoA) (982 MB) [Mirror](https://app.box.com/s/z1dvzfy3x51obvh75mzru0hssc26pc5x)

[Scrimmage 4 Edge SMOTE Training Dataset](https://purdue0-my.sharepoint.com/:u:/g/personal/amahdeej_purdue_edu/EROusY6XYOtInGVCqgg66OEBCpzGMrZec70RCRKs_xsnEA) (547.7 MB) [Mirror](https://app.box.com/s/ppppg7isycr3og1m9wsotysxumcf9qvh)

[Scrimmage 5 Edge SMOTE Training Dataset](https://purdue0-my.sharepoint.com/:u:/g/personal/amahdeej_purdue_edu/EXunZUqirGtDpNmEd5U8f5MB2Nu2-ZCGVL5W5IDhHNR4Ew) (937.4 MB) [Mirror](https://app.box.com/s/cgv5yzgqe558q2j6gj9mlfpr29xrcwsv)

A larger dataset containing complete information about each match is also available [here](https://github.com/amahdeej/sc2-frame-error). Please refer to [SC2 Dataset Documentation](https://github.com/amahdeej/sc2-frame-error/blob/master/SC2_Dataset_Documentation.pdf) for more details regarding the structure of the dataset, and [SC2 Technical Design Report](https://github.com/amahdeej/sc2-frame-error/blob/master/SC2_Dataset_Technical_Design_Report.pdf) for details about the technical specifications.
