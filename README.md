# A2A helm charts

A series of charts for installing a2a servers and a frontend.

## Install

### Prerequisites

- Python 3.12 or higher
- [UV](https://docs.astral.sh/uv/)
- Access to an LLM and API Key (Current code assumes using Google Gen AI API)
- A LlamaParse API key ([get one for free](https://cloud.llamaindex.ai))

> [!NOTE]
> LlamaParse API only required if you are using llama-index chart


1. Create required secret with Google API Key

    ```sh
    oc create secret generic gemini-api-key --from-literal=GOOGLE_API_KEY=<your-gemini-api-key>
    --from-literal=LLAMA_CLOUD_API_KEY=<your_api_key_here>
    
    ```

2. Deploy everything

    ```sh
    kustomize build --enable-helm . | oc apply -f -
    ```

## Add Agents

If the agents were installed successfully you should be able to add them by navigating to the UI's endpoint.

Navigate to agents, and add the following:

1. image-generator-agent-crewai-a2a-server:10001
2. currency-conversion-agent-langchain-a2a-server:10000
3. file-upload-agent-llama-index-a2a-server:10010

## UnInstall

```sh
kustomize build --enable-helm . | oc delete -f -
```
