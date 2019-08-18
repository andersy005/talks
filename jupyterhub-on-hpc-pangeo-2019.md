<img src="images/scipy-stack/jupyterhub_white.svg"
     alt="jupyterhub logo"
     width="70%">
## On HPC

<font size="5">_Anderson Banihirwe ([@andersy005](https://github.com/andersy005)), Software Engineer_<font size="3">

<font size="5">National Center for Atmospheric Research (NCAR)</font>

<font size="4">Pangeo Meeting 2019, Seattle, WA.</font> 



### 2018: Pangeo Meeting Wishlist

- [Can we improve the user experience?](https://medium.com/pangeo/the-2018-pangeo-developers-workshop-1be359dac33c)
  
<img src="images/pangeo/pangeo-past.png" alt="pangeo-wishlist" style="width:100%">

> If only there was a way to run Jupyter notebooks on HPC as a service...
<!-- .element: class="fragment" data-fragment-index="2" -->
<font size="4">https://medium.com/pangeo/the-2018-pangeo-developers-workshop-1be359dac33c</font><!-- .element: class="fragment" data-fragment-index="2" -->


### 2019: Dreams Do Come True*

<img src="images/ncar/jhub-ncar-home.png" alt="ncar-infra" style="width:85%">
  
<font size="3">Along comes JupyterHub on Cheyenne:</font> 
<font size="3">https://dailyb.cisl.ucar.edu/bulletins/jupyterhub-available-use-pre-production-mode</font> 


## Login/Authentication

<img src="images/jhub-ncar/login-jhub.png" width="90%">


## Specifying Job Configuration

<img src="images/jhub-ncar/spawner-jhub-options.png" width="90%">

<font size=4>Thanks to batchspawner: https://github.com/jupyterhub/batchspawner</font>


## Default + Custom Kernels

<img src="images/jhub-ncar/running-notebook-server.png" width="80%">


## Pangeo Loves Science

<img src="images/gifs/jupyterhub-cheyenne=live.gif"
     alt="jhub-demo"
     width="85%">


### 2021: JupyterHub becomes a **first-class service** on Cheyenne's successor! 

<img src="images/ncar/jhub-ncar-future.png" alt="ncar-jhub-future" style="width:200%">

<font size="4">https://dailyb.cisl.ucar.edu/bulletins/jupyterhub-available-use-pre-production-mode</font> 




### 2019: Wishlist

- Testable deployment
  - Would love to hook into JupyterHub's test framework
  - Get CI testing during development - not there yet (:
- Continuous JupyterHub performance monitoring
- JupyterHub Status Page (extension??) for communicating:
  - incidents
  - scheduled maintenances
  - downtimes



### Acknowledgments

- NCAR/CISL Supercomputer Systems, Consulting Services Groups
- Jupyter/JupyterHub development teams
- Pangeo collaborators
