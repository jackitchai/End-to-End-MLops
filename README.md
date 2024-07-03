# End-to-End-MLops
### Main idea on this project
- *Setup package*, *Logging*, *Object oriented programming*, *Data pipeline*, *CI/CD*,*AWS EC2*, *MLops*, *MLflow*
## 1.Setting up environment
- create virtual environment with 
```
python3 -m venv myenv
```
- Run `template.py` to create folder and file template
- Install packages on your terminal (Or you can just run command `pip3 install .` for setup.py)
```text
pip3 install -r requirements.txt
```
- at `src/mlProject/__init__.py` write code for logfile in __init__.py
- at `utils/common.py` write code for read_yaml, read_json etc. 

## 2. Update workflow
2.1 Update `config/ config.yaml` -> define the directory and path for each stages\
2.2 Update `schema.yaml` -> specify the data types for each column\
2.3 Update `params.yaml` -> specify the hyperparameter\
2.4 Update `src/entity/config_entity.py` -> define configuration type for different stages\
2.5 Update `src/config/configuration.py` -> read config.yaml and config.entity\
2.6 Update `src/components` -> create component for each stage\
2.7 Update `src/pipeline/` -> connect from every workflow\
2.8 Update the `main.py` -> run pipeline 
### Example of directory structure
```
.
├── setup.py
└── src
    └── mlproject
        ├── components
        │   ├── __init__.py
        │   └── data_ingestion.py
        ├── entity
        └── __init__.py
```
## 3. Data stage
3.1 Data ingestion stage -> Load data from github or kaggle to artifacts folder\
3.2 Data validation stage -> Check columns data type from `schema.yaml`\
3.3 Data transformation stage -> Clean data and split data into `train.csv` and `test.csv`\
3.4 Model training stage -> Train data with ElasticNet model using parameter `from parameter.yaml`\
3.5 Model evaluation stage -> RMSE, R2, MAE metrics for evaluation and connect with MLflow for model experimentation

## 4. Deployment stage
AWS and CI/CD deployment with Github Actions
- Create IAM user for deployment with
```
 1.AmazonEC2ContainerRegistryFullAccess
 2.AmazonEC2FullAccess
```
- Create ECR repo to store and save docker image
- Open EC2 and Install docker in EC2 Machine
- Configure EC2 as self-hosted runner
- Setup github secrets:
```
    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app
```
