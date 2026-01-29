# MCP Projects Portfolio

An AI agent-managed collection of Model Context Protocol (MCP) projects and cloud-native demo applications with automated deployment status monitoring and infrastructure management.

🤖 **Managed by AI Agent** | 📊 **Real-time Status Tracking** | ☁️ **AWS Cloud Native** | 🔒 **Security First**

## What This Is

This portfolio demonstrates how an AI agent can effectively manage and monitor multiple cloud infrastructure projects:

- **9 different projects** spanning microservices demos and infrastructure tools
- **Automated status monitoring** with real-time deployment tracking
- **Cost optimization strategies** with proven shutdown/restart procedures  
- **Security best practices** with secrets management and access controls
- **Comprehensive documentation** for each deployment pattern

## AI Agent Capabilities

The managing agent can:
- 🔍 **Discover projects** by scanning subdirectories
- 📋 **Monitor deployment status** across AWS infrastructure
- 💰 **Track costs** and recommend optimization strategies
- 🛡️ **Ensure security** through proper secrets management
- 📚 **Maintain documentation** with current deployment states
- 🚀 **Guide deployments** using proven patterns and procedures

## Current Portfolio Status

**Portfolio Health**: 100% ready (11/11 projects fully deployable)  
**Active Infrastructure**: 1 project running (OnyxPoker)  
**Monthly Cost Range**: $50 current, up to $290 if all restarted  
**Security Status**: All projects follow established security patterns

## Repository Information

**GitHub Repository**: https://github.com/apmlabs/mcpprojects-tracker

This public repository contains the portfolio documentation and AI agent workflow. For security:
- **No sensitive data** is committed (deployment status, credentials, project code)
- **Only documentation** is public (overview, patterns, best practices)
- **Project implementations** remain in local subdirectories

## Documentation Structure

- **[README.md](./README.md)** - This file: Portfolio overview and project status
- **[AGENTS.md](./AGENTS.md)** - Agent workflow, technical deployment context, and project expertise
- **[AmazonQ.md](./AmazonQ.md)** - Current deployment status and infrastructure monitoring (local only)
- **[GITHUB.md](./GITHUB.md)** - Repository setup, security information, and GitHub integration

## Quick Start

- **[AGENTS.md](./AGENTS.md)** - Agent workflow and technical deployment context
- **[GITHUB.md](./GITHUB.md)** - Repository setup and security information

### ✅ Active & Running (1 project)
1. **OnyxPoker - Poker AI Assistant** - GPT-5.2 vision + strategy engine (EC2/Python) - **CURRENTLY RUNNING**
   - **Status**: ✅ FULLY OPERATIONAL with 70+ development sessions
   - **Server**: 54.80.204.92:5001 (us-east-1)
   - **Features**: V2 vision with opponent tracking, the_lord strategy (+1091 BB vs hero)
   - **Technology**: Python, GPT-5.2, PyQt5 UI, PokerKit
   - **Player Database**: 613 players with archetype classification

### 🛑 Stopped Infrastructure (4 projects)
2. **easyTravel Demo (x2)** - Java travel booking app (EC2/Docker) - STOPPED
3. **easyTrade Demo** - 19-microservice trading platform (EC2/Docker) - STOPPED
4. **easyTrade K8s Demo** - 19-microservice trading platform (EC2/K3s) - STOPPED

### 🚫 Terminated (4 projects)
5. **Onyx Project** - Youth activities search platform - TERMINATED
6. **OpenTelemetry Astronomy Shop** - 16-service e-commerce demo (EKS) - TERMINATED
7. **Online Shop Demo** - 11-service shopping platform (EKS) - TERMINATED
8. **ACE-Box** - Dynatrace deployment platform - TERMINATED

### 🛠️ Local Tools Ready (3 projects)
9. **Dynatrace Terraform Tools** - Configuration export utilities
10. **Dynatrace Terraform Account Management** - IAM and user management tools
11. **FortiSwitch Project** - Network device monitoring (19 alerts deployed)

## Key Deployment Patterns

### EC2 + Docker Compose Pattern
- **easyTravel**: t3.medium, 5 ports, travel booking workflows
- **easyTrade**: t3.large, 19 microservices, stock trading

### EC2 + K3s Pattern
- **easyTrade K8s**: t3.large, K3s single-node, 19 microservices

### EKS + Kubernetes Pattern
- **Astro Shop**: 3×m5.large nodes, OpenTelemetry instrumentation
- **Online Shop**: 3×t3a.medium nodes, Google Cloud microservices demo

### Local Tools Pattern
- **Dynatrace Terraform Tools**: Configuration export utilities  
- **Dynatrace Terraform Account Management**: IAM and user management

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
├── AGENTS.md                    # Agent workflow and technical context
├── AmazonQ.md                   # Current deployment status
├── acebox/                      # Dynatrace ACE-Box platform
├── astroshop-demo/              # OpenTelemetry astronomy shop
├── dynatrace-terraform/         # Terraform export tools
├── dynatrace-terraform-accmgmt/ # Duplicate Terraform tools
├── easytrade-demo/              # Stock trading microservices
├── easytrade-demo-k8s/          # Stock trading microservices (K8s)
├── easytravel-demo/             # Travel booking application
├── fortiswitch-project/         # Network device monitoring
├── online-shop-demo/            # Google Cloud microservices demo
└── onyx-project/                # Youth activities search platform
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

**Portfolio Status**: 100% ready (11/11 projects fully deployable)  
**Last Updated**: 2025-01-25T22:06:00.000+00:00
