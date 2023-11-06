##  What means GitOps
> GitOps is a methodology and practice that uses Git repositories as a single source of truth to deliver infrastructure as code. 

**Pillars**
- Git is the single source of truth
- Treat everything as code
- Operations are performed through Git workflows
**Principles**
- Declarative A system managed by GitOps must have its desired state expressed declaratively
- Versioned and immutable The desired state is stored in a way that enforces immutability and versioning and retains a complete version history.
- Pulled automatically Software agents automatically pull the desired state declarations from the source.
- Continuously reconciled Software agents continuously observe the actual system state and attempt to apply the desired state.

# Why GitOps

Deal Infra Operations as a Code. 
- Standard workflow : Use familiar tools and Git workflows from application development teams 
- Enhanced security: Review changes beforehand, detect configuration drifts, and take action
-  Visibility and audit: Capture and trace any change to clusters through Git history 
- Multicluster consistency: Reliably and consistently configure multiple environments and multiple Kubernetes clusters and deployment

> Every operation, such as applica‐ tion deployment or infrastructure change, is only possible through Git workflows. And sometimes, this means a cultural shift
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYzMzQ2NDg5LDE0MDcwMTAyODldfQ==
-->