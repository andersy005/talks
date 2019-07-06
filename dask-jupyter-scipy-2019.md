## Interactive Supercomputing with Jupyter and Dask

<img src="images/scipy-stack/jupyter_logo_white.svg" width="30%">
<img src="images/scipy-stack/dask_horizontal_white.svg" width="30%">

_Anderson Banihirwe, Software Engineer_

National Center for Atmospheric Research (NCAR)

<font size="4">SciPy 2019, Austin, TX.</font > 



### What do we mean by supercomputing?


**WHAT DO WE MEAN BY SUPERCOMPUTING?**
<hr>

- MPI, batch processing...
- Lots of heavy machines managed by sysadmins...
  
<font size="4">Cheyenne is a 5.34-petaflops, high-performance computer operated by NCAR.</font>
<img src="images/ncar/supercomputer.png" alt="Cheyenne" style="width:100%">




### What do we mean by Interactive Supercomputing?


**WHAT DO WE MEAN BY INTERACTIVE SUPERCOMPUTING?**
<hr>

<!-- - A **human-in-the-loop** workflow, rapid iteration...
- Jupyter notebooks, numpy/pandas/visualization... 
- Adaptive scaling of computing resources based on the workload..

 <img src="images/pangeo/iteration.png" alt="Iteration" style="width:70%">

 -->

<div class="row">
  <div class="column">
    <img src="images/pangeo/iteration.png" alt="Iteration" style="width:100%">
  </div>
  <div class="column">
    <ul>
  <li>A <bold>"human-in-the-loop"</bold> workflow, rapid iteration...</li>
  <li>Jupyter notebooks, numpy/pandas/ interactive visualization... </li>
  <li>Adaptive scaling of computing resources based on the workload...</li>
</ul>
  </div>
</div>

**This combination would be powerful...** <!-- .element: class="fragment" data-fragment-index="2" -->

**But it is hard...** <!-- .element: class="fragment" data-fragment-index="3" -->

Note:

- Interact with the job while it is running, rather than submitting to a batch queue and checking back the next day. 
- Often involves a modern UI/UX.
- Adaptive scaling based on the workload
- Responsiveness: short jobs or tasks should start, complete, and return control to the user quickly. 
- Data analysis is inherently a "human-in-the-loop" workflow: 
  - May not have a concretely expressible goal: given a high-resolution global dataset of monthly climate, find "something interesting".
  - "I will know it when I see it"
  - Many trials, previous trials often inform what you try next.
- Without interactivity, we lose the argument for using HPC for Data analysis. 



### Interactive Supercomputing Challenges
<hr>

- Every high performance computing (HPC) system is unique: <!-- .element: class="fragment" data-fragment-index="1" -->
  - Security policies
  - Container experience/policy
  - Queue configuration
  - External node access policies
- Tension between interactive availability and machine utilization (HPC centers often measured on this)... <!-- .element: class="fragment" data-fragment-index="2" -->
- Lack of "elastic scaling" support in HPC workload managers... <!-- .element: class="fragment" data-fragment-index="3" -->

Note:

- Traditional HPC workloads managers don’t have good
support for growing and shrinking allocations based on
availability and/or demand
- Holding unused resources leads to poor utilization
and/or expensive for users



### Enabling Technologies for Interactive Supercomputing


<img src="images/scipy-stack/jupyter_logo_white.svg"
     alt="jupyter logo"
     width="25%">

<div class="row">
  <div class="column">
   <img src="images/scipy-stack/jupyter-notebook-2.png" alt="Part-2" style="width:80%">
  </div>
  <div class="column">
    <ul>
  <li>Based on a set of open standards for interactive computing</li>
  <li>Run in the web browser</li>
  <li>Combine code execution, rich text, mathematics, plots and rich media (all in a Jupyter notebook)...</li>
</ul>
  </div>
</div>


### JUPYTER NOTEBOOKS ON HPC SYSTEMS
<hr>

**Q: But isn't Jupyter already usable on HCP systems?**


**Q: But isn't Jupyter already usable on HCP systems?**
<hr>

**A: Yes, But......**

- **SSH-in**
```console
$ ssh <remote_user>@<remote_host>
```
- **Launch Jupyter on a remote machine**
```console
$ jupyter lab --no-browser --ip=`hostname` --port=<port>
```
- **Set up SSH-tunnel to the remote machine**
```console
$ ssh -N -L <port>:<hostname>:<port> <remote_user>@<remote_host>
```
- **Open the notebook in a browser on the local machine**
```console
$ open http://localhost:<port>/
```



### Jupyter Notebooks on HPC systems
<hr>

**What is missing?**

- Multi-user support
- Pure web-access to HPC resources


<img src="images/scipy-stack/jupyterhub_white.svg"
     alt="jupyterhub logo"
     width="40%">

to the rescue...

- Used to serve Jupyter notebooks to a group of HPC users:
  - Spawns, manages, proxies multiple instances of single-user Jupyter notebook server...
  - Authenticates users...
  - Supports custom spawners...
  - Provides configurable http proxy...
  


### JupyterHub @ NCAR
<hr>

**https://jupyterhub.ucar.edu/**


**JupyterHub @ NCAR: Login**

<img src="images/jhub-ncar/login.png" width="100%">


**JupyterHub @ NCAR: Specifying Job Configuration**

<img src="images/jhub-ncar/job.png" width="100%">


**JupyterHub @ NCAR: A Running Jupyter Server**

<img src="images/jhub-ncar/launcher.png" width="100%">



### TODO: Live Demonstration: JupyterHub



<img src="images/scipy-stack/dask_horizontal_white.svg"
     alt="dask logo"
     width="30%">

<div class="row">
  <div class="column">
    <ul>
  <li>Parallel programming library for Python</li>
  <li>Scales data libraries like Numpy, Pandas, Scikit-Learn, Xarray... </li>
  <li>Deploys on HPC systems</li>
  <li>Culturally native to Scientific Computing</li>
</ul>
  </div>
   <div class="column">
   <ul>
   <li>Provides schedulers for executing task graphs</li>
   </ul>
    <img src="images/scipy-stack/grid_search_schedule.gif" alt="task-graph" style="width:100%">
  </div>
</div>

<!-- -  Parallel programming library for Python
-  Scales data libraries like Numpy, Pandas, Scikit-Learn
-  Deploys on HPC systems
-  Culturally native to Scientific Computing
- Provides schedulers for executing task graphs
<img src="images/scipy-stack/grid_search_schedule.gif" width="80%"> -->



### Dask-jobqueue


**DASK-JOBQUEUE**
<hr>

<div class="row">
  <div class="column">
    <ul>
  <li>Easily deploy Dask on job queuing systems like PBS, Slurm, MOAB, SGE, and LSF, etc...</li>
  <li>Created as a spinoff of the Pangeo project.</li>
  <li>Pythonic user interface that manages dask workers/clusters</li><!-- .element: class="fragment" data-fragment-index="2" -->
</ul>
  </div>
   <div class="column">
   <!-- .element: class="fragment" data-fragment-index="2" -->
   <code class="python">
    
    from dask_jobqueue import PBSCluster
    from distributed import Client
    cluster = PBSCluster(project=.., 
      queue=.., cores=1, processes=1, 
      memory="20GB", walltime=...)
    # Ask for 10 nodes 
    cluster.scale(10)
    # OR scale adaptively based on load
    cluster.adapt(minimum=1, maximum=100, 
                wait_count=60)
    # Connect to remote workers
    client = Client(cluster)

   </code>
   <!-- .element: class="fragment" data-fragment-index="2" -->
   <font size="4">Note: The cluster object stores a configuration for a block of worker nodes that you will be requesting...</font>
  </div>
</div>


**DASK-JOBQUEUE**
<hr>

<div class="row">
  <div class="column">
    <ul>
  <li>Easily deploy Dask on job queuing systems like PBS, Slurm, MOAB, SGE, and LSF, etc...</li>
  <li>Created as a spinoff of the Pangeo project.</li>
  <li>Pythonic user interface that manages dask workers/clusters</li>
</ul>
  </div>
   <div class="column">
   <code class="python">
    
    from dask_jobqueue import SLURMCluster
    from distributed import Client
    cluster = SLURMCluster(project=.., 
      queue=.., cores=1, processes=1, 
      memory="20GB", walltime=...)
    # Ask for 10 nodes 
    cluster.scale(10)
    # OR scale adaptively based on load
    cluster.adapt(minimum=1, maximum=100, 
                wait_count=60)
    # Connect to remote workers
    client = Client(cluster)

   </code>
   <font size="4">Note: The cluster object stores a configuration for a block of worker nodes that you will be requesting...</font>
  </div>
</div>



### TODO: Live Demonstration: Dask-jobqueue



### Adaptive/Elastic scaling, Resilience, etc...


### Adaptive/Elastic scaling
<hr>

_Challenges:_ 
- Balancing cluster resources and performance can be challenging, and requires a lot of experimentation...
- Computational workloads aren't constant, they rather fluctuate throughout the analysis...

**Dask thinks about ...** <!-- .element: class="fragment" data-fragment-index="2" -->

- Scaling up and down <!-- .element: class="fragment" data-fragment-index="2" -->
- Resilience <!-- .element: class="fragment" data-fragment-index="2" -->
- Load balancing <!-- .element: class="fragment" data-fragment-index="2" -->


### Adaptive/Elastic scaling on HPC systems
<hr>

_Solution:_

- Start your Jupyter Notebook, instantiate your dask cluster, and then do science...
- Let dask determine when to scale up and/or down depending on the computational workload...


### Adaptive/Elastic scaling on HPC systems
<hr>

_Benefits:_
- Dask's adaptive scaling improves HPC systems' occupancy / utilization...
- Dask’s resilience against the death of all or part of its workers provides new ways of leveraging job preemption...


 
### Questions? Thoughts?

- https://dask.pydata.org/
- https://jobqueue.dask.org/
- https://distributed.dask.org/
- - [Dask-jobqueue workshop materials](https://github.com/willirath/dask_jobqueue_workshop_materials)
-  [Jupyter for Science User Facilities and High Performance Computing workshop](https://jupyter-workshop-2019.lbl.gov/agenda)
- https://github.com/jupyterhub


**Participate**

Community Issue Tracker: [github.com/pangeo-data/pangeo](https://github.com/pangeo-data/pangeo/issues)
