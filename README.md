
## 🐳 Docker and Kubernetes: The Wrapping Concept

  

Let’s start from the Docker side of things:

  

- In Docker, we use **Docker images**.

- When these images run, they become **Docker containers**.

- Imagine a container as a little box—we’ll call it `app`. This is your application running inside a container.

  

---

  

## 📦 Kubernetes Terminology: The Layered Wrapping

  

Kubernetes introduces a layered structure where everything is wrapped inside something else. Here's how it works:

  

### 1. **Pod**

- A **pod** is the smallest deployable unit in Kubernetes.

- It can contain **one or more containers**.

- Best practice: **one container per pod**.

- Why? If one container fails, Kubernetes may mark the entire pod as unhealthy.

- While there are workarounds, keeping one container per pod simplifies troubleshooting and stability.

  

### 2. **ReplicaSet**

- A **ReplicaSet** wraps around pods.

- It controls the **number of pod replicas** running at any time.

- Example: If your app is under heavy load, you can scale from 1 to 5 pods—each running its own container.

  

### 3. **Deployment**

- A **Deployment** wraps around the ReplicaSet.

- It allows for **version control**:

- Rollbacks

- Rollforwards

- This is useful when updating your application.

  


### 🔁 Summary of Wrapping

| Layer       | Purpose                                 |
|-------------|------------------------------------------|
| Container   | Runs your app                            |
| Pod         | Wraps one or more containers             |
| ReplicaSet  | Controls how many pods are running       |
| Deployment  | Manages updates and versioning           |


  

All of this is defined using a **YAML file**, which we’ll explore next.

  

---

  

## 📄 YAML Basics for Kubernetes

  

YAML is a markup language used to define Kubernetes objects. Here are the essentials:

  

### 🔑 Key Concepts

-  **File extension**: `.yaml` or `.yml` (both are valid)

-  **Indentation**: Always use **two spaces** (never tabs!)

- YAML consists of:

-  **Lists** (arrays)

-  **Dictionaries** (key-value pairs)

  

### 🛒 Example: Shopping List in YAML

  

#### ✅ A Proper List

```yaml

shopping:

- eggs

- milk

- fruit

```

  

#### ✅ A Dictionary

```yaml

shopping:

eggs: 1

milk: 2

fruit: apple

```

  

#### ✅ Nested Lists and Dictionaries

```yaml

purchased:

fruit:

- apple: 1

- banana: 2

need_to_buy:

- coffee

- tea

- milk

```

  

### ⚠️ Common Mistakes

- Using **one space** instead of two breaks the file.

- Copy-pasting from the web can introduce **invisible breaking spaces**.

- Use a VS Code plugin to detect these issues.

  

### Resources

### 🔌 Recommended Plugins

- [Docker Extension for VS Code](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker) — Manage Docker containers and images.
- [Kubernetes Extension for VS Code](https://marketplace.visualstudio.com/items?itemName=ms-kubernetes-tools.vscode-kubernetes-tools) — Interact with Kubernetes clusters directly from VS Code.
- [Kubernetes Snippets](https://marketplace.visualstudio.com/items?itemName=ipedrazas.kubernetes-snippets) — Handy YAML snippets for Kubernetes resources.
- [Non-Breaking Space Highlighter](https://marketplace.visualstudio.com/items?itemName=viktorzetterstrom.non-breaking-space-highlighter) — Highlights invisible non-breaking spaces in your code.

---

### 🚀 Getting Started with Kubernetes

- [Install Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/) — Run a local Kubernetes cluster for development and testing.
- [Play with Kubernetes](https://labs.play-with-k8s.com) — Try out Kubernetes in a browser-based playground.
- [Killerkoda Kubernetes Scenarios](https://www.katacoda.com)](https://killercoda.com/](https://killercoda.com/)) — Interactive tutorials for learning Kubernetes concepts.
