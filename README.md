HEYYY!!


For deploying the backend WITH helm, i have used this ![application](https://github.com/dockersamples/example-voting-app) of voting. I have made helm files of ui and backend of this voting application. 

![vote-application](https://github.com/user-attachments/assets/f3a160ee-02f9-4811-b73b-e4f5123b0355)


A front-end web app in Python which lets you vote between two options


A Redis which collects new votes


A .NET worker which consumes votes and stores them in…


A Postgres database backed by a Docker volume


A Node.js web app which shows the results of the voting in real time

## Prerequisites

- Kubernetes cluster 1.16+
- Helm 3.0+
- Ingress controller (e.g., NGINX Ingress Controller)


## Installation

1. Clone this repository:

```
git clone https://github.com/taniaduggal/taniaduggal-syself-devops1.git
```

2. Install the chart in particular namespace

```
helm install <release-name> <path-of helm-files> -n voting-app --create-namespace (helm install helm-release . -n voting-app --create-namespace)
helm list (to check helm all releases)
```

## Accessing the Application

After deploying the chart, you can access the application at: http://<ingress-host>: NodePort


Replace <ingress-host> with the value specified in your ingress.host.

## Database Deployment Approach

For deploying a production-ready database for application, i recommend this approach:


Use a Managed Database Service: For production environments, it's often best to use a managed database service provided by cloud providers (e.g., Amazon RDS, Google Cloud SQL, Azure Database for PostgreSQL).


Reasons:
- Improved reliability and availability
- Automated backups and point-in-time recovery
- Easier scaling and maintenance
- Built-in security features


## Why I go for Helm Charts?

Templating: Enables dynamic configuration and reusability across environments.


Package management: Bundles related Kubernetes resources into a single unit


Versioning: Facilitates easier rollbacks and upgrades of applications.

Dependency management: Allows defining and managing dependencies between charts.

Simplified deployment: Reduces complexity by abstracting Kubernetes manifest details.

Consistency: Ensures uniform deployments across different clusters and environments.

Parameterization: Allows easy customization without modifying core templates.

Release management: Provides tools for tracking and managing deployed releases.

Additional(Optional): For learning more about Helm or doing more hands-on, i even tried this ![helm-chart](https://github.com/taniaduggal/helm-practice1) for practicing. I know we can use secrets, hashicorp vault for secrets or sensitive data storage, but this meant for practice purpose.
