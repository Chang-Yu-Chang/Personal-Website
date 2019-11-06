+++
# Date this page was created.
date = "2018-03-08"

# Project title.
title = "Migration and Microbial Community"

# Project summary to display on homepage.
summary = "Microbe forms dynamical and complex community in nature."

# Optional image to display on homepage (relative to `static/img/` folder).
#image_preview = "bubbles.jpg"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["microbe"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Optional featured image (relative to `static/img/` folder).
[header]
image = "headers/bubbles-wide.jpg"
caption = "My caption :smile:"

+++

Something about the migration project.

# Poster


# Consumer-resource model

Here I use MacArthur's consumer-resource model to simulate the microbe growing in a chemostat. The model discription is as below. Other details are extended based on this model.

## Model description
I modify MacArthur's consumer resource model to include consumers with stoichiometric metabolism. The model consists of one supplied resources ``$R_1$`` exploited by a specialist ``$X_1$`` and a generalist consumers ``$X_2$``, while the specialist consumes supplied resources and secretes another resource ``$R_2$`` as by-product. 

Given that total number of resource type ``$P$`` and total number of consumers ``$S$`` in this system, the growth rate of consumer ``$i$`` is defined by

``$$
\frac{dX_i}{dt}=\sum^P_{j=1} X_iw_j^iu_j^i-m_iX_i
$$``


where ``$X_i$`` and ``$R_j$`` are the biomass of consumer ``$i$`` and resource ``$j$``, respectively. ``$m_i$`` is the density-independent loss rate of consumers ``$j$``, ``$w_{ij}$`` is the conversion efficiency of resource ``$j$`` converted into biomass of consumer ``$i$``, and ``$u_{ij}$`` denotes the uptaking rate for consumer ``$i$`` to use resource ``$j$``.

Resource is supplied in chemostat fashion. Let the dynamics of resource ``$j$`` be given by

``$$
\frac{dR_j}{dt}=J(R_{supply,j}-R_j)+\sum_{i=1}^{S}\sum_{k=1}^{P} D_{kj}^i u_{k}^{i} R_k X_i
$$``

The first term defines the resource supplement from environment external to this system, while the second term denote that from cross-feeding. In the first term, resource is supplied at flow rate ``$J$`` and inflow concentration ``$R_{supply,j}$``. In the second term, ``$D_{jk}^i$`` is a stoichiometric matrix of consumer that describes the metabolic networks of consumer ``$i$`` which uptakes and transforms resource ``$k$`` into secreted resource ``$j$``.


--

Thanks to the helpful information from [this post](https://stackoverflow.com/questions/42938394/problems-with-math-in-r-blogdown-package-in-md-files-with-hugo) for editing equation in markdown files.
