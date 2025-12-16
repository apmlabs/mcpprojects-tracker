# GitHub Repository Setup

## Repository Information
- **Repository**: https://github.com/apmlabs/mcpprojects-tracker
- **Visibility**: Public
- **Purpose**: AI agent-managed portfolio tracker for MCP projects and cloud-native demo applications

## Repository Structure
```
mcpprojects-tracker/
├── README.md      # Public-facing portfolio overview
├── AGENT.md       # Agent workflow and technical context
├── GITHUB.md      # This file - repository setup info
└── .gitignore     # Protection against sensitive file commits
```

## Security Configuration

### Protected Files (Never Committed)
- `AmazonQ.md` - Current deployment status with sensitive infrastructure details
- `secrets.yaml` - Sensitive configuration files
- `*/` - ALL project subfolders and their contents
- AWS credentials, Terraform state, private keys

### Committed Files (Public Safe)
- Portfolio overview and documentation
- Agent workflow descriptions
- General deployment patterns and insights
- Cost estimates and architecture patterns

## Git Workflow

### Initial Setup (Completed)
```bash
git init
git remote add origin https://github.com/apmlabs/mcpprojects-tracker.git
git add .gitignore README.md AGENT.md GITHUB.md
git commit -m "Initial commit"
git push -u origin main
```

### Future Updates
```bash
# Only update main portfolio files
git add README.md AGENT.md GITHUB.md
git commit -m "Update portfolio status"
git push origin main
```

### Multi-Repository Management

The portfolio includes **7 individual project repositories**, each with their own GitHub repository:

**Active Project Repositories:**
- https://github.com/apmlabs/astroshop-demo.git
- https://github.com/apmlabs/dynatrace-terraform.git  
- https://github.com/apmlabs/dynatrace-terraform-accmgmt.git
- https://github.com/apmlabs/easytrade-demo.git (shared by easytrade-demo and easytrade-demo-k8s)
- https://github.com/apmlabs/easytravel-demo.git
- https://github.com/apmlabs/online-shop-demo.git

**Repository Synchronization Commands:**
```bash
# Check all project repository status
for dir in /home/ubuntu/mcpprojects/*/; do
  if [ -d "$dir/.git" ]; then
    echo "=== $(basename "$dir") ==="
    cd "$dir"
    git status --porcelain
    git fetch origin
    # Pull if behind remote
    git pull
  fi
done

# Commit and push changes for specific project
cd /home/ubuntu/mcpprojects/PROJECT_NAME
git add .
git commit -m "Update documentation and deployment instructions"
git push
```

## Repository Purpose

This repository serves as:
1. **Public Portfolio Showcase** - Demonstrates AI agent portfolio management capabilities
2. **Documentation Hub** - Provides insights into cloud-native deployment patterns
3. **Best Practices Reference** - Shows security, monitoring, and cost optimization approaches
4. **Agent Workflow Transparency** - Documents how the AI agent manages infrastructure

## Important Notes

- **No Sensitive Data**: Repository contains only public-safe documentation
- **No Project Code**: Individual project implementations remain in local subfolders
- **Status Tracking**: Deployment status tracked locally in AmazonQ.md files
- **Agent Managed**: Repository updates handled by AI agent workflow

## Last Updated
- **Repository Created**: 2025-10-26T11:08:38.896+00:00
- **Initial Commit**: 2025-10-26T11:14:20.134+00:00
- **Latest Update**: 2025-12-16T13:12:00.000+00:00 - Added multi-repository management and synchronization procedures
- **Status**: Active and synchronized (7/7 project repositories up to date)
