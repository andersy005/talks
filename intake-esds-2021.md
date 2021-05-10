<img src="images/intake-esm/intake-logo-white.png" width="30%">

**Taking the pain out of data access**

<font size="7">_Anderson Banihirwe_</font>

<img src="https://github.githubassets.com/images/icons/emoji/octocat.png">[@andersy005](https://github.com/andersy005)

<font size="6">ESDS WIP Discussion | 2021-05-10</font>

<aside class="notes">
    <ul>
      <li>Thanks for the opportunity to speak.</li>
      <li>Today, I am just going to talk about data catalogs, intake and its plugins.</li>
   </ul>
</aside>



### What impacts the velocity of science? 

**Data, Software, Compute** <!-- .element: class="fragment" -->

- Data: time to find, access, clean data for analysis<!-- .element: class="fragment" -->
- Software: tools that are easily accessible, work well together (composable ecosystem)<!-- .element: class="fragment" --> 
- Compute: access to on-demand, elastically scaled computing
<!-- .element: class="fragment" -->



### Why care? 

**Challenge (1)**: Our ability to produce large datasets from Earth System Models (ESM) 
<hr>
Has surpassed our ability to analyze them
<hr>


### Why care? 

**Challenge (2)**: Traditional methods of data access 
<hr>
Cannot leverage large volumes of data
<hr>

```console
❯ find -L /glade/collections/cmip/CMIP6 -type f -name "*.nc" | wc -l
3785307	
❯ du -sh --dereference /glade/collections/cmip/CMIP6
1.3P	/glade/collections/cmip/CMIP6
```
<!-- .element: class="fragment" -->

```console
❯ find -L /glade/campaign/cgd/cesm/CESM2-LE/timeseries -type f -name "*.nc" | wc -l
4602314	
❯ du -sh --dereference /glade/campaign/cgd/cesm/CESM2-LE/timeseries
1.4P	/glade/campaign/cgd/cesm/CESM2-LE/timeseries
```
<!-- .element: class="fragment" -->


### Why Care?

**Challenge (3)**: Scientists spend a considerable portion of their research time ⏰

<hr>
writing duplicate, customized code solutions for finding, cleaning data
<hr>

<img src="images/intake-esm/no-data-catalog.drawio.svg"><!-- .element: class="fragment" -->


## Why Care?

**Question**: Can we spend more time analyzing output and less time writing (and re-writing) code?

<img src="images/intake-esm/with-data-catalog.drawio.svg"><!-- .element: class="fragment" -->

<hr>
We can reduce time to science with <font style="color:green";>Intake + Data catalogs</font>
<hr>


### Intake 

- Intake is a lightweight package that allows data as declarative code. It provides
  - a consistent API, so that you can investigate and load all of your data with the same commands, without knowing the details of the backend library<!-- .element: class="fragment" --> 
  - an extensible cataloging system<!-- .element: class="fragment" --> 
  - transparent access to remote data and catalogs for a variety of data formats (csv, netcdf, zarr, etc..)<!-- .element: class="fragment" --> 
  - a minimalist, extensible plugin system<!-- .element: class="fragment" --> 
    - The next part of this talk is going to focus on `intake-xarray` and `intake-esm`


## Use case 1: Earth System Model (ESM) outputs

- Working with large datasets. E.g.: CMIP6, CESM Large Ensemble
- How do I find what data sets are available?
- How can I load data from multiple models/ multi scenarios? 

**➜ Solution: intake-esm: https://intake-esm.readthedocs.io/**<!-- .element: class="fragment" -->  


![](images/gifs/demo-time-gif.gif)

[Notebook: https://nbviewer.jupyter.org/github/andersy005/intake-tutorial/blob/bb53df81bd0ce26672539bc7ac109c5aea4de387/notebooks/03-intake-esm-demo.ipynb](https://nbviewer.jupyter.org/github/andersy005/intake-tutorial/blob/bb53df81bd0ce26672539bc7ac109c5aea4de387/notebooks/03-intake-esm-demo.ipynb)



## Use case 2: Observation data products

- Where do I download data from?
- How are the data structured?
- How do I load the data?

**➜ Solution: intake-xarray: https://intake-xarray.readthedocs.io/**<!-- .element: class="fragment" -->  


![](images/gifs/demo-time-gif.gif)

[Notebook: https://nbviewer.jupyter.org/github/andersy005/intake-tutorial/blob/74a4fbdd6bdf41161c3e7f88d7e3e6150dac7a1c/notebooks/03-intake-esm-demo.ipynb](https://nbviewer.jupyter.org/github/andersy005/intake-tutorial/blob/bb53df81bd0ce26672539bc7ac109c5aea4de387/notebooks/04-intake-xarray-demo.ipynb)


## Summary

- Intake provides a very simple yet useful distinction between the data scientists and data engineers/curators
- Intake provides an extensible plugin system
- Data catalogs are neat. Let's have more of those, please -:)
