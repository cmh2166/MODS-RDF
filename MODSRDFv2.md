# Namespaces:
    - abstract=http://id.loc.gov/vocabulary/abstract#
    - access=http://id.loc.gov/vocabulary/access#
    - classSchemes=http://id.loc.gov/vocabulary/classSchemes/
    - identifiers=http://id.loc.gov/vocabulary/identifiers/
    - j.0=http://www.loc.gov/mods/rdf/
    - madsrdf=http://www.loc.gov/mads/rdf/v1#
	- modsrdf=http://www.loc.gov/mods/rdf/v1#
    - note=http://id.loc.gov/vocabulary/note#
    - owl=http://www.w3.org/2002/07/owl#
    - rdf=http://www.w3.org/1999/02/22-rdf-syntax-ns#
    - rdfs=http://www.w3.org/2000/01/rdf-schema#
    - relators=http://id.loc.gov/vocabulary/relators/
    - resourceTypes=http://id.loc.gov/vocabulary/resourceTypes/
    - ri=http://id.loc.gov/ontologies/RecordInfo#
    - targetAudiences=http://id.loc.gov/vocabulary/targetAudiences/
    - xsd=http://www.w3.org/2001/XMLSchema#

# Imported Ontologies:
	- http://www.w3.org/2004/02/skos/core
    - http://xmlns.com/foaf/0.1/
    - http://marklogic3.loc.gov:8281/ontologies/ClassificationSchemes
    - http://marklogic3.loc.gov:8281/ontologies/ResourceTypes
    - http://www.loc.gov/standards/mads/rdf/v1.rdf
    - http://purl.org/vocab/changeset/schema
    - http://vocab.org/changeset/
    - http://www.w3.org/2008/05/skos-xl
    - http://purl.org/dc/dcmitype/
    - http://marklogic3.loc.gov:8281/ontologies/Roles
    - http://purl.org/dc/elements/1.1/
    - http://marklogic3.loc.gov:8281/ontologies/TargetAudiences
    - http://www.loc.gov/mads/rdf/v1
    - http://marklogic3.loc.gov:8281/ontologies/Identifiers
    - http://purl.org/vocab/vann/

# Classes:
	- *AdminMetadata*
		- label: Administrative Metadata
		- comment: Administrative metadata for the description
		- URI: http://id.loc.gov/ontologies/RecordInfo#AdminMetadata
	- *ModsResource*
		- label: MODS - A MODS Resource
		- comment: The resource which is the subject of this description.
		- URI: http://www.loc.gov/mods/rdf/v1#ModsResource
		- Equivalent: http://id.loc.gov/vocabulary/resourceTypes/Res
	- *Cartographics*
		- label: MODS - Cartographic Information
		- comment: Aggregates cartographic properties
		- URI: http://www.loc.gov/mods/rdf/v1#Cartographics
	- *NoteGroup*
		- label: MODS - Note Typed
		- comment: Aggregates a note with its type.
		- URI: http://www.loc.gov/mods/rdf/v1#NoteGroup
	- *Part*
		- label: MODS - Part
		- comment: An aggregator for part properties.
		- URI: http://www.loc.gov/mods/rdf/v1#Part
	- *RoleRelationship*
		- label: MODS - Role Relationship
		- comment: Aggregates a name with its role.
		- URI: http://www.loc.gov/mods/rdf/v1#RoleRelationship
	- *Location*
		- label: MODS - Location
		- comment: Aggregator for location properties
		- URI: http://www.loc.gov/mods/rdf/v1#Location
	- *IdentifierGroup*
		- label: MODS - Identifier - Typed
		- comment: Used when the identifier type is not from the controlled list. Bundles together an identifier and its type.
		- subClassOf: owl:Thing
		- URI: http://www.loc.gov/mods/rdf/v1#IdentifierGroup
	- *ClassificationGroup*
		- label: MODS - Classification Group
		- comment: For a classification whose scheme is not part of the controlled vocabulary. Bundles together a classification number and scheme.
		- subClassOf: owl:Thing
		- URI: http://www.loc.gov/mods/rdf/v1#ClassificationGroup
	- *LocationCopy*
		- label: MODS - Location - Copy
		- comment: An aggregator for copy properties
		- URI: http://www.loc.gov/mods/rdf/v1#LocationCopy
