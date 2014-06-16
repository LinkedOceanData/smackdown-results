Linked Ocean Data - Semantics Smackdown
=======================================

Introduction
------------

This document shows the results from the Semantics Smackdown held at Rensselaer Polytechnic Institute, June 2014 as part of the Ocean Data Interoperability Platform project. During the final two days of this workshop, an approach to linking data using a generic pattern was discussed. This was driven by the use cases of interoperability 

Contents
--------

1. [Namespaces Used][] A list of the [RDF][rdf] namespaces used within this document
2. [Worshop Participants][] A list of organisations represented at the workshop
2. [To-Do][] A list of remaining action items in the generation of this document
3. [Files][] A description of the file set presented within the GitHub repository

Namespaces Used
---------------
+ arpfo [http://vocab.ox.ac.uk/projectfunding#][]
+ dcterms [http://www.purl.org/dc/terms/][]
+ foaf [http://xmlns.com/foaf/0.1/][]
+ obs [http://def.seegrid.csiro.au/isotc211/iso19156/2011/observation#][]
+ obs-prop [http://environment.data.gov.au/def/op#][]
+ odo [http://ocean-data.org/schema/][]
+ prov [http://www.w3.org/ns/prov#][]
+ rdf [http://www.w3.org/1999/02/22-rdf-syntax-ns#][]
+ time [http://www.w3.org/2006/time#][]


Workshop Participants
---------------------
+ Biological and Chemical Oceanography Data Management Office, Woods Hole Oceanographic Institution, USA
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
+ Shipboard Automated Meterological and Oceanographic System, Florida State University, USA
  - Nkem Dockery


To-Do
-----
1. Add the geometry discussion results to the cruise example

Files
-----
[data-model.ttl][] A Turtle file containing an abstract data model for Linked Ocean Data created during the meeting.

[/cruises][] A file folder for the Linked Data pattern describing a cruise.

[//]: # (Reference link declarations)
[/cruises]: https://github.com/LinkedOceanData/smackdown-results/tree/master/cruise
[data-model.ttl]: https://github.com/LinkedOceanData/smackdown-results/blob/master/data_model.ttl
[Files]: #files
[http://def.seegrid.csiro.au/isotc211/iso19156/2011/observation#]: http://def.seegrid.csiro.au/isotc211/iso19156/2011/observation#
[http://environment.data.gov.au/def/op#]: http://environment.data.gov.au/def/op#
[http://ocean-data.org/schema/]: http://ocean-data.org/schema/
[http://www.purl.org/dc/terms/]: http://www.purl.org/dc/terms/
[http://vocab.ox.ac.uk/projectfunding#]: http://vocab.ox.ac.uk/projectfunding#
[http://www.w3.org/1999/02/22-rdf-syntax-ns#]: http://www.w3.org/1999/02/22-rdf-syntax-ns#
[http://www.w3.org/2006/time#]: http://www.w3.org/2006/time#
[http://www.w3.org/ns/prov#]: http://www.w3.org/ns/prov#
[http://xmlns.com/foaf/0.1/]: http://xmlns.com/foaf/0.1/
[Namespaces Used]: #namespaces-used
[rdf]: http://www.w3.org/RDF/
[To-Do]: #to-do
[Worshop Participants]: #workshop-participants