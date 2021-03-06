# Disclaimer

This page relates to this [version (v0.01)](university_diploma_evidence_diagram_v0.01.png) of the model.

---
# University Diploma Evidence

## Entities

### University Diploma Evidence
**Definition**: Official document bearing record of graduation from, or of a degree conferred by, a university.

|     attribute               |     expected type          |     definition                                                 		                        |     cardinality    | code list |
|-----------------------------|----------------------------|------------------------------------------------------------------------------------------------|--------------------|-----------| 
|     identifier              |     Identifier             |     An unambiguous reference to the University Diploma Evidence.                               |     [1..1]         | N/A       |
|     academic qualification  |     Text                   |     The academic qualification of the University Diploma.              					    |     [1..1]         | N/A       |
|     overall grade           |     Text                   |     A mark indicating a degree of accomplishment.                                              |     [1..1]         | N/A       |
|     issuing date            |     Date                   |     The date on which the University Diploma was issued.                                       |     [1..1]         | N/A       |
|     issuing authority       |     Issuing Authority      |     The Public Organisation that issued the University Diploma Evidence.                       |     [1..1]         | N/A       |
|     issuing place           |     Location               |     The Location where the University Diploma Evidence was issued.                             |     [0..1]         | N/A       |
|     belongs to              |     Student			       |     The Student to which the University Diploma belongs.                                   	|     [1..1]         | N/A       |
|     obtained at             |     Education Institution  |     The Education Institution that delivered the University Diploma Evidence.    		        |     [1..1]         | N/A       |
 

### Education Institution
**Definition**: An Organisation that provides instructional services to individuals or education-related services to individuals and other educational institutions.

**Subclass of**: Public Organisation

*No additional attributes are defined for this entity. It does inherit, however, all the attributes from Public Organisation listed here below.*


### Public Organisation
**Definition**: Any organisation that is defined as being part of the public sector by a legal framework at any level.

|     attribute           |     expected type  |     definition                                                                                                                                                                                                                                                                                                                                                                                |    cardinality     | code list |
|-------------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-----------|
|     preferred label     |     Text           |     As defined in the ORG Ontology, a preferred label is used to provide the primary, legally recognised name of the organisation. An organisation may only have one such name in any given language. Primary names may be provided in multiple languages with multiple instances of the preferred label property.                                                                            |    [1..*]          |  N/A      |
|     identifier          |     Identifier     |     Many organisations are referred to by an acronym or some other identifier. For example, among the EU institutions, the ECB is the identifier for the European Central Bank, OLAF for the European Anti-Fraud Office, and so on. These are formally recognised by the European Commission which provides a list of such acronyms. Analogous lists should be used in other contexts.        |    [1..*]          |  N/A      |
|     registered location |     Location       |     The registered location of the Public Organisation.   																																																																																       |    [0..1]          |  N/A      |


### Student
**Definition**: A Person who attended school.

|     attribute   				 |     expected type  		|     definition                                                                                  	|     cardinality    | code list | 
|--------------------------------|--------------------------|---------------------------------------------------------------------------------------------------|--------------------|-----------| 
|     student ID number 		 |     Identifier        	|     An unambiguous reference to the Student.										        		|     [1..1]         | N/A       |


### Person
**Definition**: An individual person who may be dead or alive, but not imaginary.

|     attribute           |     expected type |     definition       											 																																																																																												|     cardinality   | code list |
|-------------------------|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|-----------|
|     identifier          |     Identifier    |     The identifier relation is used to link a Person to any formally issued Identifier for that Person.     																																																																																	|     [1..*]        | N/A       |
|     given name          |     Text          |     A given name, or multiple given names, are the denominator(s) that identify an individual within a family. These are given to a Person by his or her parents at birth or may be legally recognised as 'given names' through a formal process. All given names are ordered in one field so that, for example, the given name for Johan Sebastian Bach is “Johan Sebastian”.                                                                  |     [1..1]        | N/A       |
|     family name         |     Text          |     A family name is usually shared by members of a family. This attribute also carries prefixes or suffixes which are part of the family name, e.g. “de Boer”, “van de Putte”, “von und zu Orlow”. Multiple family names, such as are commonly found in Hispanic countries, are recorded in the single family name field so that, for example, Miguel de Cervantes Saavedra's family name would be recorded as "de Cervantes Saavedra".        |     [1..1]        | N/A       |
|     date of birth       |     Date          |     A date that specifies the birth date of a Person.                                                                                                                                                                                                                                                                                                                                                                                           |     [1..1]        | N/A       |
|     place of birth      |     Location      |     The Location where a Person was born.                                                                                                                                                                                                                                                                                                                                                                                                       |     [0..1]        | N/A       |


### Location
**Definition**: A spatial region or named place.

|     attribute             |     expected type  |     definition                                                                                                                                                                                                                                                     |     cardinality    | code list |
|---------------------------|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-----------|
|     geographic name       |     Text           |     A geographic name is a proper noun applied to a spatial object. The INSPIRE Data Specification on Geographical Names [INGN] provides a detailed model for describing a 'named place', including methods for providing multiple names in multiple scripts.      |     [1..1]         | N/A       | 
|     geographic identifier |     URI            |     A URI that identifies the location.                                                                                                                                                                                                                            |     [1..1]         | N/A       |
