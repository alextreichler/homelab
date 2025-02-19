# Homelab Cluster

This is my personal homelab repo. This cluster is used to host interesting projects that I personally use as well as a tool for learning new processes and keeping my skills with Kuberentes updated and sharp. 

## Infra/Tools

- FluxCD
- Talos
- Cillum


## Structure

The structure is based on the recommended way by FluxCD [FluxCD Repo Structure(https://fluxcd.io/flux/guides/repository-structure/)]. Currently using the "Monorepo" structure from the documentation.  Althought I currently only have a single production cluster, I plan on eventually working some sort of staging cluster as well. Eventhough I do not have the staging setup, I plan to follow this Repo layout, so it will be easier to use when staging is added.


## Hardware

Currently I have a 3 node cluster. Two Think Centre computers I purchased from Ebay and an Intel Nuc I have had for many years. The Intel Nuc has more RAM than the others, so I am using it as a worker node that could potentially run larger work loads. I also have an older PC with a Intel Arch 750 GPU, which I plan to add to the cluster at a future point in time.


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



