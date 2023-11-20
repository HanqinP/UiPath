# Orchestrator
## overview
Orchestrator is the component of the UiPath Platform for managing automations, robots, and the related entities.

## The main capabilities of Orchestrator
### Orchestrator Capabilities: Provisioning
Provisioning: Orchestrator creates and maintains the connection with robots and attended users.
![Provisioning](../resources/Provisioning.png)

### Orchestrator Capabilities: Control and License Distribution

Orchestrator also enables the creation, assignment, and maintenance of licenses, roles, permissions, groups, and folder hierarchies

![Alt text](../resources/ControlAndLicenseDistribution.png)

### Orchestrator Capabilities: Running Jobs in Unattended Mode

it enabels the creation and distribution of automation jobs in various ways, including through queues and triggers.

![Running Jobs in Unattended Mode](../resources/RunningJobsInUnattendedMode.png)

### Orchestrator Capabilities: Automation Storage and Distribution

Orchestrator is the environment enabling the controlled storage and distribution of automation projects, assets, and credentials, as well as large files used in the automation.

![Automation Storage and Distribution](../resources/AutomationStorageAndDistribution.png)

### Orchestrator Capabilities: Monitoring

With Orchestrator, admins are able to monitor jobs and robots.

![Monitoring](../resources/Monitoring.png)

it also stores Logs for auditing and analytics

![MonitorWithLog](../resources/MonitorWithLog.png)

### Orchestrator Capabilities: Inter-connectivity

Orchestrator acts as the centralized point of communication for third-party solutions or third-party applications.

![Inter-connectivity](../resources/Inter-connectivity.png)

## Orchestrator entities-Tenants and Folders

### overview
A single Orchestrator instance can be split into multiple Tenants. Each tenant in an organization can be further subdivided and organized into Folders. Tenants are designed for the purpose of completed isolation of all Orchestrator entities(i.e., Robots, Assets, Queues, etc.) between these segregated instances of your deployment. 