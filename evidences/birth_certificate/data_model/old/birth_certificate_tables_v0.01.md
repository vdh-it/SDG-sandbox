# Disclaimer

This page relates to this [version (v0.11)](https://github.com/SEMICeu/SDG-sandbox/blob/master/evidences/birth_certificate/data_model/birth_certificate_diagram_v0.11.pdf) of the model.

---

# Birth Evidence

## Entities

### Birth Evidence
**Definition**: Official document proving the Birth of a Person. 

|     attribute            |     expected type          |     definition                                                                                |     cardinality    | code list | 
|--------------------------|----------------------------|-----------------------------------------------------------------------------------------------|--------------------|-----------|
|     identifier           |     Identifier             |     An unambiguous reference to the Birth Evidence.                                           |     [1..1]         |    N/A    |
|     issuing date         |     Date                   |     The date on which the Birth Evidence was issued.                                          |     [1..1]         |    N/A    |
|     certifies            |     Birth                  |     Attesting in a formal way that the Birth is true.                                         |     [1..1]         |    N/A    |
|     issuing authority    |     Public Organisation    |     A Public Organisation with official authority in charge of issuing the Birth Evidence.    |     [1..1]         |    N/A    | 
|     issuing place        |     Location               |     The Location where the Birth Evidence was issued.                                         |     [0..1]         |    N/A    |


### Birth
**Definition**: The event indicating the moment a Person emerges from the body of another Person (start of life).

|     attribute    |     expected type |     definition                                            |     cardinality    | code list |
|------------------|-------------------|-----------------------------------------------------------|--------------------|-----------|
|     parent one   |     Person        |     The first parent of the child.                        |     [0..1]         |    N/A    |
|     parent two   |     Person        |     The second parent of the child.                       |     [0..1]         |    N/A    |      
|     child        |     Person        |     The Person who is born at the Birth.                  |     [1..1]         |    N/A    |


### Person
**Definition**: An individual person who may be dead or alive, but not imaginary.

|     attribute           |     expected type |     definition                                                                                                                                                                                                                                                                                                                                                                                                                               |     cardinality   |    code list                                                                                                                                                                               | 
|-------------------------|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     identifier          |     Identifier    |     The identifier relation is used to link a Person to any formally issued Identifier for that Person.                                                                                                                                                                                                                                                                                                                                      |     [1..*]        |    N/A                                                                                                                                                                                     |
|     given name          |     Text          |     A given name, or multiple given names, are the denominator(s) that identify an individual within a family. These are given to a Person by his or her parents at birth or may be legally recognised as 'given names' through a formal process. All given names are ordered in one field so that, for example, the given name for Johan Sebastian Bach is “Johan Sebastian”.                                                               |     [1..1]        |    N/A                                                                                                                                                                                     |
|     family name         |     Text          |     A family name is usually shared by members of a family. This attribute also carries prefixes or suffixes which are part of the family name, e.g. “de Boer”, “van de Putte”, “von und zu Orlow”. Multiple family names, such as are commonly found in Hispanic countries, are recorded in the single family name field so that, for example, Miguel de Cervantes Saavedra's family name would be recorded as "de Cervantes Saavedra".     |     [1..1]        |    N/A                                                                                                                                                                                     |
|     date of birth       |     Date          |     A date that specifies the birth date of a Person.                                                                                                                                                                                                                                                                                                                                                                                        |     [1..1]        |    N/A                                                                                                                                                                                     |
|     gender              |     Code          |     The gender of an individual should be recorded using a controlled vocabulary that is appropriate for the specific context. In some cases, the chromosomal or physical state of an individual will be more important than the gender that they express, in others the reverse will be true. What is always important is that the controlled vocabulary used to describe an individual's gender is stated explicitly.                      |     [1..1]        |    [Human Sex](https://op.europa.eu/en/web/eu-vocabularies/at-concept-scheme/-/resource/authority/human-sex/?target=Browse&uri=http://publications.europa.eu/resource/authority/human-sex) |
|     citizenship         |     Jurisdiction  |     The citizenship relationship links a Person to a Jurisdiction that has conferred citizenship rights on the individual such as the right to vote, to receive certain protection from the community or the issuance of a passport. Multiple citizenships are recorded as multiple instances of the citizenship relationship.                                                                                                               |     [0..*]        |    N/A                                                                                                                                                                                     |
|     place of birth      |     Location      |     The Location where a Person was born.                                                                                                                                                                                                                                                                                                                                                                                                    |     [0..1]        |    N/A                                                                                                                                                                                     |


### Jurisdiction 
**Definition**: The authority that an official organisation has, to make legal decisions about somebody/something. 

|     attribute   |     expected type  |     definition                                                                                                          |     cardinality    |  code list                                                                                                                                                                         |
|-----------------|--------------------|-------------------------------------------------------------------------------------------------------------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    name         |     Text           |    The name is simply a string that identifies the Jurisdiction, typically a country, with or without a language tag.   |     [1..1]         |  [Country](https://op.europa.eu/en/web/eu-vocabularies/at-concept-scheme/-/resource/authority/country/?target=Browse&uri=http://publications.europa.eu/resource/authority/country) | 
|    id           |     URI            |    The value for the id property is a URI for that Jurisdiction.                                                        |     [1..1]         |  N/A                                                                                                                                                                              |


### Public Organisation
**Definition**: Any organisation that is defined as being part of the public sector by a legal framework at any level.

|     attribute        |     expected type  |     definition                                                                                                                                                                                                                                                                                                                                                                                       |    cardinality     |   code list   |
|----------------------|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|---------------|
|     preferred label  |     Text           |     As defined in the ORG Ontology, a preferred label is used to provide the primary, legally recognised name of the organisation. An organisation may only have one such name in any given language. Primary names may be provided in multiple languages with multiple instances of the preferred label property.                                                                                   |    [1..*]          |   N/A         |
|     identifier       |     Identifier     |     Many organisations are referred to by an acronym or some other identifier. For example, among the EU institutions, the ECB is the identifier for the European Central Bank, OLAF for the European Anti-Fraud Office, and so on. These are formally recognised by the European Commission which provides a list of such acronyms. Analogous lists should be used in other contexts.               |    [1..*]          |   N/A         |


### Location
**Definition**: A spatial region or named place.

|     attribute              |     expected type  |     definition                                                                                                                                                                                                                                                 |     cardinality    |  code list |
|----------------------------|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|------------|
|     geographic name        |     Text           |     A geographic name is a proper noun applied to a spatial object. The INSPIRE Data Specification on Geographical Names [INGN] provides a detailed model for describing a 'named place', including methods for providing multiple names in multiple scripts.  |     [1..1]         |  N/A       | 
|     geographic identifier  |     URI            |     A URI that identifies the Location.                                                                                                                                                                                                                        |     [1..1]         |  N/A       |
