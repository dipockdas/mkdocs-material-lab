# Architecture Model





### Component

An individual element within the model, such as a database, web server, API gateway, VPC, or subnet. Components can represent both physical infrastructure (e.g., servers, storage) and logical entities (e.g., applications, services).

### Connection

The relationships or interactions between components in the model. Connections may represent data flow, dependencies, network links, or other types of interactions that are crucial for understanding the system architecture.

### Contextual Model

A flexible framework that allows for the dynamic generation of different views and layouts based on the specific requirements of different user personas (e.g., CTO, architect, developer, DevOps, SecOps, QA). The contextual model adapts the representation of components and relationships to emphasize the aspects most relevant to each role.

### Environment

A specific deployment or context within a workspace, often representing distinct architecture states, requirements, and recommendations. An environment may align with a business function or technical division (e.g., development, production).




## Workspace

The highest-level container within a tenant, supporting organizational hierarchies. Workspaces contain multiple environments, integrations, and users with explicit access. It allows for organizational and project-based management. 
Workspaces :

- belong to Simple or multi-layer org hierarchies (business unit/department/project).
- Have Integration management at the workspace level.
- Contain Environments, architecture models, requirements and recommendations.