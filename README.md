# AI Ops Assistant - Intelligent Kubernetes Operations Platform

An AI-powered operations assistant designed to monitor, troubleshoot, investigate and manage Kubernetes infrastructure using Large Language Models (LLMs), AI agents and observability tools.
The platform combines **Kubernetes, Prometheus, Grafana, Loki, LangChain, LangGraph and LangSmith** to deliver intelligent infrastructure monitoring, automated incident investigation and controlled remediation.

---

## Project Overview 
Traditional infrastructure monitoring tools provide metrics, dashboards and alerts, but engineers still need to investigate incidents manually.
The AI Ops assistant aims to bridge this gap by introducing an intelligent agent that can understand natural language questions, interact with infrastructure monitoring systems, investigate operational issues and recommend corrective actions.
Instead of manually checking multiple dashboards and logs, engineers can ask questions such as:
- Why is my NGINX application slow?
- Which Kubernetes pods are consuming most memory?
- Why did my NGINX pod restart?
- Are there any failing Prometheus targets?
- Investigate why my application is unavailable?
- Can you restart the unhealthy deployment?

The assistant uses specialized skills, connectors and plugins to investigate infrastructure issues.

## Architecture

```mermaid
flowchart TB
  U["User / Engineer"] --> UI["AI Ops Chat Interface"]
  UI                   --> API["FastAPI Backend"]
  API                  --> AG["LangGraph Agent Orchestrator"]
  AG                   --> SK["AI Skills"]
  SK                   --> K["Kubernetes Connector"]
  SK                   --> P["Prometheus Connector"]
  SK                   --> G["Grafana Connector"]
  SK                   --> L["Loki Connector"]
  K                    --> KC["Kubernetes API"]
  P                    --> PR["Prometheus"]
  G                    --> GR["Grafana"]
  L                    --> LO["Loki"]
  KC                   --> INF["Minikube infrastructure"]
  INF                  --> NG["NGINX Application"]
  AG                   --> LS["LangSmith Observability"]
```

## Technology Stack
| Category | Technology | Purpose |
| --- | --- | ---|
| Container orchestration | Kubernetes | Infrastructure management |
| Local Kubernetes | Minikube | Development environment |
| Containers | Docker | Containerization |
| AI framework | LangChain | LLM and tool integration |
| Agent orchestration | LangGraph | Multi-step agent workflows |
| LLM observability | LangSmith | Tracing and evaluation |
| LLM | OpenAI | Reasoning and natural language |
| Backend | Python/FastAPI | API and application backend |
| Metrics | Prometheus | Infrastructure and monitoring |
| Visualization | Grafana | Monitoring dashboards |
| Logging | Loki | Centralized log management|
| Integration | MCP | Extensible tool connectivity |

## AI Agent
The assistant uses reusable operational skills rather than relying on a single generic chatbot.
| Skill | Description |
| -- | -- |
| Kubernetes Resource Analysis | Analyze CPU, memory and pod resource consumption |
| Kubernetes Troubleshooting | Analyze NGINX performance and HTTP errors |
| Prometheus Health Check | Investigate scrape targets and monitoring health |
| Performance Analysis | Identify infrastructure bottlenecks |
| Incident Investigation | Correlate logs, metrics and Kubernetes events |
| Kubernetes Remediation | Perform approved infrastructure operations |

## Connectors and Integrations
