# KubeArchive

KubeArchive is a system that archives Kubernetes objects to permanent storage, which can then be retrieved through an API.
This project was inspired by [Tekton Results](https://github.com/tektoncd/results).

## Architecture

![kubarchive architecture diagram](/profile/arch-diagram.png)

KubeArchive consists of the following components:

- A deployer
- One or more APIServerSources that send cloud events to a sink
- A sink that receives the cloud events and write the resource information in a DB
- A REST API server that facilitates the retrieval of cluster data
- A CLI that queries both the KubeArchive REST API and the k8s API to expose the resources

## Database Model

- WIP. Check [this Miro board](https://miro.com/app/board/uXjVNjKPncc=/) for more information.
