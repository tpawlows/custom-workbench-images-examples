# custom-workbench-images-examples

An easy way to quickly add a lot of useful, community-provided, custom Workbench Images

* individually:

    ```bash

    URL='https://raw.githubusercontent.com/rh-ai-kickstart/custom-workbench-images-examples/refs/heads/main/imagestreams/'

    # AnythingLLM:
    oc apply -f ${URL}/AnythingLLM-Custom-Workbench-Image.yaml

    # ODH-TEC
    oc apply -f ${URL}/ODH-TEC-Custom-Workbench-Image.yaml
    ```


* All the images:

    ```bash
    oc apply -k https://github.com/rh-ai-kickstart/custom-workbench-images-examples/imagestreams/
    ```

* delete all the images:

    ```bash
    oc delete -k https://github.com/rh-ai-kickstart/custom-workbench-images-examples/imagestreams/
    ```

