# KubeArchive

KubeArchive is a system that archives Kubernetes objects to permanent storage, which can then be retrieved through an API.
This project was inspired by [Tekton Results](https://github.com/tektoncd/results).

## Architecture

![kubarchive architecture diagram](/profile/arch-diagram.png)

Kubearchive consists of the following components:

- An operator that manages the system as a whole.
- An archive controller that reads data from the cluster.
- An archive service that receives data to archive, and stores it in a database.
- (future) A log storage backend.
- (future) A REST API server that facilitates the storage and retrieval of cluster data.

## Database Model

![kubearchive database model](/profile/database-model.png)
