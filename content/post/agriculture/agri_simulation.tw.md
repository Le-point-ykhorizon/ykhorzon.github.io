+++
author = "ykhorizon"
date = "2017-05-07T18:29:48+08:00"
title = "農業模擬軟體 Survey"
categories = ["agriculture","agriculture/software"]
topics = []
keywords = []
tags = ["software","simulation"]
type = "post"
+++

# Todo for Contents
- 分類工具
- 簡單敘述每個工具目的與功能
- Why Case2

# 引言 - 為什麼需要農業模擬軟體工具?

## Case1: 大範圍農業 - 澳洲農民

請想像一下，如果你一名澳洲的穀物耕種農民，你住在西澳洲(Western Australia)並且擁有一個 1200公頃(相當於 1237甲)的小麥

(以下數據為澳洲各省，平均每個農場的大小)


![](http://www.landcommodities.com/wp-content/uploads/2012/11/Comparison-of-cropping-farm-sizes-in-different-Australian-states-2011.gif)
http://www.landcommodities.com/

![](http://www.abc.net.au/news/image/1142978-3x2-940x627.jpg)
http://www.abc.net.au/news/image/1142978-3x2-940x627.jpg

這種規模必須用 central pivot Irrigation System(下圖為不同作物僅是示意圖)才有辦法澆水達成。在栽種過程中不可避免，需要幫植物澆水，但出動一次這種大機具，不是便宜簡單事情。


![](https://wattsupwiththat.files.wordpress.com/2014/09/potato-crops-720-browser1.jpg)
https://wattsupwiththat.files.wordpress.com/2014/09/potato-crops-720-browser1.jpg


因此 __事先大概知道/粗略評估__ 什麼時候這大片田地上的穀物會缺水，需要澆灌，就變成一個重要的問題。
<!--more-->
## Case2: 農業工程滴灌系統評估

場景轉換到溫室內，你是一名剛採購完一套滴灌系統的農人，你想知道這套系統澆水後，如何決定滴灌出水點、澆水速率，使果樹吸收到足夠的水分？更何況各種不同的土壤材質，對於水分擴散的模式不盡相同，如何知道澆水後的結果？


![](http://www.trickle-l.com/new/gallery/soilpat.gif)


此時就需要土壤濕度的模擬，可以快速驗證出土壤濕度擴散的現象，決定如何配置澆水位置以及澆水速率

![](http://www.scielo.br/img/revistas/sa/v67n1/v67n01a02fig06.gif)


# 工具類型
必須要先打一個預防針，自然環境是一個極為複雜的系統，植物也是非常複雜生命體，要完全模擬出一樣的系統，是不可能的。

但這不代表simulation對於農業完全沒有幫助

Software Simulation Tools 主要分成兩類，各自有不同用途 (我自己分類的)
- Macroscope
- Microscope

__Macroscope:__
> Full Environment System Rough Behavior Simulation (交互作用)

__Microscope:__
> Detail Simulation of Specific Component (精細模擬)

__Macroscope__
重點是 環境系統與植物交互作用的關係，能夠大略被模擬，作為務農決策參考。這類型工具類似 Decision Support System 的其中一個環節

舉例來說：天氣變化，對於植物、土壤的水分散失的關係 (FAO- AquaCrop)

__Microscope__
另外一類是專注在環境系統內特定部分，已精細Model設法重現行為
流體在土壤(孔隙介質)中移動如 HYDRUS-2D

# Software Simulation Tools List - Macroscope

## Python Crop Simulation Environment - PCSE
https://github.com/ajwdewit/pcse
http://pcse.readthedocs.io/en/master/


## APSIM Series
CSIRO (澳洲的聯邦研究機構，類似台灣中研院或工研院)
It contains a suite of modules which enable the simulation of systems  that cover a range of plant, animal, soil, climate and management  interactions

### APSIM
http://www.apsim.info/
- C# .Net 
- Open Source

### APSIMX 
Next Generation for refactoring flexable software architecture 
https://github.com/APSIMInitiative/ApsimX


## AquaCrop - Series
Developed by UN - FAO 
Focus on Plant response to irrigation with soil profile and weather data in daily time step


### AquaCrop
http://www.fao.org/land-water/aquacrop/en/
Paper Title
- AquaCrop—The FAO Crop Model to Simulate Yield Response to Water: II. Main Algorithms and Software Description

### AquaCrop-OS
Paper Title
- AquaCrop-OS: An open source version of FAO's crop water productivity model
http://aquacropos.com/about-2/
Open Source But You need to send a request to auther


## DSSAT
- http://dssat.net/
software application program that comprises crop simulation models for  over 42 crops (as of v4.6). DSSAT is supported by data base management  programs for soil, weather, and crop management and experimental data,  and by utilities and application programs


## SWAP 
- Open Source for 1-D simulation
- https://soil-modeling.org/models/model-descriptions/swap
- Wageningen University (荷蘭 農業、生物科技 強項之研究大學)


## AgMIP
http://www.agmip.org/


# Software Simulation Tools List - Microscope

## HYDRUS - Series

目前 state of the art的 soil hydraulic simulation tool

### HYDRUS 1D 
- Hydrus-1D is a public domain Windows-based modeling environment for analysis of water flow and solute transport in variably saturated porous -media
- Open Source
- Fortran


### HYDRUS 2D/3D
Commercial Software
Freeware for trial without run but not open source
![](https://www.pc-progress.com/Images/Pgm_Hydrus2D/Main/Animation.gif)
![](https://www.pc-progress.com/Images/Pgm_Hydrus3D/MainPg_01_Medium.gif)


## SWIM
APSIM water balance core model
[SWIMv1/SWIMv2](http://www.scisoftware.com/products/swim_details/swim_details.html)


## Drip-Irriwater
Close source ( You can send a email for requesting executable program )
Paper Title
Drip-Irriwater: Computer software to simulate soil wetting patterns under surface drip irrigation
 
 
## SAWCal
Paper Title : 
- SAWCal: A user-friendly program for calculating soil available water quantities and physical quality indices


## Soilphysics
Paper Title 
- soilphysics: An R package for calculating soil water availability to plants by different soil physical indices
- Open Source with R Language


## SOILPSI
Paper Title
- SOILPSI: a potential-driven three-dimensional soil water redistribution model—description and comparative evaluation


## CHEMFLO-2000 
Free But Not Open Source
http://soilphysics.okstate.edu/software/chemflo/chemflo2000/ChemfloManual.pdf
[CHEMFLO-2000, Interactive Software for Simulating Water and Chemical Movement in Unsaturated Soils | Water Research | US EPA](https://www.epa.gov/water-research/chemflo-2000-interactive-software-simulating-water-and-chemical-movement-unsaturated)

UDSA
http://water.usgs.gov/software/lists/groundwater/#gui-and-postproc

## SWAT
USDA
https://www.youtube.com/watch?v=AkVG_YccsVI

## WAVES
WAVES - An integrated energy and water balance model - Software
CSIRO
https://research.csiro.au/software/waves/


## hydromad 
R package 
http://hydromad.catchment.org/


------------


# Pedotransfer function


- In soil science, pedotransfer functions (PTF) are predictive functions of certain soil properties using data from soil surveys. [wiki](https://en.wikipedia.org/wiki/Pedotransfer_function)
## ROSETTA Model
https://www.ars.usda.gov/pacific-west-area/riverside-ca/us-salinity-laboratory/docs/rosetta-model/

## SOILPAR2

# Atmosphere Related Tools
## ETo 
https://cran.r-project.org/web/packages/Evapotranspiration/index.html

# Others

## Agros2D
- numerical solutions of 2D coupled problems in technical disciplines,[wiki](https://en.wikipedia.org/wiki/Agros2D)
- https://github.com/hpfem/agros2d

# Resource Hub for Soil Model

A Summary website of Soil-Water Balance Model

- https://soil-modeling.org/resources-links/model-portal
- [Mission statement — ISMC](https://soil-modeling.org/governance)
- [R.J. Oosterbaan, Software and mathematical (numerical) simulation models, free downloading](https://www.waterlog.info/software.htm)


