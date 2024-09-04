# KubeArchive

KubeArchive is a system that archives Kubernetes objects to permanent storage, which can then be retrieved through an API.
This project was inspired by [Tekton Results](https://github.com/tektoncd/results).

Check the DevConf.CZ 2024 lightning talk (15 min) about KubeArchive in 
[this YouTube stream](https://youtu.be/ipb-_rgFNa4?t=3372) (already pointing to the appropriate timestamp).

## Documentation

Take a look to our docs in https://kubearchive.github.io/kubearchive

## Architecture

![kubarchive architecture diagram](/profile/arch-diagram.jpg)

KubeArchive consists of the following components:

- Custom Resource Definition for `KubeArchiveConfig`
- An operator that reconciles `KubeArchiveConfig` Custom Resources to create APIServerSource CRs and update the `sink-filters` `ConfigMap`
- One or more APIServerSources that send cloud events to a sink
- A sink that receives the cloud events and write the resource information in a DB based on the filters of `sink-filters` `ConfigMap`
- A REST API server that facilitates the retrieval of the archived data
- A CLI that queries both the KubeArchive REST API and the k8s API to expose the resources

The user interacts with KubeArchive by:

- Configuring ***what*** to archive and ***when*** to archive it in through [KubeArchiveConfig CR](https://kubearchive.github.io/kubearchive/main/configuration/kubearchiveconfig.html)
- Querying the KubeArchive API to get archived resources
- Querying the archived and the cluster data through the CLI

## Database Model

![kubearchive_db_model](/profile/db-model.jpg)
