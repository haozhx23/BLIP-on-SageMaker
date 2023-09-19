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
