# CrewAI A2A Server Helm Chart

This Helm chart deploys the `crewai-a2a-server` application to your Kubernetes cluster.

## Installation

1. Create secret with your Gemini API Key

```sh
oc create secret generic gemini-api-key --from-literal=GOOGLE_API_KEY=<your-gemini-api-key>
```

```sh
helm upgrade -i crewai-a2a-server .
```

## Configuration

You can customize the deployment by editing `values.yaml` or using `--set` flags.

|     Parameter      |     Description     |              Default              |
| :----------------: | :-----------------: | :-------------------------------: |
|  `geminiAiSecret`  | Name of Gemni Secet |     `generic gemini-api-key`      |
| `image.repository` |  Image repository   | `quay.io/jland/crewai-a2a-server` |
|    `image.tag`     |      Image tag      |               `v1`                |

## Uninstallation

```sh
helm uninstall crewai-a2a-server
```

## License

MIT
