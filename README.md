# MCP Projects Portfolio

A comprehensive collection of Model Context Protocol (MCP) projects and cloud-native demo applications managed by an AI agent that monitors deployment status and provides infrastructure automation.

## Agent Role

This portfolio is managed by an AI agent that:
- **Reads project subdirectories** to discover available projects
- **Monitors deployment status** by checking AmazonQ.md/PROGRESS.md files in each project
- **Compares with AWS reality** to identify infrastructure discrepancies  
- **Updates main portfolio files** with current status (never modifies project files)
- **Provides deployment reports** and infrastructure management

## Quick Start

- **[AGENT.md](./AGENT.md)** - Agent workflow and technical deployment context
- **[AmazonQ.md](./AmazonQ.md)** - Current deployment status and portfolio summary

## Portfolio Overview

**8 Total Projects** spanning different technologies and deployment patterns:

### ✅ Ready to Deploy (6 projects)
1. **Web Search MCP Server** - Node.js tool for Google search integration
2. **easyTravel Demo** - Java travel booking app (EC2/Docker)
3. **easyTrade Demo** - 19-microservice trading platform (EC2/Docker)
4. **OpenTelemetry Astronomy Shop** - 16-service e-commerce demo (EKS/Kubernetes)
5. **Online Shop Demo** - 11-service shopping platform (EKS/Kubernetes)
6. **Dynatrace Terraform Tools** - Configuration export utilities

### ⚠️ Known Issues (1 project)
- **ACE-Box** - Has config corruption bug, needs workarounds

### 🔄 Duplicate (1 project)
- **Dynatrace Terraform Account Management** - Same as main Terraform tools

## Key Deployment Patterns

### EC2 + Docker Compose Pattern
- **easyTravel**: t3.medium, 5 ports, travel booking workflows
- **easyTrade**: t3.large, 19 microservices, stock trading

### EKS + Kubernetes Pattern
- **Astro Shop**: 3×t3a.medium nodes, OpenTelemetry instrumentation
- **Online Shop**: 3×t3a.medium nodes, Google Cloud microservices demo

### Local Tools Pattern
- **Web Search**: MCP server for Claude/VSCode integration
- **Terraform Tools**: Dynatrace configuration export

## Critical Insights

1. **Dynatrace First Rule**: Always install OneAgent/operator BEFORE applications
2. **LoadBalancer Cleanup**: Delete Kubernetes services before cluster deletion to avoid billing
3. **Resource Checking**: Always verify existing AWS resources before creating new ones
4. **Secrets Management**: Consistent secrets.yaml pattern with .gitignore protection
5. **Cost Optimization**: Stop/scale-down strategies preserve configuration while saving money

## Project Structure

```
mcpprojects/
├── README.md                    # This file
├── AGENT.md                     # Agent workflow and technical context
├── AmazonQ.md                   # Current deployment status
├── acebox/                      # Dynatrace ACE-Box platform
├── astroshop-demo/              # OpenTelemetry astronomy shop
├── dynatrace-terraform/         # Terraform export tools
├── dynatrace-terraform-accmgmt/ # Duplicate Terraform tools
├── easytrade-demo/              # Stock trading microservices
├── easytravel-demo/             # Travel booking application
└── online-shop-demo/            # Google Cloud microservices demo
```

## Quick Deployment

Each project folder contains:
- **README.md** - Project overview and features
- **AGENTS.md** - Complete deployment instructions
- **AmazonQ.md** - Current deployment status (not committed to git)
- **secrets.yaml** - Sensitive configuration (not committed to git)

## Cost Estimates

- **easyTravel (t3.medium)**: ~$25/month
- **easyTrade (t3.large)**: ~$50/month  
- **Astro Shop (3x t3a.medium)**: ~$95/month
- **Online Shop (3x t3a.medium)**: ~$95/month
- **ACE-Box (c5.2xlarge)**: ~$140/month

## Security

All projects follow consistent security patterns:
- Secrets stored in `secrets.yaml` (never committed)
- Standard `.gitignore` protects sensitive files
- IAM roles for AWS resource access
- Proper security group configurations

## Monitoring

All deployable applications include Dynatrace integration:
- **EC2 Deployments**: OneAgent installation
- **EKS Deployments**: Dynatrace operator
- **Auto-discovery**: Automatic service monitoring
- **Business Events**: Application workflow tracking

## Support

For deployment assistance or troubleshooting:
1. Check project-specific **AGENTS.md** for detailed instructions
2. Review **AmazonQ.md** for current status and known issues
3. Verify **AmazonQ.md** in project folders for deployment context

---

**Portfolio Status**: 87.5% ready (7/8 projects fully deployable)  
**Last Updated**: 2025-10-26T10:54:28.676+00:00
