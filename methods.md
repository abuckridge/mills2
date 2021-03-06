---
title: Methods
layout: base
date: 2019-12-12
---
{% include figure.html
  class="img-right"
  width="80%"
  caption="Feastday bread fresh from an horno in Taos, 1985."
  src="sites/images/feastday-bread-taos-1985.jpg"
%}
### METHODOLOGY

This project began like so many other research projects of the 21st century—with a Google search. From the onset, I found numerous secondary sources acknowledging the historic presence of hundreds of flour mills in New Mexico, particularly in the northern part of the state. But as my research continued, I could only find actual documentation for a dozen or so mills. I spent hours at [The Center for Southwest Research](https://elibrary.unm.edu/cswr/) in Albuquerque, and at the archives of the [Fray Angelico Chavez History Library](http://www.palaceofthegovernors.org/library.html) in Santa Fe, but with little success. Traditional methods of historical research left me wanting, and time for the project was running out. 

At that point, I decided to expand my methodology. I had dabbled with text mining in a digital history course the previous year and decided to see if I could use those techniques to scour the digital archives for reference to mills in historic New Mexican newspapers. That method was invaluable to my research and turned out to be the single most effective tool of this project. I detail that process below. 

I had always intended to have a geospatial component to this project, but that too evolved as I got further into my research. I had originally planned on using GIS technologies to create an interactive map of mill sites across New Mexico, but after months of trying to locate abandoned and demolished sites, I had too little data to support an engaging map interface. Then I shifted gears. How could I use GIS to identify areas where mills were most likely to have been? What parameters could I define that would isolate regions of potential mill occurrence? What spatial relationships could I uncover to visualize patterns in New Mexico’s milling history? The methods I employed in this process are detailed below. Check out the “Geographical Perspective” page of this site for further spatial analysis. 

### WHY A DIGITAL INTERFACE?

Becoming a student in the 21st century has changed the way I perceive, consume, and create knowledge—historical, geographical, and otherwise. At the onset of this project, I was tasked with designing the format for presenting my research. Did I want to write a National Register Nomination for a single historic mill? Submit a paper to an academic journal? Create a website? Write a grant? My inner Luddite debated with my budding technologist. 

Ultimately, I chose a digital format over traditional historical publications for a few reasons. Firstly, **websites are living documents**. Unlike printed publications, websites allow their creators to edit, amend, and grow their research, taking into consideration things like changing data and new sources. Secondly, **digital formats offer enormous collaborative potential**. Whereas traditional scholarly publications are largely the work of a single author, digital projects combine the expertise of scholars, computer scientists, and graphic artists, among others. I wanted this project to be collaborative and am thankful for the support of my professor and advisor, Fred Gibbs, and the other historians and archivists who helped me along the way. I hope that this project can serve as a jumping off point for others.

Collaboration does not end in the production phase of digital projects, as it can with traditional print publications. Users get to engage and interact with a site like this. Which brings me to my third point: **websites are one of the best ways to support public history**. The production of knowledge during the digital age has revolutionized the way that communities and individuals access cultural heritage. If I had written a report for this research, it is likely that it would have gone no further than the other dusty essays in my filing cabinet. Instead, I chose a digital interface to have a free public format for accessing my writing, research, code, and spatial analysis. Not only can community members and individuals access these forgotten histories, they can augment them—building on my code or research to support their diverse goals. I used [GitHub](github.com) to manage my project and create this site. It is an amazing tool for collaborative work, and I highly recommend it for digital history projects. 

### TEXT MINING 

So, what exactly is text mining? First of all, text mining is made possible by the fact that more and more documents are either born digital (meaning they never had an analog format, such as an email, tweet, blog, or online news article) or have been digitized. We now have access to millions and millions of documents online, which means that we can do computations on those documents. Text mining is essentially a method of analyzing the words in digital documents—counting their occurrences, looking for patterns and relationships between words, visualizing changes in word use over time, etc. Its applications are diverse across public and private sectors and a variety of software packages offer text mining tools. I used [Antconc](https://www.laurenceanthony.net/software/antconc/) for this project, a free text mining software program created by Laurence Anthony of Waseda University.  

Despite my love of reading through old newspapers, the relatively short time span allotted for this project was not enough to comb through the 307,000 pages of historic New Mexican newspapers digitized on the Library of Congress’s [Chronicling America](https://chroniclingamerica.loc.gov/) website. However, the archivists at the Library of Congress were able to send me JSON files for those pages, which range in date of publication from 1852-1922.  By isolating the pages that included the phrase “grist mill”, I refined that corpus to 706 pages of interest which I uploaded as a corpus into the Antconc software. 

{% include figure.html
  class="img-right"
  width="100%"
  caption="The Library of Congress manages a digital archive of American newspapers dating as far back as 1690. Their collection of New Mexican papers begins in the 1850s."
  src="sites/images/loc-newspapers.png"
%}


Of the seven available tools offered through Antconc, the concordance tool proved to be the most valuable for this project. Concordance allows the user to select a key word to be displayed in its context. Several words are presented on either side of the keyword and the filename is also displayed alongside. With “grist mill” as my key word selection, I was able to quickly scan the corpus for surrounding words of interest such as the name of the mill, the mill owner, the town it served, if it was up for sale or had just been burned in a fire, etc. With each file name referenced alongside, I could easily cross reference the complete original text if I wanted more thorough detail.


{% include figure.html
  class="img-right"
  width="100%"
  caption="The concordance tool searches for words and displays them in their context. Notice also how the txt file is placed alongside and reveals the date of each publication."
  src="sites/images/concordance-crop.png"
%}

What would have taken me years to read using traditional historical research methods, I did in a matter of days. In the months leading up to this text mining analysis, I had only identified seventeen mills. Text mining helped me identify an additional 44 mills and in a fraction of the time. The below map illustrates the location of each mill I identified.

{% include figure.html
  class="img-right"
  width="42%"
  caption="add caption."
  src="sites/images/Historic-mills.jpg"
%}

#### A NOTE ABOUT NAMING CONVENTIONS

Because the levels of data I had for the mills varied, I created a hierarchical naming convention to classify them. Ideally, my sources would list the mill by its name, but when they did not, I would classify them by the owner’s name or ultimately by the locale they served if other data was not available. As such, my list of historic mills includes names such as The Aztec Grist Mill, The Vincente Romero Mill, and The Mountainair Grist Mill. 

### GIS ANALYSIS

For those unfamiliar with the terms Geographic Information Systems and Geographic Information Science (GIS), fear not, you’re almost certainly familiar with some of their applications. If you’ve ever used Google Maps, checked in somewhere on your phone, or used a GPS to find the best route to wherever you were headed, then you’ve used GIS technologies. A Geographic Information System is a framework “designed to capture, store, manipulate, analyze, manage, and present spatial or geographic data” (thanks, wikipedia). GIScience is a field that looks at how to best implement GISystems as well as the social, ethical, and theoretical concerns of GIS. GIS exists at the crossroads of geography, computer science, and graphic design. It is used in fields as diverse as urban planning, health care, military, business, agriculture, and history. 

#### ACQUIRING DATA

Historical GIS can be frustrating. Because it is not as popular as GIS for say physical sciences or urban planning, there is not as much data available. This means you spend a lot of time creating datasets. In my case, I was able to acquire datasets for New Mexico county lines, rivers, and populated places while I had to create datasets for historic military forts, the route of the Atchison Topeka Santa Fe Railroad in the 1880s, and of course grist mills. I also augmented the county data layer by linking it to population data from the 1910 New Mexico Census. 

{% include figure.html
  class="img-right"
  width="30%"
  caption="some quote about forts in nm."
  src="sites/images/forts-nm.jpg"
%}
{% include figure.html
  class="img-right"
  width="70%"
  caption="some quote and census info 1910."
  src="sites/images/census1910.png"
%}


Making the railroad layer was the most fun because it involved a process I enjoy called [georeferencing](https://pro.arcgis.com/en/pro-app/help/data/imagery/overview-of-georeferencing.htm). Essentially, I took the digitized historic railroad map and overlayed a transparent copy of it onto my spatially referenced map of New Mexico. I then selected what are called control points which align locations on the historic map with actual coordinates in the real world. Once aligned, I traced the railroad route to create a new data layer representing that historic line. As for the military forts, I simply uploaded a spreadsheet I had made which included the geographic coordinates for the historic forts and then converted that file into a new point layer. The grist mills were more elusive. I could not find the geographical coordinates for the majority of the mills so instead, they are spatially linked to the towns which they served. 

{% include figure.html
  class="img-right"
  width="52%"
  caption="Although less beautiful than the hand drawn maps of the past, this map is spatially referenced and ready for further analysis."
  src="sites/images/forts-map.png"
%}

{% include figure.html
  class="img-right"
  width="48%"
  caption="The Atchison Topeka and Santa Fe Railroad was the first rail to reach the New Mexican Territory, arriving via Raton Pass in 1880.This map was created by the American Bank Note Company in 1899."
  src="sites/images/ATSF1889-crop.jpg"
%}


#### SPATIAL ANALYSIS

At the risk of getting too technical here, I want to speak a bit about the two basic types of models used in all GIS applications: vector models and raster models. Vectors use a system of points, lines, and polygons to represent space, whereas raster models use a grid or pixel system where each grid is the same size and has a single numerical value. All of the data I acquired and created was vector data. Towns, forts, and mills were represented by points. Rivers and railroad lines were represented as lines, and the counties were represented as polygons. 

Vector models are effective for visualizations and some spatial analysis. For example, a vector model could help me answer questions like how many mills were in each county? Or how far was each mill from a river or railroad? These are interesting questions, but I wanted to find the areas where the confluence of the parameters I set indicated a higher probability of historic mill occurrence. The way I chose to answer that question required raster analysis, so I converted my data to rasters and performed what is called a [Euclidean Distance Analysis](https://desktop.arcgis.com/en/arcmap/10.3/tools/spatial-analyst-toolbox/understanding-euclidean-distance-analysis.htm). 

I overlayed a grid on top of each vector data layer and assigned each cell a numerical value based on its distance from the parameters I set. This way I could visualize how the proximity of a river, town, or fort increased the relative likelihood of a mill having once existed in that region. Because the arrival of the railroad decreased the price and increased the availability of milled grain from the Midwest, railroads actually had a negative effect on New Mexican milling operations, and as such were given a negative weight in my analysis. Ultimately, I overlayed each independent data layer and did some map algebra to determine which areas had the highest value cells for all features and were therefore most likely to once have had a mill nearby. 

<div class="carousel">
  <div><img src="{{ site.baseurl }}/sites/images/d-to-towns.png"/></div>
  <div><img src="{{ site.baseurl }}/sites/images/d-to-forts.png"/></div>
  <div><img src="{{ site.baseurl }}/sites/images/d-to-rivers.png"/></div>
  <div><img src="{{ site.baseurl }}/sites/images/d-to-rails.png"/></div>
  <div><img src="{{ site.baseurl }}/sites/images/aggregate-map.png"/></div>
  <div><img src="{{ site.baseurl }}/sites/images/actual-vs-model.png"/></div>
</div>

The first four maps illustrate the roles that individual features had on the likelihood of mill existence. For example, the closer the fort, the more likely that a mill was nearby. The map titled "Aggregate of Determining Factors" illustrates the combined effects of those individual factors, and the final map compares the actual mill locations to the model of likelihood I created.  

There are tons of opportunities for further spatial analysis on this project. Given more time, it would be interesting to do a temporal analysis to look for trends over time in mill locations. Also, I could not find a good historic digitized map outlining early reservations in New Mexico but would still be curious to see how their introduction changed milling development throughout the region. It would be interesting to map the influence of industrial bread on local milling production too. When did people stop baking bread at home, and how did that change the way people grew and processed grain in New Mexico? And of course, hundreds of historic mills still remain unidentified.  



