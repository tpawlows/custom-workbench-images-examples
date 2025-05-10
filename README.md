# custom-workbench-images-examples

Welcome to the Custom Workbench Images AI kickstart!

This AI Kickstart will quickly add a number of community-provide Custom Workbench Images into your RHOAI environment.

These images will immediately be available to all your OpenShift AI users.

## Description

While OpenShift AI comes with a number of Red Hat-provided images, it can be useful to supplement them with Custom Workbench Images.

### List of images and main features

* ODH-TEC: S3 web-based browser
* AnythingLLM: Chatbot Frontend, can easily connect to LLMs via OpenAI-compatible API


## Required software

- Red Hat OpenShift
- Red Hat OpenShift AI

## Installation instructions

* The commands in this sections require:
  * access to the `oc` cli
  * cluster-admin level of access to the cluster.

An easy way to quickly add a lot of useful, community-provided, custom Workbench Images



* All the images:

    ```bash
    oc apply -k https://github.com/rh-ai-kickstart/custom-workbench-images-examples/imagestreams/
    ```

* delete all the images:

    ```bash
    oc delete -k https://github.com/rh-ai-kickstart/custom-workbench-images-examples/imagestreams/
    ```

* individually:

    ```bash

    URL='https://raw.githubusercontent.com/rh-ai-kickstart/custom-workbench-images-examples/refs/heads/main/imagestreams/'

    # AnythingLLM:
    oc apply -f ${URL}/AnythingLLM-Custom-Workbench-Image.yaml

    # ODH-TEC
    oc apply -f ${URL}/ODH-TEC-Custom-Workbench-Image.yaml

    # TODO
    ## docling workbench

    ## others?
    ```
