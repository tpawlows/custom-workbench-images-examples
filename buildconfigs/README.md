# Custom Workbench BuildConfigs

Some workbench images in this repository are not available in public registries and must be built directly on your OpenShift cluster using BuildConfigs. This approach allows you to customize the build process and integrate the images seamlessly into your OpenShift AI environment.

## Available Workbench BuildConfigs

The following workbenches require building on OpenShift:

### Gaudi-PyTorch
- **Image Name**: `ai-quickstart-image-gaudi-pytorch:1.22.1-6`
- **Base OS**: RHEL 9.6
- **PyTorch**: 2.7.1
- **Gaudi PyTorch Modules**: 1.22.1-6
- **Habanalabs hl-smi**: hl-1.22.1-fw-61.4.2.1
- **Habanalabs Driver**: 1.20.0-bd87f71

### Gaudi-DataScience
- **Image Name**: `ai-quickstart-image-gaudi-datascience:1.22.1-6`
- **Base OS**: RHEL 9.6
- **PyTorch**: 2.7.1
- **Gaudi PyTorch Modules**: 1.22.1-6
- **Habanalabs hl-smi**: hl-1.22.1-fw-61.4.2.1
- **Habanalabs Driver**: 1.20.0-bd87f71

## Building Images on OpenShift

When you apply a BuildConfig using `oc apply`, OpenShift automatically triggers a build process. The built image is stored in the internal registry and becomes available for use in OpenShift AI workbenches. Once the build completes successfully, **the workbench will automatically appear in the RHOAI dashboard and is ready to use, no additional configuration or steps are required.**

### Build All Workbenches

To build and install all workbench images on your OpenShift cluster:

```bash
oc apply -k .
```

### Build Individual Workbenches

To build a specific workbench image:

```bash
# Build and install Gaudi-PyTorch
oc apply -k gaudi-pytorch

# Build and install Gaudi-DataScience
oc apply -k gaudi-datascience
```

## Uninstalling

Remove the BuildConfigs and associated resources:

```bash
# Remove all BuildConfigs and ImageStreams
oc delete -k .

# Remove individual BuildConfigs
oc delete -k gaudi-pytorch
oc delete -k gaudi-datascience
```
