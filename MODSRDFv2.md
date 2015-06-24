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

# Object Properties:

	- *subjectTemporal*
    	- range: http://www.loc.gov/mads/rdf/v1#Temporal
    	- domain rdf:resource="#ModsResource
		- comment: A subject of the resource which is a temporal expression, expressed in terms of a MADS Temporal.
		- subPropertyOf: subject
		- label: Subject - Temporal
		- URI: 
	- *subjectComplex
    	- range rdf:resource="http://www.loc.gov/mads/rdf/v1#ComplexSubject"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>A subject of the resource composed of several component subjects. </rdfs:comment>
    <rdfs:subPropertyOf>
      <owl:ObjectProperty rdf:about="#subject"/>
    </rdfs:subPropertyOf>
    <rdfs:label rdf:datatype="http://www.w3.org/2001/XMLSchema#string">Subject - Complex</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="subjectHierarchicalGeographic">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#HierarchicalGeographic"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>A subject of the resource which is a hierarchy of geographic entities expressed in terms of a MADS Geographics.</rdfs:comment>
    <rdfs:subPropertyOf>
      <owl:ObjectProperty rdf:about="#subject"/>
    </rdfs:subPropertyOf>
    <rdfs:label>Subject -  Hierarchical Geographic </rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="roleRelationship">
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:range rdf:resource="#RoleRelationship"/>
    <rdfs:comment>Binds a name to the role that the named entity played for the resource. </rdfs:comment>
    <rdfs:label>Role Relationship</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="titleUniform">
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Title"/>
    <rdfs:subPropertyOf>
      <owl:ObjectProperty rdf:ID="title"/>
    </rdfs:subPropertyOf>
    <rdfs:comment>A title which has been distinguished as a uniform title. (This corresponds to a MODS XML titleInfo with 'type=uniform' attribute.) There should be no more than one uniform title.  Represented as a MADS Title, or, if there is a primary name, it is represented as a MADS NameTitle.  </rdfs:comment>
    <rdfs:label>Title - Uniform</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="titlePrincipal">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Title"/>
    <rdfs:subPropertyOf>
      <owl:ObjectProperty rdf:about="#title"/>
    </rdfs:subPropertyOf>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>A title which has been distinguished as the principal  title. (This corresponds to a MODS XML titleInfo with  no type attribute.) There should be no more than one principal title. Represented as a MADS Title.</rdfs:comment>
    <rdfs:label>Title - Principal</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="cartographics">
    <rdfs:range rdf:resource="#Cartographics"/>
    <rdfs:label>Cartographics </rdfs:label>
    <rdfs:comment>A geographic entity expressed in cartographic terms.</rdfs:comment>
    <rdfs:domain rdf:resource="#ModsResource"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedOriginal">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:subPropertyOf>
      <owl:ObjectProperty rdf:ID="relatedItem"/>
    </rdfs:subPropertyOf>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>Relates the described MODS resource to another MODS resource which is an original of the described resource.</rdfs:comment>
    <rdfs:label>Related item - Original</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="placeOfOrigin">
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:label rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >Place</rdfs:label>
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Geographic"/>
    <rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >Place of publication/origin. Used in connection with the origin of a resource, i.e., creation, publication, issuance, etc.  Represented as a MADS Geographic.</rdfs:comment>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="namePrincipal">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Name"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:label>Name -  Principle</rdfs:label>
    <rdfs:subPropertyOf>
      <owl:ObjectProperty rdf:ID="name"/>
    </rdfs:subPropertyOf>
    <rdfs:comment>A name that has been distinguished as the principal name associated with the resource. There should be no more than one name principal name. (The rule for determining the principal name is as follows: If the role associated with the name is 'creator' AND if it is the only name whose role is 'creator' then it is the principal name. Thus if there are more than one name, or no name, whose role is 'creator', then there is no principal name.) If there is a principal name, and if there is a uniform title, then that name and title are to be combined into a nameTitle. </rdfs:comment>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedReferencedBy">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:label>Related item - Referenced By</rdfs:label>
    <rdfs:comment>Relates the described MODS resource to another MODS resource which references the described resource.</rdfs:comment>
    <rdfs:comment></rdfs:comment>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:subPropertyOf>
      <owl:ObjectProperty rdf:about="#relatedItem"/>
    </rdfs:subPropertyOf>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:about="#relatedItem">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>Relates the described MODS resource to another, related MODS resource.</rdfs:comment>
    <rdfs:label>Related Item</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="adminMetadata">
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:label>Administrative Metadata</rdfs:label>
    <rdfs:comment>Administrative metadata for the MODS description, corresponds to recordInfo (MODS XML) which is, minimimally, a Class defined outside of the MADS/RDF namespace. The RecordInfo Class from the RecordInfo ontology is recommended.</rdfs:comment>
    <rdfs:range rdf:resource="http://id.loc.gov/ontologies/RecordInfo#AdminMetadata"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedVersion">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:subPropertyOf rdf:resource="#relatedItem"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>Relates the described MODS resource to another MODS resource which is a different version of the described resource.</rdfs:comment>
    <rdfs:label>Related Item - Other Version</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="subjectGeographic">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Geographic"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>A subject of the resource which is a geographic entity, expressed in terms of a MADS Geographic.</rdfs:comment>
    <rdfs:subPropertyOf>
      <owl:ObjectProperty rdf:about="#subject"/>
    </rdfs:subPropertyOf>
    <rdfs:label>Subject - Geographic </rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="locationCopy">
    <rdfs:label rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >Location - Copy</rdfs:label>
    <rdfs:comment>Information about a specific tangible instance of a bibliographic resource or set which comprises one or more pieces via indication of sublocation and/or locator.</rdfs:comment>
    <rdfs:domain rdf:resource="#Location"/>
    <rdfs:range rdf:resource="#LocationCopy"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedConstituent">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:subPropertyOf rdf:resource="#relatedItem"/>
    <rdfs:label>Related item - Constituent</rdfs:label>
    <rdfs:comment>Relates the described MODS resource to another MODS resource which is a constituent of the described resource. </rdfs:comment>
    <rdfs:domain rdf:resource="#ModsResource"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="subjectOccupation">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Occupation"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>A subject of the resource which is an occupation, expressed in terms of a MADS Occupation.</rdfs:comment>
    <rdfs:subPropertyOf>
      <owl:ObjectProperty rdf:about="#subject"/>
    </rdfs:subPropertyOf>
    <rdfs:label>Subject - Occupation</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="publisher">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Name"/>
    <rdfs:label rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >Publisher</rdfs:label>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >The name of the entity that published, printed, distributed, released, issued, or produced the resource.</rdfs:comment>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:about="#subject">
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:label>Subject</rdfs:label>
    <rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >An abstract property defined for which the various subject catergories (e.g. subjectGenre, subjectTitle) are subproperties.</rdfs:comment>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedReview">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:subPropertyOf rdf:resource="#relatedItem"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>Relates the described MODS resource to another MODS resource which is review of the described resource.</rdfs:comment>
    <rdfs:label>Related item - Review</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="role">
    <owl:equivalentProperty rdf:resource="http://id.loc.gov/vocabulary/relators/role"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>role is an abstract property, for which all terms in the relator vocabulary of roles become subproperties.  Thus for example 'relator:artist' refers to the role 'artist' within that vocabulary. (The prefix 'relator:' is used to denote the namespace for the "relator" vocabulary. The property 'relator:artist' relates the resource to an artist associated with the resource, represented as a mads name.</rdfs:comment>
    <rdfs:label>Role (unbound)</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="subjectTitle">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Title"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>A subject of the resource which is a title, expressed in terms of a MADS Title.</rdfs:comment>
    <rdfs:subPropertyOf rdf:resource="#subject"/>
    <rdfs:label rdf:datatype="http://www.w3.org/2001/XMLSchema#string">Subject - Title</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="subjectGeographicCode">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Geographic"/>
    <rdfs:label>Subject - Geographic Code </rdfs:label>
    <rdfs:comment>A subject of the resource which is a geographic entity, expressed as a geographic code and in terms of a MADS Geographic.</rdfs:comment>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:subPropertyOf rdf:resource="#subjectGeographic"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="noteGroup">
    <rdfs:label rdf:datatype="http://www.w3.org/2001/XMLSchema#string">Note  Group</rdfs:label>
    <rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string">Used for a note with a type (other than "statement of responsibility")</rdfs:comment>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:range rdf:resource="#NoteGroup"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedHost">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:subPropertyOf rdf:resource="#relatedItem"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>Relates the described MODS resource to another MODS resource which is a host of the described resource.</rdfs:comment>
    <rdfs:label>Related item - Host</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="subjectName">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Name"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>A subject of the resource which is a name, expressed in terms of a MADS Name.</rdfs:comment>
    <rdfs:subPropertyOf rdf:resource="#subject"/>
    <rdfs:label>Subject - Name Subject</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="classificationGroup">
    <rdfs:label rdf:datatype="http://www.w3.org/2001/XMLSchema#string">Classification Group</rdfs:label>
    <rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string">Used when classification scheme is not in controlled vocabulary. Bundles together the classification number with its scheme.</rdfs:comment>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:range rdf:resource="#ClassificationGroup"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="part">
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:range rdf:resource="#Part"/>
    <rdfs:comment>Information about a physical part of the resource, including the part number, its caption and title, and dimensions. </rdfs:comment>
    <rdfs:label>Part</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:about="#name">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Name"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>A name  - personal, corporate, conference, or family - associated with the resource. Represented in the MADS namespace. </rdfs:comment>
    <rdfs:label>Name</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedSucceeding">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:subPropertyOf rdf:resource="#relatedItem"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:label>Related item - Suceeding</rdfs:label>
    <rdfs:comment>Relates the described resource to a another MODS resource which suceeded it.</rdfs:comment>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedInstantiation">
    <rdfs:label rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >Related item - Instantiation</rdfs:label>
    <rdfs:subPropertyOf rdf:resource="#relatedItem"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >Relates the described resource to a another MODS resource with different origination information.</rdfs:comment>
    <rdfs:range rdf:resource="#ModsResource"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedReference">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:label rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >Related item - Reference</rdfs:label>
    <rdfs:subPropertyOf rdf:resource="#relatedItem"/>
    <rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >Relates the described MODS resource to another MODS resource which the described resource references.</rdfs:comment>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="roleRelationshipName">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Name"/>
    <rdfs:label>Role Relationship - Name</rdfs:label>
    <rdfs:comment>The name included in a roleRelationship.  The roleRelationship binds an name and a role, where the name is a name associated with the resource and is specified elsewhere via the hasName property.  This mechanism is used when the role is not part of a known vocabulary.  Otherwise, the relationship is expressed by using the role vocabulary term as the property; for example, see relator:creator.</rdfs:comment>
    <rdfs:domain rdf:resource="#RoleRelationship"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:about="#title">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Title"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>A title for the resource. Represented as a MADS Title.</rdfs:comment>
    <rdfs:label>Title</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedFormat">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:subPropertyOf rdf:resource="#relatedItem"/>
    <rdfs:label>Related item - Other Format</rdfs:label>
    <rdfs:comment>Relates the described MODS resource to a similar MODS resource of a different format.</rdfs:comment>
    <rdfs:domain rdf:resource="#ModsResource"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="genre">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#GenreForm"/>
    <rdfs:label>Genre</rdfs:label>
    <rdfs:comment>The genre (or one of several genres) of the resource. Represented in the MADS namespace. </rdfs:comment>
    <rdfs:domain rdf:resource="#ModsResource"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="subjectTopic">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#Topic"/>
    <rdfs:subPropertyOf rdf:resource="#subject"/>
    <rdfs:comment>A subject of the resource which is a topic, expressed in terms of a MADS Topic.</rdfs:comment>
    <rdfs:label>Subject - Topic</rdfs:label>
    <rdfs:domain rdf:resource="#ModsResource"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedSeries">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:subPropertyOf rdf:resource="#relatedItem"/>
    <rdfs:comment>Relates the described resource to a another MODS resource which is a series of which the described resource is a part.</rdfs:comment>
    <rdfs:label>Related item - Series</rdfs:label>
    <rdfs:domain rdf:resource="#ModsResource"/>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="subjectGenre">
    <rdfs:range rdf:resource="http://www.loc.gov/mads/rdf/v1#GenreForm"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:label>Subject - Genre Subject</rdfs:label>
    <rdfs:subPropertyOf rdf:resource="#subject"/>
    <rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >A subject of the resource which is a genre, expressed in terms of a MADS GenreForm.</rdfs:comment>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="identifierGroup">
    <rdfs:range rdf:resource="#IdentifierGroup"/>
    <rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >Used when identifier type is not in controlled vocabulary. Bundles together the identifier with its type.</rdfs:comment>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:label rdf:datatype="http://www.w3.org/2001/XMLSchema#string"
    >Identifier Group</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="locationOfResource">
    <rdfs:range rdf:resource="#Location"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>The location (or one of several locations) at which the resource resides.</rdfs:comment>
    <rdfs:label>Location</rdfs:label>
  </owl:ObjectProperty>
  <owl:ObjectProperty rdf:ID="relatedPreceding">
    <rdfs:range rdf:resource="#ModsResource"/>
    <rdfs:subPropertyOf rdf:resource="#relatedItem"/>
    <rdfs:domain rdf:resource="#ModsResource"/>
    <rdfs:comment>Relates the described MODS resource to a MODS resource which preceded the described resource.</rdfs:comment>
    <rdfs:label>Related item - Preceding</rdfs:label>
  </owl:ObjectProperty>

# Datatype Properties:

# Annotation Properties:


