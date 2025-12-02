# Custom Workbench Dockerfiles  
Some images in this repository are not published to a public registry, but you can build them yourself using the provided recipes. This approach lets you customize the Dockerfile to meet your requirements. 

To build an image, run make with the desired target; the resulting local image will be ready for use. 

To use the image in OpenShift AI, apply an ImageStream from the `imagestreams` directory, then push the image to the OpenShift cluster.

Currently available workbench dockerfiles:
 - Gaudi-PyTorch
	- Name: `pytorch-installer-rhel9.6.rhoai.pytorch-2.7.1:1.22.1-6`
	- OS: `RHEL 9.6`
	- PyTorch: `2.7.1`
	- Gaudi PyTorch modules: `1.22.1-6`
	- Habanalabs hl-smi: `hl-1.22.1-fw-61.4.2.1`
	- Habanalabs Driver: `1.20.0-bd87f71`
 - Gaudi-DataScience
	- Name:  `pytorch-installer-rhel9.6.rhoai.datascience-2.7.1:1.22.1-6`
	- OS: `RHEL 9.6`
	- PyTorch: `2.7.1`
	- Gaudi PyTorch modules: `1.22.1-6`
	- Habanalabs hl-smi: `hl-1.22.1-fw-61.4.2.1`
	- Habanalabs Driver: `1.20.0-bd87f71`

# Building Dockerimage 

Use make to build desired target dockerimage.

```bash
# Gaudi-PyTorch
# - pytorch-installer-rhel9.6.rhoai.pytorch-2.7.1:1.22.1-6
make gaudi-pytorch

# Gaudi-DataScience
# - pytorch-installer-rhel9.6.rhoai.datascience-2.7.1:1.22.1-6 
make gaudi-datascience
```

