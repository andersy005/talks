<img src="images/climpred-logo-inverse.png" width="100%">

**Pangeo Use Case: Analyzing Initialized Climate Prediction System Datasets with climpred**

<font size="6">_Anderson Banihirwe ([@andersy005](https://github.com/andersy005)), Software Engineer_<font size="3">

<font size="5">National Center for Atmospheric Research (NCAR)</font>

<font size="6"><a href="https://www.cpc.ncep.noaa.gov/products/outreach/CDPW/45/">NOAA's 45th Climate Diagnostics & Prediction Workshop</a> | 2020-10-20</font>
<aside class="notes">
    <ul>
      <li>Thanks for the opportunity to speak.</li>
      <li>I work as a software engineer @ the National Center for Atmospheric Research (aka NCAR).</li>
      <li>Today, I am just going to talk about climpred, a Python package designed for handling ensemble re-forecast data.</li>
   </ul>
  </aside>



## Why Care?

**Problem (1)**: Our ability to produce large datasets from Earth System Model (ESM)s
<hr>
Has surpassed our ability to analyze them



## Why Care?

**Problem (2)**: A typical output from an ESM model run in forecast mode contains a lot of dimensions such as

<hr>

`initialization date` , `lead time` , `ensemble member` , `latitude` , `longitude` , and/or `depth`

<hr>

These dimensions are not easy to keep track of during data analysis.


## Why Care?

**Problem (3)**: Scientists spend a consideration portion of their research time

<hr>

writing in-house code solutions (e.g., NCL, MATLAB, GrADS, FORTRAN)  for handling forecast verifications, etc..



## Why Care?

**Question**: Can we spend more time analyzing output and less time writing (and re-writing) code?

<hr>

**Solution**: a resounding yes...


## climpred

[github.com/pangeo-data/climpred](github.com/pangeo-data/climpred)
<img src="images/climpred-repo.png" width="80%">


## Demo



## Roadmap

- Continuously adding new metrics and skill scores to the package. 
- Modularization of the bootstrapping system.
- Addition of new reference forecasts




## Thanks

- Please get involved!
  - https://github.com/pangeo-data/climpred
  - https://gitter.im/climpred

<img src="images/climpred-repo.png" width="50%">
