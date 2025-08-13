# Custom Workbench Images for Red Hat OpenShift AI

This repository was created by the CAI team.
This repository provides a fast way to add a collection of community-contributed Custom Workbench Images for Red Hat OpenShift AI (RHOAI), helping you get to work faster with specialized tools and libraries.

These images extend the functionality of your RHOAI environment with additional tools and capabilities that can be immediately accessed by all users.

They are not part of the core product, and therefore, do not fall under the support umbrella of OpenShift AI.


### Architecture

![OpenShift AI Workbenches](assets/images/simple-arch-diag.png)

## Available Images

The following custom workbench images are available in this collection. For the full list of available images, see the [`imagestreams`](./imagestreams) directory.

### [AnythingLLM](./imagestreams/AnythingLLM-Custom-Workbench-Image.yaml)

- **Description**: A powerful chatbot frontend that easily connects to Large Language Models.
- **Key Features**:
  - OpenAI-compatible API integration
  - User-friendly chat interface
  - Customizable chat experience
- **Use Cases**:
  - Quickly build and deploy conversational AI applications
  - Test and iterate on different LLMs
  - Create interactive demos and prototypes
- **GitHub Repository**: [llm-on-openshift/anythingllm](https://github.com/rh-aiservices-bu/llm-on-openshift/tree/main/llm-clients/anythingllm)

### [ODH-TEC](./imagestreams/ODH-TEC-Custom-Workbench-Image.yaml)

- **Description**: An enhanced data science workbench with integrated S3 capabilities for seamless data access.
- **Key Features**:
  - Web-based S3 browser
  - Integrated data science tools
  - Streamlined data access
- **GitHub Repository**: [odh-tec](https://github.com/opendatahub-io-contrib/odh-tec)

## Getting Started

Follow these steps to install and use the custom workbench images in your Red Hat OpenShift AI environment. For detailed installation instructions, see the documentation in the [`imagestreams`](./imagestreams) directory.

### Prerequisites

Before you begin, ensure you have the following:

- Red Hat OpenShift cluster with administrator access
- Red Hat OpenShift AI (RHOAI) installed and configured
- `oc` CLI tool installed and logged in with cluster-admin privileges

### Installation

You can install all images at once or individually from the [`imagestreams`](./imagestreams) directory based on your needs.

#### Install All Images

To install all available custom workbench images, run the following command:

```bash
# Apply all custom workbench images
oc apply -k https://github.com/rh-ai-kickstart/custom-workbench-images-examples/imagestreams/
```

#### Install Individual Images

To install a specific image, use the appropriate command below:

```bash
# Set the base URL for individual image streams
URL='https://raw.githubusercontent.com/rh-ai-kickstart/custom-workbench-images-examples/main/imagestreams'

# Install AnythingLLM
oc apply -f ${URL}/AnythingLLM-Custom-Workbench-Image.yaml

# Install ODH-TEC
oc apply -f ${URL}/ODH-TEC-Custom-Workbench-Image.yaml
```

## Usage

After installation, the new images will be available in the RHOAI dashboard. Users can select them when creating or configuring workbenches, just as they would with the default images.

### Uninstallation

To remove all custom workbench images added by this repository, run the following command:

```bash
oc delete -k https://github.com/rh-ai-kickstart/custom-workbench-images-examples/imagestreams/
```

## Community

### Contributing

We welcome contributions to expand this collection of custom workbench images. If you have an image that would be useful to the community, please open a pull request with your proposed changes.

### Support

These images are provided by the community and are not officially supported by Red Hat. They are provided as-is, and while we strive for quality, there is no guarantee of support. If you encounter issues, please check the respective GitHub repositories or open an issue in this repository. 

