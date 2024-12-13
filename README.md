
# BEAT: Adaptive Testing via Gradient-Matching Subset Selection




### Introduction

 Adaptive testing, a tool for efficiently measuring the examinee's ability, has been widely adopted in various various fields, including Education, Healthcare, Sports, and Sociology. It aims to solve a fundamental subset selection problem: selecting a small and appropriate subset of questions from a large question bank for each examinee, ensuring accurate ability estimation. This paradigm enables shorter, more informative tests, reducing both examinee's burden and the system's costs. However, explicitly solving this subset selection problem is infeasible, as the true ability of examinees is unobservable. Consequently, existing selection algorithms cannot be guaranteed to make the ability estimate converge to the true with such limited responses. 
 
We analyze the statistical properties of ability estimators and propose a theoretical approximation of true ability: the ability estimated from responses to the full question bank. Based on this insight, we introduce the Bounded Ability Estimation Adaptive Testing (BEAT) framework in a data-summary manner, which selects question subsets that closely match the gradient of full responses. A simple greedy algorithm is developed to solve this problem approximately. Considering the approximation errors and computational complexity in practical testings, we further design a gradient-path-based training algorithm. 


### Requirements and Dependencies

Install the required dependencies using `pip`:

```bash
pip install -r requirements.txt
```


### Dataset Preparation

1. **Format**: The dataset should be in JSON format, with each record containing input features and corresponding labels.
2. **Example**: A sample dataset is provided in `data/assist2009.json`.
3. **Configuration**: Update `utils/configuration.py` to specify the dataset path and other relevant settings.


### Configuration

The key configurations for model training are defined in `utils/configuration.py`. 

- **`--model`**: Specifies the model type.
- **`--lr`**: Learning rate for the model.
- **`--meta_lr`**: Learning rate for meta-parameters.
- **`--inner_lr`**: Learning rate for the inner optimization loop.
- **`--policy_lr`**: Learning rate for the policy network.
- **`--dataset`**: Dataset to use for training (e.g., 'assist2009', 'eedi-1', 'exam').
- **`--neptune`**: Flag to enable logging to Neptune for experiment tracking (optional).
To customize, edit the parameters directly in the file or use command-line arguments.

### Training

Run the following command to start training:

```bash
python train.py
```
