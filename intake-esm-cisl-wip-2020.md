# Intake-esm 

**Making It Easier To Consume Climate**

**and Weather Data**

<font size="5">_Anderson Banihirwe ([@andersy005](https://github.com/andersy005)), Software Engineer_<font size="3">

<font size="6">TDD | IOWA </font>

<font size="6">CISL WIP Talk | 2020-11-04</font>
<aside class="notes">
    <ul>
      <li>thanks a lot to the organizers for the
chance to speak. </li>
      <li>I work as a software engineer in the IOWA group.</li>
      <li>Today, I am going to talk about intake-esm, which is a Python data discovery/cataloging tool for earth system model outputs.</li>
   </ul>
  </aside>



### This Work Had Input From

| Matt Long (NCAR/CGD) | Ryan Abernathey (LDEO) |
|:--------------------:| :-----------------------------------------:|
| Naomi Henderson (LDEO) | Joe Hamman (NCAR/CGD) |
| Kevin Paul (NCAR/CISL) | Sheri Mickelson (NCAR/CISL)| 
| Charles Blackmon Luca (LDEO) | Julia Kent (NCAR/CISL) |
| Brian Bonnlander (NCAR/CISL) | Aaron Spring (Max-Planck-Institut für Meteorologie)|
| Martin Durant (Anaconda inc.) | Many others in the Pangeo community!|

<aside class="notes">
    <p>
     This work had a lot of input from a lot of great colleagues and collaborators some
     of whom are named on this slide and also many others who are part of the Pangeo community.
   </p>
</aside>



## Why Care?

😞 **Problem (1)**: Our ability to produce large datasets from Earth System Models (ESM) 
<hr>
Has surpassed our ability to analyze them
<hr>

```bash
$ # Total number of netCDF files for CMIP6 Data
$ # available on NCAR's GLADE filesystem as of 2020-11-04
$ cd /glade/collections/cmip/CMIP6
$ find -L . -type f -name "*.nc" | wc -l
3616641
$ du -sh --apparent-size --dereference .
1.1P	.
```


## Why Care?

😞 **Problem (2)**: The sheer increase in available climate, weather datasets 

<hr>

demands that scientific analysis tools be **generic**, **frictionless** and **open source**.

<aside class="notes">
   <p>Generic software is software that can perform many different tasks. It is not limited to one particular application.</p>
</aside>



## Why Care?

😞 **Problem (3)**: Scientists spend a considerable portion of their research time ⏰

<hr>

writing in-house, customized code solutions for collecting, homogenizing/cleaning data, etc..

<aside class="notes">
   <p>Generic Software is harder to develop as one has to take into account a lot requirements which will be useful for a number of stakeholders/users.. So, scientists tend to prefer writing in-house, custom solutions</p>
</aside>



## Why Care?

**Question**: Can we spend more time analyzing output and less time writing (and re-writing) code?

<hr>

😀 **Answer**: a resounding yes... with **Analysis Ready Data**...


## "Analysis Ready" Data

With Analysis Ready data:

- Users think in **datasets** not **data files**
- Data are curated and cataloged
- Scientists immediately get to the interesting part of their science work


## Introducing [intake-esm](https://intake-esm.readthedocs.io/en/latest/)

- A data cataloging utility built on top of [intake](https://intake.readthedocs.io/en/latest/), pandas, and xarray. 

- Objectives include facilitating:

    - the discovery of earth's climate and weather datasets via Earth System Model (ESM) data catalog.
    - the seamless ingestion of these datasets into xarray dataset containers.


## Demo: CMIP6 Use Case

Notebook: https://nbviewer.jupyter.org/gist/andersy005/849d248742e46d0025c1c36de1acf8bb



## What's Next?

- Integration with NCAR's Dash Repos
- Merging ESM collection specifications into [SpatioTemporal Asset Catalog (STAC) specification](https://stacspec.org/) to offer a more universal specification standard
  - https://github.com/NCAR/esm-collection-spec/issues/21
- Development of tools to verify and describe catalogued data on a regular basis



## 😀 Thanks! 😀

We need your help and feedback!

- Intake-esm: https://github.com/intake/intake-esm
- Pangeo Discourse: https://discourse.pangeo.io/
