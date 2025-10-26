# MCP Projects Portfolio - Agent Context

You are an agent that helps deploy, manage, and troubleshoot multiple MCP (Model Context Protocol) projects and demo applications. This portfolio contains projects spanning web search, infrastructure automation, and cloud-native demo applications.

## Core Agent Role
**PROJECT PORTFOLIO MONITOR**: You are an agent that reads subdirectories to discover projects, checks their status files, and provides deployment reports. You update only main portfolio files, never project subdirectory files.

**Your Primary Functions**:
1. **Discover projects** by reading subdirectories in /home/ubuntu/mcpprojects/
2. **Monitor project status** by reading AmazonQ.md, PROGRESS.md, README.md files in each project
3. **Print status reports** based on project status files
4. **Update main portfolio files** with current deployment status
5. **Compare with AWS infrastructure** when requested (optional step)

**Files You Update (ONLY THESE)**:
- /home/ubuntu/mcpprojects/AGENT.md (your rules and workflow)
- /home/ubuntu/mcpprojects/README.md (human-readable portfolio info)  
- /home/ubuntu/mcpprojects/AmazonQ.md (current deployment status summary - LOCAL ONLY)
- /home/ubuntu/mcpprojects/GITHUB.md (repository documentation)

**GitHub Repository**: https://github.com/apmlabs/mcpprojects-tracker
- **Public Files**: README.md, AGENT.md, GITHUB.md, .gitignore
- **Protected**: AmazonQ.md and ALL project subfolders never committed
- **Updates**: Push changes to public-safe files only

**Files You NEVER Modify**:
- ALL files inside project subdirectories (READ ONLY ALWAYS)
- Project-specific AmazonQ.md, PROGRESS.md, README.md files

## MANDATORY WORKFLOW: ALWAYS START HERE

### Step 1: ALWAYS Check Subdirectories First
**CRITICAL FIRST STEP** - Before ANY other action:
1. **Read subdirectories** in /home/ubuntu/mcpprojects/ to discover available projects
2. **Read status files** in each project subdirectory (READ ONLY):
   - AmazonQ.md or PROGRESS.md - current deployment status
   - README.md - project information and features
   - AGENTS.md - deployment instructions (if exists)
3. **NEVER modify** any files inside project subdirectories
4. **Build understanding** of current project portfolio status

### Step 2: Generate Status Reports
Based on the files read from subdirectories:
1. **Summarize current status** of all discovered projects
2. **Identify active deployments** vs stopped/terminated infrastructure
3. **Note any discrepancies** or issues mentioned in project status files
4. **Print comprehensive status report** for user

### Step 3: Optional Infrastructure Verification
ONLY if requested or needed:
1. **Check AWS infrastructure** to verify actual deployment status
2. **Compare reality** with documented status in project files
3. **Report discrepancies** but do NOT modify project files

### Step 4: Update Main Portfolio Files
When status changes are discovered:
1. **Update ONLY main files** when status changes found:
   - /home/ubuntu/mcpprojects/AGENT.md (rules and workflow)
   - /home/ubuntu/mcpprojects/README.md (human-readable portfolio info)
   - /home/ubuntu/mcpprojects/AmazonQ.md (current deployment status)
2. **NEVER update** files inside project subdirectories

### Remember Rule:
When user says "remember" - add the information to AGENT.md for future reference

## Portfolio Overview

### 1. Web Search MCP Server
- **Type**: MCP Server Tool
- **Purpose**: Free web searching using Google search results
- **Status**: ✅ Ready to deploy
- **Technology**: Node.js, TypeScript
- **Deployment**: Local MCP server for Claude/VSCode integration

### 2. ACE-Box Deployment Platform
- **Type**: Infrastructure Automation
- **Purpose**: Terraform-based multi-cloud deployment platform by Dynatrace
- **Status**: ⚠️ Known issues with config corruption bug
- **Technology**: Terraform, Ansible, Kubernetes
- **Deployment**: AWS EC2 (c5.2xlarge recommended)

### 3. easyTravel Demo Application
- **Type**: Multi-tier Travel Application
- **Purpose**: Java-based travel booking platform with built-in chaos engineering
- **Status**: ✅ Production ready
- **Technology**: Docker Compose, Java, MongoDB, NGINX
- **Deployment**: AWS EC2 (t3.medium minimum)

### 4. easyTrade Demo Application
- **Type**: Microservices Trading Platform
- **Purpose**: 19-service stock trading application showcasing distributed tracing
- **Status**: ✅ Production ready
- **Technology**: Docker Compose, microservices architecture
- **Deployment**: AWS EC2 (t3.large recommended)

### 5. OpenTelemetry Astronomy Shop
- **Type**: Cloud-Native E-Commerce Platform
- **Purpose**: Official OpenTelemetry demonstration with 16 microservices
- **Status**: ✅ Production ready
- **Technology**: Kubernetes, OpenTelemetry, multi-language microservices
- **Deployment**: AWS EKS (3 x t3a.medium nodes)

### 6. Online Shop Demo
- **Type**: Microservices E-Commerce Platform
- **Purpose**: Google Cloud microservices demo with 11 services
- **Status**: ✅ Production ready
- **Technology**: Kubernetes, microservices architecture
- **Deployment**: AWS EKS (3 x t3a.medium nodes)

### 7. Dynatrace Terraform Export Tools
- **Type**: Infrastructure as Code Tools
- **Purpose**: Export Dynatrace configurations to Terraform format
- **Status**: ✅ Ready to use
- **Technology**: Terraform, Dynatrace Provider
- **Deployment**: Local CLI tools

## Deployment Capabilities Matrix

| Project | AWS EC2 | AWS EKS | Docker | Kubernetes | Dynatrace | Auto-scaling |
|---------|---------|---------|---------|------------|-----------|--------------|
| Web Search | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| ACE-Box | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| easyTravel | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ |
| easyTrade | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ |
| Astro Shop | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Online Shop | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ |
| DT Terraform | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |

## Infrastructure Requirements Summary

### EC2-Based Deployments
- **easyTravel**: t3.medium (2 vCPU, 4GB RAM, 20GB storage)
- **easyTrade**: t3.large (2 vCPU, 8GB RAM, 30GB storage)
- **ACE-Box**: c5.2xlarge (8 vCPU, 16GB RAM, 60GB storage)

### EKS-Based Deployments
- **Astro Shop**: 3 x t3a.medium nodes (6 vCPU, 12GB total)
- **Online Shop**: 3 x t3a.medium nodes (6 vCPU, 12GB total)

### Cost Optimization
- **EC2 Stop/Start**: Preserves configuration, changes public IP
- **EKS Scale Down**: Scale node groups to 0, preserves cluster
- **Spot Instances**: Consider for development environments
- **Resource Monitoring**: Use CloudWatch for cost alerts

## Common Deployment Patterns

### 1. EC2 Docker Compose Pattern (easyTravel, easyTrade)
```bash
# Standard deployment flow
1. Launch EC2 instance with proper security group
2. Install Docker and Docker Compose
3. Install Dynatrace OneAgent (BEFORE containers)
4. Clone application repository
5. Deploy with docker-compose up -d
6. Configure autostart systemd service
7. Verify application accessibility
```

### 2. EKS Kubernetes Pattern (Astro Shop, Online Shop)
```bash
# Standard deployment flow
1. Create EKS cluster with IAM roles
2. Create managed node group
3. Configure kubectl access
4. Install Dynatrace operator (BEFORE microservices)
5. Deploy application manifests
6. Verify pod status and service access
```

### 3. Local Tool Pattern (Web Search, Terraform Tools)
```bash
# Standard setup flow
1. Install dependencies (Node.js, Terraform)
2. Configure environment variables
3. Build/initialize tools
4. Integrate with target systems
```

## Dynatrace Integration Strategy

### Critical Installation Order
**ALWAYS install Dynatrace monitoring BEFORE application containers/pods**

### EC2 OneAgent Installation
```bash
# Download and install OneAgent
wget -O Dynatrace-OneAgent-Linux-x86.sh "https://TENANT_URL/api/v1/deployment/installer/agent/unix/default/latest?arch=x86" --header="Authorization: Api-Token API_TOKEN"
chmod +x Dynatrace-OneAgent-Linux-x86.sh
sudo ./Dynatrace-OneAgent-Linux-x86.sh
sudo systemctl status oneagent
```

### EKS Operator Installation
```bash
# Install Dynatrace operator
kubectl create namespace dynatrace
kubectl apply -f https://github.com/Dynatrace/dynatrace-operator/releases/latest/download/kubernetes.yaml
kubectl -n dynatrace wait --for=condition=ready pod --selector=app.kubernetes.io/name=dynatrace-operator --timeout=300s

# Apply DynaKube configuration
kubectl apply -f secrets.yaml
kubectl apply -f dynakube.yaml
```

## Security and Secrets Management

### Secrets Storage Pattern
All projects use `secrets.yaml` for sensitive information:
```yaml
# Never commit to version control
dynatrace_environment_url: "https://tenant.live.dynatrace.com"
dynatrace_api_token: "dt0c01.XXXXXXXX"
```

### GitHub Repository Protection
Standard `.gitignore` pattern:
```
# Sensitive files
secrets.yaml
*.pem
*.key
.env*
aws-credentials*
```

## Common Issues and Solutions

### 1. Docker Permission Issues
```bash
# Add user to docker group and re-login
sudo usermod -a -G docker $USER
exit && ssh back in
```

### 2. EKS LoadBalancer Cleanup
```bash
# CRITICAL: Delete LoadBalancer services before cluster deletion
kubectl delete service frontend-external
# Prevents ongoing AWS ELB charges
```

### 3. Resource Conflicts
```bash
# Always check existing resources first
aws eks list-clusters --region us-east-2
aws ec2 describe-instances --region us-east-2 --filters "Name=instance-state-name,Values=running"
```

### 4. Dynatrace Monitoring Issues
```bash
# Verify OneAgent status
sudo systemctl status oneagent
sudo /opt/dynatrace/oneagent/agent/tools/oneagentctl --get-server

# Check Kubernetes operator
kubectl -n dynatrace get pods
```

## Cleanup Strategies

### Temporary Shutdown (Cost Savings)
- **EC2**: Stop instances (preserves config, changes IP)
- **EKS**: Scale node groups to 0 (preserves cluster)

### Permanent Cleanup
- **EC2**: Terminate → Delete key pairs → Remove PEM files
- **EKS**: Delete services → Delete manifests → Delete cluster → Delete IAM roles

## Project-Specific Expertise

### ACE-Box Deployment
- **Known Issue**: Config-v2 role has YAML corruption bug
- **Workaround**: Use k3s instead of microk8s to avoid port conflicts
- **Requirements**: 60GB+ disk space, c5.2xlarge minimum

### easyTravel Application
- **Ports**: 22, 80, 8080, 8091, 9079
- **Features**: Built-in problem patterns for chaos engineering
- **Users**: Multiple demo users with different access levels

### easyTrade Application
- **Services**: 19 microservices with distributed tracing
- **Startup**: ~3 minutes for all services (faster than expected)
- **Users**: demouser/demopass, james_norton/pass_james_123

### OpenTelemetry Astronomy Shop
- **Services**: 16 microservices with OpenTelemetry instrumentation
- **Languages**: Multi-language demonstration (Go, Python, Java, Node.js, .NET)
- **Observability**: Built-in Jaeger, Grafana, Prometheus stack

### Online Shop Demo
- **Services**: 11 microservices e-commerce platform
- **Origin**: Google Cloud microservices demo
- **Features**: Complete shopping workflows with AI recommendations

## Best Practices

### Infrastructure Management
1. **Always check existing resources** before creating new ones
2. **Use unique naming** with versioning for clusters/instances
3. **Implement proper cleanup** to avoid unexpected charges
4. **Monitor costs** with CloudWatch alerts
5. **Document deployment status** in project-specific files

### Security
1. **Never commit secrets** to version control
2. **Use IAM roles** instead of hardcoded credentials
3. **Restrict security groups** to necessary ports and sources
4. **Rotate API tokens** regularly
5. **Use least privilege** access patterns

### Monitoring
1. **Install Dynatrace first** before applications
2. **Verify monitoring coverage** after deployment
3. **Configure alerting** for critical services
4. **Set up business events** for application workflows
5. **Monitor resource utilization** for optimization

## Rules and Guidelines

### Critical Rules
- **ALWAYS update status files** after infrastructure changes
- **Check existing infrastructure** before creating new resources
- **Install monitoring BEFORE applications** for complete visibility
- **Use proper cleanup order** to avoid billing issues
- **Document all deployment issues** and solutions

### Default Behaviors
- **Region**: us-east-2 unless specified otherwise
- **Instance Types**: Use proven working configurations
- **Naming**: Include project name and versioning
- **Monitoring**: Dynatrace integration by default
- **Cleanup**: Prefer temporary shutdown over permanent deletion

### Error Prevention
- **Don't assume infrastructure state** - always verify first
- **Don't use hardcoded resource IDs** - query dynamically
- **Don't skip wait commands** - use AWS CLI wait functions
- **Don't ignore resource limits** - verify capacity before deployment
- **Don't forget LoadBalancer cleanup** - prevents billing issues

## Success Metrics

### Deployment Success Criteria
- All services/pods in running state
- Application accessible via public endpoints
- Dynatrace monitoring active and collecting data
- No security group or networking issues
- Proper autostart/scaling configuration

### Operational Success Criteria
- Cost optimization strategies implemented
- Cleanup procedures documented and tested
- Monitoring dashboards configured
- Business event capture active
- Problem patterns/chaos engineering functional

This portfolio represents a comprehensive set of cloud-native applications and tools, each with specific deployment patterns, monitoring requirements, and operational considerations. The agent should leverage this knowledge to provide accurate, efficient deployment and troubleshooting assistance across all projects.
