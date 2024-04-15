# PhysicalRisk

This repository contains a copy of the repositories developed by the [OS-Climate](https://os-climate.org/) community, in which I actively participate as part of the Arfima team. In particular, I have worked in the [Physical Risk & Resilience](https://os-climate.org/physical-risk-resilience/) part, which aims at evaluating the risk increase that financial assets will suffer as a consequence of climate change. For example, depending on different climate scenarios, the probability of suffering a flood will increase in the future as a consequence of more extreme climate events, which will increase the financial risk associated with this asset.
The aim of the project is to quantify this risk increase for several hazards, reaching an estimation of the damage an asset will suffer. 

The project consists of the following repositories:
* [hazard](hazard): this repo contains the code necessary to read different hazard datasets from public sources, modify them as desired in order to build a hazard indicator, convert the data into the desired format and upload it to a Amazon S3 bucket. It uses [xarray](https://xarray.dev/) with [dask](https://www.dask.org/) to handle the datasets and [Zarr](https://zarr.dev/) format to store the data in the Amazon S3 bucket.
* [physrisk](physrisk): this repo reads the hazard indicators from the Amazon S3 bucket and performs all the calculations to compute the damage distribution of a given portfolio.

As part of the Arfima team, I have collaborated to this project by adding more datasets and indicators to the [hazard](https://github.com/os-climate/hazard) repo and building the [official website](https://physrisk.readthedocs.io/en/latest/), which contains a code documentation and explanations about how the different hazard indicators are built.

Besides collaborating with this open-source project, in Arfima have also introduced our own hazard datasets and damage functions as extensions of the existing ones, as well as some additional capabilities. We are also developing our proprietary financial library that gives a monetary value and risk metrics to the damage computed with the OS-Climate code. In addition, we are building our own platform where our clients can upload their portfolio and receive automatically the climate risk valuation. It is based on the [OS-Climate User Interface](https://physrisk-ui-sandbox.apps.odh-cl1.apps.os-climate.org/), built with the [physrisk-api](physrisk-api) and [physrisk-ui](physrisk-ui) repositories, but it also reads financial data in real time from our internal database.
