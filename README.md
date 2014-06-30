Linked Ocean Data - Semantics Smackdown
=======================================

Introduction
------------

This document shows the results from the Semantics Smackdown held at 
Rensselaer Polytechnic Institute, June 2014 as part of the Ocean Data 
Interoperability Platform project. During the final two days of this 
workshop, an approach to linking data using a generic pattern was discussed. 
This was driven by the use cases of interoperability between data 
repositories in the ocean sciences domain and also between ocean sciences data 
repositories and those from other domains. Therefore, the approach taken to 
modelling Linked Ocean Data was to use high level terms from ontologies and 
vocabularies which are well understood in a range of communities (for example 
[PROV][prov] and Observations and Measurements, [O&M][om]) while maintaining the 
references to domain specific ontologies (such as the Ocean Data Ontology, 
[ODO][odo]). 

Contents
--------

1. [Namespaces Used][] A list of the [RDF][rdf] namespaces used within 
this document
1. [Cruise] The Linked Data pattern decided upon to describe a research cruise
1. [Dataset] The Linked Data pattern decided upon to describe a dataset
1. [Geometry] Example encoding of a GeoSPARQL geometry for the Linked Ocean
Data patterns
1. [Observation] The Linked Data pattern decided upon to link an Observations 
and Measurements observation to a dataset
1. [Project] The Linked Data pattern decided upon to describe a project
1. [Temporal Entity] Example encoding of an OWL Time temporal entity for the
Linked Ocean Data patterns
1. [Workshop Participants][] A list of organisations represented at the 
workshop
1. [To-Do][] A list of remaining action items in the generation of this 
document
1. [Files][] A description of the file set presented within the GitHub 
repository

Namespaces Used
---------------
+ arpfo [http://vocab.ox.ac.uk/projectfunding#][]
+ dcat [http://www.w3.org/ns/dcat#][]
+ dcterms [http://www.purl.org/dc/terms/][]
+ foaf [http://xmlns.com/foaf/0.1/][]
+ geo [http://www.opengis.net/ont/geosparql#][]
+ obs [http://def.seegrid.csiro.au/isotc211/iso19156/2011/observation#][]
+ obs-prop [http://environment.data.gov.au/def/op#][]
+ odo [http://ocean-data.org/schema/][]
+ ol-cruise [http://schema.oceanlink.org/cruise#][]
+ prov [http://www.w3.org/ns/prov#][]
+ rdf [http://www.w3.org/1999/02/22-rdf-syntax-ns#][]
+ sf [http://www.opengis.net/ont/sf#][]
+ time [http://www.w3.org/2006/time#][]

Cruise
------
![](https://raw.githubusercontent.com/LinkedOceanData/smackdown-results/master/cruise/CruisePattern.png)

A cruise is a discrete deployment of a platform (normally a research vessel)
which has a trajectory from a port to another, or returning to the port of 
departure. The cruise itself is not a geographic feature, its trajectory is,
therefore an intermediate resource for the trajectory must be instantiated to
which the geometry can be assigned. The linkage is made using classes and
properties from the [OceanLink][] ontology.

Dataset
-------
![](https://raw.githubusercontent.com/LinkedOceanData/smackdown-results/master/dataset/DatasetPattern.png)
During the workshop, dataset entities were deemed to have been generated by
cruise activities. However, there are use cases in operational modes (such
as in [SMAOS][samos]) where the cruise (a single port-to-port deployment of 
a platform, such as a research vessel) is not known. In this case we 
recommend that a PROV activity is created for a given calendar day's activity
on that platform instead of a full cruise instance. This day's activity may
later be mapped to a, for example, R2R cruise instance.

The use of prov:wasAttributedTo and odo:fromInstrument to link a dataset to 
the collecting instrument is optional, is repeatable (i.e. it is a one-to-many
relationship) and no rank or instrument order should be inferred from the use
of these properties. Similarly, the use of odo:hasObservedProperty to state 
the discovery level descriptions of the observed properties within a dataset is
both optional and repeatable.

Geometry
--------

Observation
-----------
![](https://raw.githubusercontent.com/LinkedOceanData/smackdown-results/master/observation/ObservationPattern.png)

Project
-------
![](https://raw.githubusercontent.com/LinkedOceanData/smackdown-results/master/project/ProjectPattern.png)

Temporal Entity
---------------

In order to encode temporal entities associated with cruise deployment dates 
and with project dates, we chose to implement the Temporal Entity objects
from OWL Time. An example encoding of a Temporal Entity is shown below.

	<http://linked.bodc.ac.uk/series/952050#time> a time:TemporalEntity ;
		time:hasBeginning <http://linked.bodc.ac.uk/series/952050#timeBegins> ;
		time:hasEnd <http://linked.bodc.ac.uk/series/952050#timeEnds> .
	
	<http://linked.bodc.ac.uk/series/952050#timeBegins> a time:instance ;
		time:inXSDDateTime "1994-10-31T03:00:00Z"^^xsd:datetime ;
		time:inDateTime <http://linked.bodc.ac.uk/series/952050#timeBeginsDescription> .
	
	<http://linked.bodc.ac.uk/series/952050#timeBeginsDescription> a time:DateTimeDescription ;
		time:unitType time:unitSecond ;
		time:second "00" ;
		time:dayOfWeek time:Tuesday ;
		time:minute "00" ;
		time:hour "03" ;
		time:day "18" ;
		time:month "10" ;
		time:year "1994" ;
		time:dayOfYear "291" ;
		time:timeZone <http://www.w3.org/2006/timezone-world#ZTZ> .
	
	<http://linked.bodc.ac.uk/series/952050#timeEnds> a time:instance ;
		time:inXSDDateTime "1994-10-31T11:02:00Z"^^xsd:datetime ;
		time:inDateTime <http://linked.bodc.ac.uk/series/952050#timeEndsDescription> .
	
	<http://linked.bodc.ac.uk/series/952050#timeEndsDescription> a time:DateTimeDescription ;
		time:unitType time:unitSecond ;
		time:second "00" ;
		time:dayOfWeek time:Monday ;
		time:minute "02" ;
		time:hour "11" ;
		time:day "31" ;
		time:month "10" ;
		time:year "1994" ;
		time:dayOfYear "304" ;
		time:timeZone <http://www.w3.org/2006/timezone-world#ZTZ> .
	
	<http://linked.bodc.ac.uk/series/952050#timeBeginsDescription> a time:DateTimeDescription ;
		time:timeZone <http://www.w3.org/2006/timezone-world#ZTZ> .

Workshop Participants
---------------------
+ Biological and Chemical Oceanography Data Management Office, Woods Hole 
Oceanographic Institution, USA
  - Cyndy Chandler
  - Adam Shepherd
+ British Oceanographic Data Centre, Natural Environment Research Council, UK
  - Adam Leadbetter
  - Rob Thomas
+ Lamont-Doherty Earth Observatory, Columbia University, USA
  - Bob Arko
+ Tetherless World Constellation, Rensselaer Polytechnic Institute, USA
  - Yanning Chen
  - Peter Fox
  - Linyun Fu
  - Patrick West
  - Stephan Zednik
+ Scripps Institution of Oceanography, University of California San Diego, USA
  - Renata Ferreira
+ Shipboard Automated Meterological and Oceanographic System, 
Florida State University, USA
  - Nkem Dockery

To-Do
-----

Files
-----
[data-model.ttl][] A Turtle file containing an abstract data model for Linked 
Ocean Data created during the meeting.

[/cruise][] A file folder for the Linked Data pattern describing a cruise.

[/dataset][] A file folder for the Linked Data pattern describing a project.

[/observation][] A file folder for the Linked Data pattern describing an observation.

[/project][] A file folder for the Linked Data pattern describing a project.

[//]: # (Reference link declarations)
[/cruise]: https://github.com/LinkedOceanData/smackdown-results/tree/master/cruise
[/dataset]: https://github.com/LinkedOceanData/smackdown-results/tree/master/dataset
[/observation]: https://github.com/LinkedOceanData/smackdown-results/tree/master/observation
[/project]: https://github.com/LinkedOceanData/smackdown-results/tree/master/project
[Cruise]: #cruise
[data-model.ttl]: https://github.com/LinkedOceanData/smackdown-results/blob/master/data_model.ttl
[Dataset]: #dataset
[Files]: #files
[http://def.seegrid.csiro.au/isotc211/iso19156/2011/observation#]: http://def.seegrid.csiro.au/isotc211/iso19156/2011/observation#
[http://environment.data.gov.au/def/op#]: http://environment.data.gov.au/def/op#
[http://ocean-data.org/schema/]: http://ocean-data.org/schema/
[http://schema.oceanlink.org/cruise#]: http://schema.oceanlink.org/cruise
[http://www.opengis.net/ont/geosparql#]: http://www.opengis.net/ont/geosparql#
[http://www.opengis.net/ont/sf#]: http://www.opengis.net/ont/sf#
[http://www.purl.org/dc/terms/]: http://www.purl.org/dc/terms/
[http://vocab.ox.ac.uk/projectfunding#]: http://vocab.ox.ac.uk/projectfunding#
[http://www.w3.org/1999/02/22-rdf-syntax-ns#]: http://www.w3.org/1999/02/22-rdf-syntax-ns#
[http://www.w3.org/2006/time#]: http://www.w3.org/2006/time#
[http://www.w3.org/ns/dcat#]: http://www.w3.org/ns/dcat#
[http://www.w3.org/ns/prov#]: http://www.w3.org/ns/prov#
[http://xmlns.com/foaf/0.1/]: http://xmlns.com/foaf/0.1/
[Namespaces Used]: #namespaces-used
[odo]: http://www.ocean-data.org/
[OceanLink]: http://schema.oceanlink.org/
[om]: http://www.opengeospatial.org/standards/om
[prov]: http://www.w3.org/TR/2013/NOTE-prov-overview-20130430/
[rdf]: http://www.w3.org/RDF/
[samos]: http://samos.coaps.fsu.edu/html/
[To-Do]: #to-do
[Workshop Participants]: #workshop-participants