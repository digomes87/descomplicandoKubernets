# Utilizando Kubernetes com `kind`

## Pré-requisitos

1. **Docker**: Certifique-se de que você tem o Docker instalado e em execução. Se você ainda não tiver, pode obtê-lo [aqui](https://docs.docker.com/get-docker/).
2. **`kind`**: Instale o `kind` seguindo as instruções [aqui](https://kind.sigs.k8s.io/docs/user/quick-start/).

## Passos Básicos

### 1. Criar um Cluster

```bash
kind create cluster --name nome-do-seu-cluster

### 2. Verificar Clusters Existentes

```bash
kind get clusters


### 3. Configurar kubectl
O kind configura automaticamente kubectl (a ferramenta de linha de comando do Kubernetes) 
para apontar para o cluster que você acabou de criar.

```bash
kubectl get nodes

### 4. Implantar uma Aplicação
Como um exemplo básico, podemos criar um Deployment usando a imagem nginx:

```bash
kubectl create deployment nginx --image=nginx
E depois, expor a aplicação usando um serviço do tipo NodePort:

```bash
kubectl expose deployment nginx --type=NodePort --port=80
Para acessar a aplicação, você precisará obter a porta onde o nginx está sendo exposto. Use o comando a seguir:

```bash
kubectl get services

### 5. Acessar o Dashboard do Kubernetes
O Kubernetes possui um dashboard visual para ajudar na administração. Para configurar e acessar, siga os passos aqui.

### 6. Deletar o Cluster
Quando terminar, você pode deletar o cluster:

```bash
kind delete cluster --name nome-do-seu-cluster
