# End-to-End-MLops
### Main idea on this project
- *Setup package*, *Logging*, Object Oriented Programming, 
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
- write code for log file at `src/mlProject/__init__.py`
- create `utils/common.py` for read_yaml, read_json etc. 

## 2. Update workflow
1. Update config/ `config.yaml` -> define the directory and path for each stages
2. Update `schema.yaml` -> specify the data types for each column
3. Update `params.yaml` -> specify the hyperparameter
4. Update src/entity/`config_entity.py` -> define configuration type for different stages
5. Update src/config/`configuration.py` -> read config.yaml and config.entity
6. Update src/components -> create component for each stage
7. Update src/pipeline/ -> connect from every workflow
8. Update the main.py -> run pipeline 


import dagshub
dagshub.init(repo_owner='jackitchai', repo_name='End-to-End-MLops', mlflow=True)

import mlflow
with mlflow.start_run():
  mlflow.log_param('parameter name', 'value')
  mlflow.log_metric('metric name', 1)

https://dagshub.com/jackitchai/End-to-End-MLops.mlflow

