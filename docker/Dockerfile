ARG PYTORCH="1.7.0"
ARG CUDA="11.0"
ARG CUDNN="8"

FROM pytorch/pytorch:${PYTORCH}-cuda${CUDA}-cudnn${CUDNN}-runtime

# install nnUNet:
# https://github.com/MIC-DKFZ/nnUNet#installation
ARG NNUNET="1.6.6"
RUN pip install nnunet==${NNUNET}

# set nnUnet environment variables
# https://github.com/MIC-DKFZ/nnUNet/blob/master/documentation/setting_up_paths.md
RUN echo 'export nnUNet_raw_data_base="/work/nnUNet_raw"' >> /root/.bashrc && \
    echo 'export nnUNet_preprocessed="/work/nnUNet_preprocessed"' >> /root/.bashrc && \
    echo 'export RESULTS_FOLDER="/work/nnUNet_trained_models"' >> /root/.bashrc

WORKDIR /work