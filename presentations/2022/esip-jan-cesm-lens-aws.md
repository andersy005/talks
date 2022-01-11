## Community Earth System Model Large Ensemble (CESM LENS) Data Sets on AWS

---
<font size="7">_Anderson Banihirwe_, [@andersy005](https://github.com/andersy005)<img src="../../images/GitHub-Mark/PNG/GitHub-Mark-Light-32px.png"></font>

<font size="6">Software Engineer @ The National Center for Atmospheric Research</font>

<font size="6">ESIP January 2022 Virtual Meeting | 2022-01-19</font>



## What is CESM LENS?

The Community Earth System Model Large Ensemble consists of

- 40-member ensemble of climate simulations for 1920-2100 with slightly different initial conditions<!-- .element: class="fragment" data-fragment-index="2" -->
- Two spatial grids (land/atmosphere and ocean/ice)<!-- .element: class="fragment" data-fragment-index="3" -->
- Multiple vertical axes (surface, 3D atmosphere, 3D ocean)<!-- .element: class="fragment" data-fragment-index="4" -->
- Multiple temporal resolutions (annual, monthly, daily, 6 hours, hourly)<!-- .element: class="fragment" data-fragment-index="5" -->
- The full dataset (data volume ~500 TB)<!-- .element: class="fragment" data-fragment-index="6" --> 
  - Can be accessed for compute in place via NCAR HPC systems<!-- .element: class="fragment" data-fragment-index="7" -->
  - Available for download via NCAR Climate Data Gateway<!-- .element: class="fragment" data-fragment-index="7" -->



## CESM1-LENS on AWS
    
- 100 TB storage allocation from the AWS Open Data Sponsorship Program<!-- .element: class="fragment" data-fragment-index="1" -->
    - AWS covers both egress and S3 storage costs<!-- .element: class="fragment" data-fragment-index="1" -->
- 70 TB subset (of 500 TB) so far<!-- .element: class="fragment" data-fragment-index="2" -->
    - most popular data variables<!-- .element: class="fragment" data-fragment-index="3" -->
    - monthly, daily, and 6-hour frequencies<!-- .element: class="fragment" data-fragment-index="4" -->
    - surface and 3D fields<!-- .element: class="fragment" data-fragment-index="5" -->
    - 278 Zarr stores created from ~10, 000 netCDF files<!-- .element: class="fragment" data-fragment-index="6" -->



## Tools used to create zarr stores

We used [custom scripts](https://github.com/NCAR/data-zarrification) to create zarr stores from the raw CESM netCDF files:

- [intake-esm](https://github.com/intake/intake-esm)<!-- .element: class="fragment" data-fragment-index="1" -->
- [Dask](https://dask.org)<!-- .element: class="fragment" data-fragment-index="2" -->
- [Zarr](https://zarr.readthedocs.io/en/stable/)<!-- .element: class="fragment" data-fragment-index="2" -->
- [Xarray](https://xarray.pydata.org/en/stable/)<!-- .element: class="fragment" data-fragment-index="2" -->
- [Globus](https://www.globus.org/)<!-- .element: class="fragment" data-fragment-index="3" -->



## Example notebooks 

<iframe data-src="http://gallery.pangeo.io/" data-preload width="100%" height="600"></iframe>


## Challenges encountered during the conversation process

- Some of the data were stored on near-line tape archive<!-- .element: class="fragment" data-fragment-index="1" -->
  - Transferring the data from tape archive to local posix filesystem is a slow process<!-- .element: class="fragment" data-fragment-index="1" -->
- Corruption and discrepancy in original netCDF data on disk<!-- .element: class="fragment" data-fragment-index="2" -->
- Deciding on zarr's chunking strategy<!-- .element: class="fragment" data-fragment-index="63" -->



## Thanks!

