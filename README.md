# Homelab Cluster


![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white)
![Argo CD](https://img.shields.io/badge/argo-EF7B4D.svg?style=for-the-badge&logo=argo&logoColor=white)
![Talos](https://img.shields.io/badge/Talos%20Linux-gray.svg?style=for-the-badge)
![GitOps](https://img.shields.io/badge/GitOps-yellow.svg?style=for-the-badge)

This is my personal homelab repo. This cluster is used to host interesting projects that I personally use as well as a tool for learning new processes and keeping my skills with Kuberentes updated and sharp as opposed to using Virtual Machines. Although a lot of organizations use and continue to use VM's, Kubernetes always seems to be something that is good to know and develop in skills as it is a common way for organizations to run their applications.

## Infra/Tools

- FluxCD
- Talos
- Cillum
- age & sops


### GitOps & FluxCD

I want my entire kubernetes homelab to be run in a declarative manner all store in Git as a single store of truth. The goal is to setup and run a homelab and run it as I would if this was a realworld production enviroment within an Organization. This means I would like my entire code delivery process to be controlled via Git. This includes both infrastructure and application definitions as code in order to complete updates and rollbacks as well as provide history of changes made over time.  Why Flux? When looking at what tools to use, I mainly focused on looking at either ArgoCD or FluxCD. Each of these tools appear to be well supported by the community and has an active community. Ultimately I decided with Flux due to the current organization I work at uses Flux & I prefer to work from the command line as opposed to from GUI in which case it appears Flux has better CLI tooling than ArgoCD.

### Talos

Looking at which Kuberenetes infrastructure I wanted to run - I was mainly looking at setting up the cluster using either k3s, kubeadm, or Talos. Kubeadm seemed to require alot more management of specific settings then I would want. K3s has a very simple setup and very easy to use, however I ended up using Talos because I like that it is more security oriented in mind and I wanted something a little bit different and more challenging. I also like defining the machine configuration using yaml files for a more declarative manner.

### Cillum

Talos defaults to using fannel, which is probably good enough for my homelab setup. However, I decided that I wanted to use Cillum instead as it seems to provide more customizations later down the line, if needed.


### Secret Management

Since I would like to make my entire homelab repo plubic, I need to make sure I have a way to handle secrets and I do not make them available in my code, which gits pushed to git. Flux has a few recommended ways of handling [secrets](https://fluxcd.io/flux/security/secrets-management/). I ended up choosing using [age & sops](https://fluxcd.io/flux/guides/mozilla-sops/) as flux has some guides on setting it up and recommends using age over openPGP.

## File Structure

The structure is based on the recommended way by FluxCD [FluxCD Repo Structure](https://fluxcd.io/flux/guides/repository-structure/). Currently using the "Monorepo" structure from the documentation.  Althought I currently only have a single production cluster, I plan on eventually working some sort of staging cluster as well. Eventhough I do not have the staging setup, I plan to follow this Repo layout, so it will be easier to use when staging is added.


## Hardware

Currently I have a 3 node cluster. Two Think Centre computers I purchased from Ebay and an Intel Nuc I have had for many years. The Intel Nuc has more RAM than the others, so I am using it as a worker node that could potentially run larger work loads. I also have an older PC with a Intel Arch 750 GPU, which I plan to add to the cluster at a future point.


ControlPlane: 
- Lenovo ThinkCentre M910q Mini Desktop
    - 128GB SSD
    - i5 7th Gen
    - 8GB RAM

Worker1:
- Lenovo ThinkCentre M910q Mini Desktop
    - 128GB SSD
    - i5 7th Gen
    - 8GB RAM


Worker2:
- Intel NUC
    - 256 GB NVME
    - 32 GB RAM
    - i5 7th Gen



