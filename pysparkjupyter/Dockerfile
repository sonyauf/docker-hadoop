FROM jupyter/pyspark-notebook:latest

RUN pip install jupyterlab_sql_editor &&\
    sudo docker cp Twitter_model_training.ipynb pysparkjupyter:/home/jovyan/ &&\
    sudo docker cp Twitter_data_processing.ipynb pysparkjupyter:/home/jovyan/

#COPY Twitter_data_processing.ipynb Twitter_model_training.ipynb /home/jovyan/
