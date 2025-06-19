# Custom Workbench Images for Red Hat OpenShift AI

This repository provides a fast way to add a collection of community-contributed Custom Workbench Images for Red Hat OpenShift AI (RHOAI).

These images extend the functionality of your RHOAI environment with additional tools and capabilities that can be immediately accessed by all users.

They are not part of the core product, and therefore, do not fall under the support umbrella of OpenShift AI.

## Detailed description

Red Hat OpenShift AI comes with several Red Hat-provided Workbench images out of the box. This collection supplements those with additional custom workbench images that add specialized tools and capabilities for specific use cases.

### Architecture diagrams

![OpenShift AI Workbenches](assets/images/simple-arch-diag.png)

### Available Images

#### AnythingLLM
- **Description**: A powerful chatbot frontend that easily connects to Large Language Models
- **Key Features**:
  - OpenAI-compatible API integration
  - User-friendly chat interface
  - Customizable chat experience
- **Github Repository**: https://github.com/rh-aiservices-bu/llm-on-openshift/tree/main/llm-clients/anythingllm

#### ODH-TEC
- **Description**: Enhanced data science workbench with S3 capabilities
- **Key Features**:
  - Web-based S3 browser
  - Integrated data science tools
  - Streamlined data access
- **Github Repository**: https://github.com/opendatahub-io-contrib/odh-tec

## Requirements

Before installing these custom workbench images via this Kickstart, ensure you have:

- Red Hat OpenShift cluster with administrator access
- Red Hat OpenShift AI (RHOAI) installed and configured
- `oc` CLI tool installed and configured
- Cluster-admin privileges

## Installation

You can install all images at once or individually based on your needs.

### Install All Images

```bash
# Apply all custom workbench images
oc apply -k https://github.com/rh-ai-kickstart/custom-workbench-images-examples/imagestreams/
```

### Install Individual Images

```bash
# Set the base URL for individual image streams
URL='https://raw.githubusercontent.com/rh-ai-kickstart/custom-workbench-images-examples/refs/heads/main/imagestreams/'

# Install AnythingLLM
oc apply -f ${URL}/AnythingLLM-Custom-Workbench-Image.yaml

# Install ODH-TEC
oc apply -f ${URL}/ODH-TEC-Custom-Workbench-Image.yaml
```

## Uninstall Images

To remove all Kickstart-added custom workbench images:

```bash
oc delete -k https://github.com/rh-ai-kickstart/custom-workbench-images-examples/imagestreams/
```

## Usage

After installation, the custom workbench images will be available in your RHOAI dashboard. Users can select these images when creating new workbenches through the RHOAI interface.

## Additional information

### Contributing

We welcome contributions! If you have a custom workbench image that could benefit the community, please consider submitting a pull request.

### Support

These images are community-contributed. While we strive to maintain quality and functionality, they are provided as-is without official support.

### Categories

This project falls into the following categories:

- AI
- Workbench Images
- RHOAI
- OpenShift

### Tags

- custom-workbench
- oc-apply
- test
