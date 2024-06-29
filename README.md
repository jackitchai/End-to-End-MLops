# End-to-End-MLops
### Main idea on this project
- *setup package*, *logging*, Object Oriented Programming, 
## 1.Setting up environment
- Run `template.py` to create folder and file template
- Install packages on your terminal (Or you can just run only `setup.py` file)
```text
pip3 install -r requirements.txt
```
## 2. Update workflow
1. Update config/ `config.yaml` -> define the directory and path for each stages
2. Update `schema.yaml` -> specify the data types for each column
3. Update `params.yaml` -> specify the hyperparameter
4. Update src/entity/config_entity.py
5. Update src/config/configuration.py
6. Update src/components
7. Update src/pipeline/
8. Update the main.py
9. Update the app.py


import dagshub
dagshub.init(repo_owner='jackitchai', repo_name='End-to-End-MLops', mlflow=True)

import mlflow
with mlflow.start_run():
  mlflow.log_param('parameter name', 'value')
  mlflow.log_metric('metric name', 1)

https://dagshub.com/jackitchai/End-to-End-MLops.mlflow

