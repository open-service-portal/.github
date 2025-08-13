<div align="center">
  <img src="../images/logo.png" alt="Open Service Portal Logo" width="200"/>
  
  # 🚀 Open Service Portal
  
  **Your Self-Service Platform for Cloud-Native Services**
  
  [![Backstage](https://img.shields.io/badge/Built%20with-Backstage-9BF0E1?logo=backstage)](https://backstage.io)
  [![GitHub](https://img.shields.io/badge/Platform-GitHub-181717?logo=github)](https://github.com/open-service-portal)
  [![Kubernetes](https://img.shields.io/badge/Runs%20on-Kubernetes-326CE5?logo=kubernetes)](https://kubernetes.io)
</div>

---

<div align="center">

<table>
<tr>
<td align="center" width="33%">
<h3>🏠</h3>
<b><a href="https://github.com/open-service-portal/app-portal">App Portal</a></b><br/>
The Backstage application
</td>
<td align="center" width="33%">
<h3>📚</h3>
<b><a href="https://github.com/open-service-portal/portal-workspace">Workspace</a></b><br/>
Docs & setup guides
</td>
<td align="center" width="33%">
<h3>📋</h3>
<b><a href="https://github.com/orgs/open-service-portal/projects/1">Roadmap</a></b><br/>
Track our progress
</td>
</tr>
</table>

</div>

---

## 🎯 Our Mission

We're building an **open-source Internal Developer Platform** that empowers developers to provision and manage cloud-native services through a unified, self-service portal. No more tickets, no more waiting - just click and deploy!

## 🛠️ What We're Building

### 🎭 **Backstage-Powered Platform**
Built on [Backstage](https://backstage.io), the open platform for building developer portals created by Spotify.

### 📦 **Key Features**
- **Software Templates** - Standardized blueprints for creating new services
- **Service Catalog** - Central registry of all your services, APIs, and resources  
- **Self-Service Infrastructure** - Provision databases, message queues, and more with a click
- **Developer Documentation** - Integrated TechDocs for all your services
- **GitHub Integration** - Seamless authentication and repository management

<!-- ROADMAP-START -->
## 🗓️ Project Roadmap

This roadmap is automatically generated from our GitHub Project and updated every Friday.

```mermaid
gantt
    title Open Service Portal Roadmap
    dateFormat YYYY-MM-DD
    axisFormat %b %d
    todayMarker stroke-width:5px,stroke:#0f0,opacity:0.75

section Local Development
Epic Local Development Environment :task4, 2025-08-11, 11d

section Crossplane Foundation
Epic Crossplane Foundation :task5, 2025-08-13, 9d

section Template Discovery
Epic Template Discovery & Generation :task6, 2025-08-25, 11d

section Service Catalog
Epic Service Catalog Implementation :task7, 2025-08-25, 11d

section Production Deployment
Epic Production Deployment :task8, 2025-09-08, 11d

section GitOps CICD
Epic GitOps & CI/CD :task9, 2025-09-08, 11d

section Day-2 Operations
Epic Day-2 Operations :task10, 2025-09-10, 9d

section Milestones
v0.1 - Local MVP :milestone, task_v0_1_local_mvp, 2025-08-22, 0d
v0.2 - Service Catalog :milestone, task_v0_2_service_catalog, 2025-09-05, 0d
v0.3 - Production :milestone, task_v0_3_production, 2025-09-19, 0d
```


## 📊 Project Statistics

- **Total Epics:** 16
- **Completed:** 0 (0%)  
- **In Progress:** 0
- **To Do:** 0
- **Critical Priority:** 0
- **High Priority:** 0

### 🔗 Quick Links
- [📋 Project Board](https://github.com/orgs/open-service-portal/projects/1)
- [🗺️ Interactive Roadmap View](https://github.com/orgs/open-service-portal/projects/1/views/3)
- [📊 Table View](https://github.com/orgs/open-service-portal/projects/1/views/1)
- [🎯 Kanban Board](https://github.com/orgs/open-service-portal/projects/1/views/2)

*Last updated: Aug 08, 2025 at 13:34 UTC*

---
*🤖 This roadmap is automatically generated from [GitHub Projects](https://github.com/orgs/open-service-portal/projects/1) every Friday at 16:00 UTC*  
*View the [interactive roadmap](https://github.com/orgs/open-service-portal/projects/1/views/3) for real-time updates*  
*Generated on: Friday, August 8, 2025*
<!-- ROADMAP-END -->

## 🚀 Getting Started

```bash
# Clone the workspace
git clone https://github.com/open-service-portal/portal-workspace.git
cd portal-workspace

# Clone the main application
git clone https://github.com/open-service-portal/app-portal.git
cd app-portal

# Install and start
yarn install
yarn start
```

Visit http://localhost:3000 to see your portal in action!

## 📚 Repositories

| Repository | Description | Status |
|------------|-------------|---------|
| [**app-portal**](https://github.com/open-service-portal/app-portal) | Main Backstage application | ![Build](https://img.shields.io/github/actions/workflow/status/open-service-portal/app-portal/ci.yml?branch=main) |
| [**portal-workspace**](https://github.com/open-service-portal/portal-workspace) | Documentation and setup guides | ![Docs](https://img.shields.io/badge/docs-available-blue) |

## 🤝 Contributing

We welcome contributions from the community! Whether you're fixing bugs, adding features, or improving documentation, we'd love to have you aboard.

- 🐛 [Report Issues](https://github.com/open-service-portal/app-portal/issues)
- 💡 [Discussions](https://github.com/orgs/open-service-portal/discussions)
- 📖 [Documentation](https://github.com/open-service-portal/portal-workspace/tree/main/docs)

## 🔧 Tech Stack

<div align="center">
  
| Component | Technology |
|-----------|------------|
| Framework | [Backstage](https://backstage.io) |
| Language | TypeScript |
| Runtime | Node.js 20 LTS |
| Database | PostgreSQL / SQLite |
| Container | Docker / Kubernetes |
| Auth | GitHub Apps |

</div>

## 📊 Project Status

This project is under active development. We're currently working on:
- ✅ GitHub App authentication
- ✅ Organization member import
- 🚧 Service templates
- 🚧 Kubernetes integration
- 📋 Cloud provider integrations

## 🌟 Why Open Service Portal?

- **Developer Experience First** - Built by developers, for developers
- **Open Source** - No vendor lock-in, full transparency
- **Extensible** - Add your own plugins and integrations
- **Production Ready** - Built on proven technologies

## 📬 Get in Touch

- 💬 [GitHub Discussions](https://github.com/orgs/open-service-portal/discussions)
- 🐛 [Issue Tracker](https://github.com/open-service-portal/app-portal/issues)

---

<div align="center">
  Made with ❤️ by the Open Service Portal Community
</div>