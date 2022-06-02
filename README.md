# DevNet: An End-to-end Anomaly Score Learning Network

By Guansong Pang, Chunhua Shen, Anton van den Hengel. Deep anomaly detection with deviation networks (KDD19).

This repository modified the [source code](https://github.com/GuansongPang/deviation-network) to test the model on Fraud dataset. Parameters are set to test it under the same conditions as models in [GitHub - odilecooper/Anomaly_Detection_Comparison](https://github.com/odilecooper/Anomaly_Detection_Comparison).

Results and comparisons are also in the respository above.

## Usage

To run the training and testing, first unzip Fraud dataset in Data/.

Then run

```python
python devnet.py --network_depth=2 --runs=10 --known_outliers=394 --cont_rate=0.02 --data_format=0 --output=./results.csv --dataset='creditcardfraud_normalised'
```

See devnet.py for more details about each argument used in this line of code.

The key packages and their versions used in our algorithm implementation are listed as follows

- python==3.6.6
- keras==2.2.4
- tensorflow-gpu==1.10.0
- scikit-learn==0.20.0
- numpy==1.14.5
- pandas==0.23.4
- scipy==1.1.0
- tensorboard==1.10.0

See the full paper below for the implemenation details of DevNet.

## Brief Introduction

Deviation network (DevNet) is introduced in our KDD19 paper, which leverages a limited number of labeled anomaly data and a large set of unlabeled data to perform end-to-end anomaly score learning. It addresses a weakly supervised anomaly detection problem in that the anomalies are partially observed only and we have no labeled normal data.

Unlike other deep anomaly detection methods that focus on using data reconstruction as the driving force to learn new representations, DevNet is devised to learn the anomaly scores directly. Therefore, DevNet directly optimize the anomaly scores, whereas most of current deep anomaly detection methods optimize the feature representations. The resulting DevNet model achieves significantly better anomaly scoring than the competing deep methods. Also, due to the end-to-end anomaly scoring, DevNet can also exploit the labeled anomaly data much more effectively.

## Full Paper

The full paper can be found at [ACM Portal](https://dl.acm.org/citation.cfm?id=3330871) or [arXiv](https://arxiv.org/abs/1911.08623)

## Datasets

The datasets used in DevNet are also released here. See our anomaly detection dataset repository [ADRepository](https://github.com/GuansongPang/anomaly-detection-datasets) for more preprocessed datasets that are widely-used in other papers.

## Citation

```bibtex
@inproceedings{pang2019deep,
  title={Deep anomaly detection with deviation networks},
  author={Pang, Guansong and Shen, Chunhua and van den Hengel, Anton},
  booktitle={Proceedings of the 25th ACM SIGKDD international conference on knowledge discovery \& data mining},
  pages={353--362},
  year={2019}
}
```
