<img src="https://github.com/zarr-developers/zarr-python/blob/994f2449b84be544c9dfac3e23a15be3f5478b71/docs/_static/logo1.png?raw=true" width="30%">

**chunked, compressed, multidimensional arrays**

<font size="6">_Anderson Banihirwe ([@andersy005](https://github.com/andersy005)), Software Engineer_<font size="3">

<font size="6">National Center for Atmospheric Research (NCAR)</font>

<font size="5">Cloud Native Geospatial Outreach Day | 2020-09-08</font>
<aside class="notes">
    <ul>
      <li>Thanks for the opportunity to speak.</li>
      <li>I work as a software engineer @ the National Center for Atmospheric Research (aka NCAR).</li>
      <li>Today, I am just going to talk about intake which is a Python data discovery/cataloging tool and intake-esm, an intake plugin for earth system model outputs.</li>
   </ul>
  </aside>



## Why Care?

Geo-spatial data come in several different data formats


## Why Care?

Traditional data formats:

- netCDF
- HDF5
- GeoTIFF

These formats are effective for traditional disk storage, but are less efficient for modern cloud-focused technologies. 


## Why Care?

Newer cloud optimized data formats:

- Cloud Optimized GeoTIFF (COG): [cogeotiff](https://github.com/cogeotiff)
- TileDB: [TileDB-Inc/TileDB](https://github.com/TileDB-Inc/TileDB)
- **Zarr**



## What is Zarr?

- [Zarr](https://zarr-specs.readthedocs.io/en/core-protocol-v3.0-dev/index.html) is foremost **a data model/specification** that provides a protocol for storing and retrieving chunked, compressed multi-dimensional arrays.


- As of today, the zarr spec has implementations in the following languages:
  - **Python**: [zarr-developers/zarr-python](https://github.com/zarr-developers/zarr-python)
  - **TypeScript**: [gzuidhof/zarr.js](https://github.com/gzuidhof/zarr.js/)
  - **C++**: [constantinpape/z5](https://github.com/constantinpape/z5)
  - **Julia**: [meggart/zarr.jl](https://github.com/meggart/Zarr.jl)
  - **Java**: [saalfeldlab/n5-zarr](https://github.com/saalfeldlab/n5-zarr)
  - **Scala**: [lasersonlab/ndarray.scala](https://github.com/lasersonlab/ndarray.scala)
  - **C**: [Unidata/netcdf-c/libnczarr](https://github.com/Unidata/netcdf-c/tree/master/libnczarr)


## Core Features

<img src="images/zarr/zarr-hierarchy.drawio.svg">


![](images/zarr/zarr-create.png)


## Core Features: Chunks

![](images/zarr/zarr-chunks.png)


## Core Features: Compression

- **lossless**: reversible i.e. data can be restored in its original form.
- **lossy**: irreversible i.e. some information is lost (can't go back to the original)

[zarr-developers/numcodecs](https://github.com/zarr-developers/numcodecs) Python package provides a high level API for configuring compression and filters for zarr arrays.


## Core Features: Compression

![](images/zarr/zarr-compression.png)



## Core Features: Storage

- In-Memory Store (Dictionary, Memory, LRUCache)
- Database Store (SQLite, Redis, MongoDB, etc..)
- POSIX filesystem (Directory store, Zip store)
- Cloud Object Storage (GCS, S3, Azure, etc...)
- Bring Your Own. **Zarr arrays can be stored in any key-value store**


#### Zarr in Action: AWS and Google Public Datasets

<img src="images/zarr/aws-public-datasets.png" width="50%">



### Thanks!
