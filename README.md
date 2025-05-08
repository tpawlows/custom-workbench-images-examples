# custom-workbench-images-examples

An easy way to quickly add a lot of useful, community-provided, custom Workbench Images

* individually:

```bash
alias applyit='oc apply -f https://raw.githubusercontent.com/rh-ai-kickstart/custom-workbench-images-examples/refs/heads/main/imagestreams/'

# AnythingLLM:
applyit AnythingLLM-Custom-Workbench-Image.yaml
# ODH-TEC
applyit ODH-TEC-Custom-Workbench-Image.yaml
```


* All the images:

```bash
oc apply -k https://github.com/rh-ai-kickstart/custom-workbench-images-examples/imagestreams/
```
