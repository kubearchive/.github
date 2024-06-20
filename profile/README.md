# KubeArchive

KubeArchive is a system that archives Kubernetes objects to permanent storage, which can then be retrieved through an API.
This project was inspired by [Tekton Results](https://github.com/tektoncd/results).

Check the DevConf.CZ 2024 lightning talk (15 min) about KubeArchive in 
[this YouTube stream](https://youtu.be/ipb-_rgFNa4?t=3372) (already pointing to the appropriate timestamp).

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
