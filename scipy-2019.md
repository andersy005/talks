
Turning HPC Systems into Interactive Data Analysis Platforms using Jupyter and Dask
------------------------------------------------------------------------------------

<img src="images/jupyter_logo_white.svg" width="30%">
<img src="images/dask_horizontal_white.svg" width="30%">

*Anderson Banihirwe, Software Engineer*

National Center for Atmospheric Research



### Introduction
    
- Large high-performance computer (HPC) clusters are very common among scientific/research groups. <!-- .element: class="fragment" data-fragment-index="1" -->

- These systems consist of powerful hardware such as: <!-- .element: class="fragment" data-fragment-index="2" -->
  - large compute nodes <!-- .element: class="fragment" data-fragment-index="2" -->
  - high-speed interconnects <!-- .element: class="fragment" data-fragment-index="2" -->
  - and parallel file systems. <!-- .element: class="fragment" data-fragment-index="2" -->


**Example: Cheyenne Supercomputer**

Cheyenne is a 5.34-petaflops, high-performance computer operated by NCAR
  <br>
    <img src="images/cheyenne-2.png" width="50%"/> 



### Jupyter on HPC systems

**Commonly, inconvenient used setup:**
- SSH-in <!-- .element: class="fragment" data-fragment-index="1" -->
- Launch Jupyter <!-- .element: class="fragment" data-fragment-index="1" -->
- Set up SSH-tunnel process <!-- .element: class="fragment" data-fragment-index="1" -->


**JupyterHub to rescue:**

- Centralized service to deploy notebooks in a standard authenticated manner.
- Access to HPC resources through single interface: Filesytems, Batch Queue, Network


### Jupyter @ NCAR: jupyterhub.ucar.edu

**Login**

<img src="images/jhub-ncar/login.png" width="100%">


**Job Configuration**

<img src="images/jhub-ncar/job.png" width="100%">


**Running Jupyter Server**

<img src="images/jhub-ncar/spawner.png" width="100%">

<img src="images/jhub-ncar/launcher.png" width="100%">





### The Problem

 - HPC systems are a bit hard to use with anything other than MPI



### The solution: Dask on HPC Machines

- To facilitate deploying dask on HPC systems, `dask-jobqueue` package was created as a spinoff of the Pangeo project. 


- Dask-jobqueue allows launching Dask on traditional HPC job schedulers like:
    - PBS
    - SLURM
    - SGE
    - Torque
    - LSF
    - and others commonly found on HPC systems



- Dask-jobqueue provides a *Pythonic* user interface that manages dask workers/clusters through
  - submission
  - execution 
  - and deletion of individual jobs on an HPC system
  


- Dask-jobqueue gives users the ability to interactively scale workloads across large HPC systems; turning an interactive Jupyter Notebook into a powerful tool for scalable computation on very large datasets. 



### Dask-Jobqueue Setup

```python
from dask_jobqueue import PBSCluster
cluster = PBSCluster(project=..., queue=..., cores=1, 
                     processes=1, memory="20GB",
                     walltime="00:30:00")
```

The cluster object stores essentially a configuration for a block of worker nodes that you will be requesting:

```python
print(cluster)
PBSCluster(cores=0, memory=0 B, workers=0/0, jobs=0/0)
```



### Dask-jobqueue Setup 

```python
from dask_jobqueue import SLURMCluster
cluster = SLURMCluster(project=..., queue=..., cores=1, 
                       processes=1, memory="20GB", 
                       walltime="00:30:00")
```



### Dask-jobqueue Setup 

```python
from dask_jobqueue import SGECluster
cluster = SGECluster(project=..., queue=..., cores=1,  
                     processes=1, memory="20GB", 
                     walltime="00:30:00")
```



### Scaling

- Scale cluster to n dask workers 


### Scaling: Manual

```python
cluster.scale(10)
```


### Scaling: Adaptive Scaling based on load

```python
cluster.adapt(minimum=1, maximum=100, wait_count=60)
```


### Advantages of adaptive scaling

- Configuring clusters to balance resources and performance can be challenging, and requires a lot of experimentation.
- Computational workloads aren't constant, they rather fluctuate throughout the analysis.
- Start your Jupyter Notebook, instantiate your dask cluster, and then do science 
- Let dask determine when to scale up and down depending on the commputational workload
- The bursting approach to interactive parallel computing offers many benefits



