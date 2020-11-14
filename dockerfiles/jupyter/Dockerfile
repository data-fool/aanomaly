FROM jupyter/scipy-notebook

USER root

COPY requirements.txt /tmp/
RUN pip3 install --requirement /tmp/requirements.txt && \
    fix-permissions $CONDA_DIR && \
    fix-permissions /home/$NB_USER && \
    apt update && \
    apt-get install curl -y

ENV PYTHONPATH "${PYTHONPATH}:/home/jovyan/work/aanomaly"
    
CMD ["jupyter", "notebook", "--no-browser","--NotebookApp.token=''","--NotebookApp.password=''", "--allow-root"]