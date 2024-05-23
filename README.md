# End-to-End-MLops

Workflows
1. Update config/config.yaml
2. Update schema.yaml
3. Update params.yaml
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

