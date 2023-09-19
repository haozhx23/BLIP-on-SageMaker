# BLIP-on-SageMaker

Incremental training of BLIP retrieval model on SageMaker Training Job.

### Infra

- training: ml.p4d.24xlarge

- notebook: ml.c5.xlarge

- notebook EBS: 200GB


### References
1. SageMaker LLM hands-on (manual): https://catalog.us-east-1.prod.workshops.aws/workshops/a3686b6c-2ac4-4f19-925b-8466c331912b

2. BLIP original repo: https://github.com/salesforce/BLIP

3. Kaggle Flickr30k Dataset: https://www.kaggle.com/datasets/adityajn105/flickr30k

4. Sagemaker Examples: https://github.com/aws/amazon-sagemaker-examples

5. SageMaker Distributed Training developer guide: https://docs.aws.amazon.com/sagemaker/latest/dg/distributed-training.html

6. AWS p4 instance deep dive: https://aws.amazon.com/cn/blogs/compute/amazon-ec2-p4d-instances-deep-dive/


### Change Log
1. BLIP/data/flickr30k_dataset.py
use sampled label file to replace original version.

2. BLIP/configs/retrieval_flickr_2.yaml
change the file path on training instances NVME, should use tmp/ as prefix.

3. BLIP/requirements.txt
change dependencies to latest version

4. train_retrieval_2.py
    - L152: cpu/gpu device fix
    - use local rank 0 process to copy resources from s3, including images and labels files
    - use local rank 0 process to copy trained model to s3 for persistant storage
   
5. entry.py
SageMaker global entrance, call main train script and set communication environment for single and multi-instances