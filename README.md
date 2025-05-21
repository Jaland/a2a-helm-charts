# A2A helm charts

A series of charts for installing a2a servers and a frontend.

## Install

1. Create required secret with Google API Key

    ```sh
    oc create secret generic gemini-api-key --from-literal=GOOGLE_API_KEY=<your-gemini-api-key>
    LLAMA_CLOUD_API_KEY=your_api_key_here
    
    ```

2. Deploy everything

    ```sh
    kustomize build --enable-helm . | oc apply -f -
    ```

## Add Agents

If the agents were installed successfully you should be able to add them by navigating to the UI's endpoint.

Navigate to agents, and add the following:

1. image-generator-agent-crewai-a2a-server:10001


## UnInstall

```sh
kustomize build --enable-helm . | oc delete -f -
```

