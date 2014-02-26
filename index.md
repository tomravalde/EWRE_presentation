---
title       : Highly integrated urban energy, water and waste resources
subtitle    : EWRE Seminar, 26 February 2014
author      : Tom Ravalde
job	    : "Supervisor: Dr James Keirstead"
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : mathjax       # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
--- 

<!--
There once was a grad at Imperial,
Who thought we should use less material,
He modelled in haste,
Flows of water and waste,
(Energy, water and waste,)
To reduce imports from zones extraterratorial.

There once was a grad at Imperial,
Who thought we should use less material,
He modelled in haste,
Reducing water and waste,
Using programming statements in serial.

Currently his thesis remains ethereal.
Magesterial.
-->

## Urbanisation
<!--
<q>the world is still in the midst of a sweeping and profound urban transformation that is literally changing the face of the planet.</q>
-->


```
## Error: could not find function "ggplot"
```

```
## Error: object 'fig.Trends' not found
```

<figcaption><centre>UN urbanisation forecasts</centre>
</figcaption>

--- .class #id 

## Urbanisation

<div style='text-align: center;'>
<figure>
  <img src="r4-today.png" alt="urb-cycle" align="center" width="600px"/>
  <img src="urbanCycle.png" alt="urb-cycle" align="center" width="650px"/>
</figure>
</div>

<!--
<q>We must understand the trade-offs. You can't look at the water and energy sectors in isolation anymore," Rodriguez says. "You need to have constant feedback between the two.<footer>The Guardian</footer></q>
-->

--- .class #id 

## Environmental strain

<!--
<div style='text-align: center;'>
<figure>
  <img src="overconsumption.png" alt="env-strain" align="center" height="200px"/>
</figure>
-->
<div style='text-align: center;'>
<figure>
  <img src="HDI-EF-Urbanisation.png" alt="LSE-cities" align="center" height="500px"/>
  <figcaption>LSE Cities Report (2012)</figcaption>
</figure>
</div>


--- &twocol

## Economic stability

\begin{align}
\mbox{Population growth} = f(\mbox{current population}, \mbox{resource requirements})
\end{align}

*** =left

<figure>
  <img src="urban-growth-regimes.png" alt="growth-regimes" align="center" height="300px" />
  <figcaption>Bettencourt et al (2007)</figcaption>
</figure>

*** =right

<figure>
  <img src="bettencourt_innovation.png" alt="collapse" align="center" height="300px"/>
  <figcaption>Bettencourt et al (2007)</figcaption>
</figure>

<!--
![Bettencourt](bettencourt_innovation.png)

```
## Error: could not find function "ggplot"
```

```
## Error: object 'fig.urbPop' not found
```

-->



--- &twocol

## Opportunities

*** =left

Co-location of infrastructure:

1. Cascading
   	- CHP
	- Energy from waste/biomass
	- Water reuse
2. Decentralisation
	- Grey water reuse
	- Local generation
	- Solar PV

*** =right

<figure>
  <img src="linearMetabolism.png" width="500px"/>
</figure>

<figure>
  <img src="circularMetabolism.png" alt="circ-met" align="center" width="500px"/>
<figcaption><centre>Future Cities Laboratory</centre>
</figcaption>
</figure>

--- &twocol

## Existing models ...

*** =left

  <img src="energy-network.png" alt="shannGu-network" width="450px"/>

*** =right

  <img src="water-network.png" alt="shannGu-network" width="450px"/>

--- .class #id 

## ...but

<div style='text-align: center;'>
  <img src="shannGu-network.png" alt="shannGu-network" width="400px"/>
  </div>

--- .class #id 

## Urban metabolism

<div style='text-align: center;'>
<figure>
  <img src="urb-met.png" alt="circ-met" align="center" width="700px"/>
  <figcaption>Duvigneaud and Denaeyer-De Smet (1977)</figcaption>
</figure>
</div>



--- .quote

<q> By how much can urban metabolism be improved through models which optimise the integrated provision of energy, water and waste?,</q>

--- .class #id 

## (<font color="red">Non</font>)linearity

|        | Conversion    | Transport |
|--------|---------------|-----------|
| Energy | Dispatchable  | Elec      |
|        | End use       | Gas       |
|        | <font color="red">Renewables</font>    | <font color="red">Heat</font>      |
| Water  | <font color="red">Pump/Dam</font>      | <font color="red">Friction</font>  |
|        | <font color="red">Contamination</font> |           |
| Waste  | Dispatchable  | <font color="red">Wastewater</font>     |
|        | <font color="red">Treatment</font>     |           |

--- &twocol

## Modelling


$$\mbox{production} = \sum_{\mbox{processes}} \mbox{resource ratio} \times \mbox{process rate}$$


*** =left

```
pump water_in -1
pump water_out 1
pump elec_in -98.1


```
<figcaption><centre>Null</centre>
</figcaption>

<img src="null.png" width="350px"/>

*** =right

```
pump water_in mass -1
pump water_in energy 0
pump water_out mass 1
pump water_out energy 98.1
pump elec_in -98.1
```
<figcaption><centre>PRaQ</centre>
</figcaption>

  <img src="PRaQ.png" width="400px"/>

---



```
## Find out what's changed in ggplot2 with
## news(Version == "0.9.3.1", package = "ggplot2")
## Loading required package: plyr
## 
## Attaching package: 'reshape'
## 
## The following object(s) are masked from 'package:plyr':
## 
##     rename, round_any
```

<img src="assets/fig/methods.png" title="plot of chunk methods" alt="plot of chunk methods" style="display: block; margin: auto;" />


--- &twocol

## Case study: Shann Gu

$$\mbox{imports} + \mbox{production} = \mbox{exports} + \mbox{demand}$$

*** =left

<img src="shannGu-network.png" alt="shannGu-network" width="360px"/>

*** =right

<img src="shannGu-zones.png" alt="shannGu-zones" width="360px"/>

---

## Results

<img src="assets/fig/results.png" title="plot of chunk results" alt="plot of chunk results" style="display: block; margin: auto;" />


--- .class #id 

## Future work

- Explore nonlinear options
- Develop case study
	- add resource storage
	- finer spatial and temporal discretisation
- Build pre- and post-processors
- Relate to urban metabolism literature

--- bg:black
