## Constraint Catalog

|                                                                            |            Basic            |           Standard          |           Extended          |            Strict           |
|----------------------------------------------------------------------------|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|
| [Mandatory Node](\#Mandatory_Node)                                         | ![X](../images/table-x.png) | ![X](../images/table-x.png) | ![X](../images/table-x.png) | ![X](../images/table-x.png) |
| [Recommended Node](\#Recommended_Node)                                     |                             | ![X](../images/table-x.png) | ![X](../images/table-x.png) | ![X](../images/table-x.png) |
| [Optional Node](\#Optional_Node)                                           |                             |                             |                             | ![X](../images/table-x.png) |
| [CodeValue of Controlled Vocabulary](\#CodeValue_of_Controlled_Vocabulary) |                             | ![X](../images/table-x.png) | ![X](../images/table-x.png) | ![X](../images/table-x.png) |
| [Maximum Node Occurrence](\#Maximum_Node_Occurrence])                      |                             |                             | ![X](../images/table-x.png) | ![X](../images/table-x.png) |
| [Compilable XPath](\#Compilable_XPath)                                     |                             |                             |                             |                             |
| [Predicate-less XPath](\#Predicate-less_XPath)                             |                             |                             |                             |                             |


### Mandatory Node

#### Definition

* An XML node (element or attribute) described by a predicate-less XPath expression is mandatory to be used within the metadata document. 
* The metadata document is valid, only if the element is present at least one, otherwise invalid.

#### Representation

* DDI Profile
	```xml
	<pr:Used xpath="/codeBook/docDscr/citation/titlStmt/titl" isRequired="true"/>
	```
#### Example
* Valid, because *titl* element is used
	```xml
	<docDscr>
	  <citation>
	    <titlStmt>
	      <titl>DDI2.5 XML CODEBOOK RECORD FOR STUDY NUMBER 2000</titl>
	    </titlStmt>      
	  </citation>
	</docDscr>
	```
	
* Invalid, because *titl* element is not used
	```xml
	<docDscr>
	  <citation>
	    <titlStmt>
	    </titlStmt>      
	  </citation>
	</docDscr>
	```

### Recommended Node

#### Definition

* An XML node (element or attribute) described by a predicate-less XPath expression is recommended to be used within the metadata document. 
* The metadata document is valid, only if the element is present at least one, otherwise invalid.

#### Representation

* DDI Profile
	```xml
	<pr:Used xpath="/codeBook/stdyDscr/citation/rspStmt/AuthEnty" isRequired="false">
	  <pr:Instructions>
	    <r:Content>
	      <![CDATA[
	        <Constraints>
	          <RecommendedNodeContraint/>
	        <Constraints>
	      ]]>
	    </r:Content>
	  </pr:Instructions>
	</pr:Used>
	```

#### Example
* Valid, because *AuthEnty* element is used
	```xml
	<stdyDscr>
	  <citation>
	    <rspStmt>
	      <AuthEnty>Lummis, T., University of Essex. Department of Sociology</AuthEnty>
	    </rspStmt>
	  </citation>
	</stdyDscr>
	```

* Valid, because *AuthEnty* element is not used
	```xml
	<stdyDscr>
	  <citation>
	    <rspStmt/>
	  </citation>
	</stdyDscr>
	```

### Optional Node

#### Definition

* An XML node (element or attribute) described by a predicate-less XPath expression is optional to be used within the metadata document. 
* The metadata document is valid, only if the element is present at least one, otherwise invalid.

#### Representation

* DDI Profile
	```xml
	<pr:Used xpath="/codeBook/stdyDscr/citation/rspStmt/AuthEnty" isRequired="false"/>
	```

#### Example
* Valid, because *AuthEnty* element is used
	```xml
	<stdyDscr>
	  <citation>
	    <rspStmt>
	      <AuthEnty>Lummis, T., University of Essex. Department of Sociology</AuthEnty>
	    </rspStmt>
	  </citation>
	</stdyDscr>
	```

* Valid, because *AuthEnty* element is not used
	```xml
	<stdyDscr>
	  <citation>
	    <rspStmt/>
	  </citation>
	</stdyDscr>
	```




### Value of Controlled Vocabulary 

> NOTE: Work in progress, see [#9](https://bitbucket.org/cessda/cessda.cmv/issues/9)

#### Definition

* A field element in a metadata document uses a controlled vocabulary (CV). 
* The metadata document is valid, only if the field element value equals one of the defined values of the given CV, otherwise invalid.

#### Representation

* DDI Profile
	```xml
	<pr:Used xpath="/codeBook/stdyDscr/stdyInfo/sumDscr/anlyUnit/concept">
	  <pr:Instructions>
	    <r:Content>
	      <![CDATA[
	        <Constraints>
	          <CodeValueOfControlledVocabularyContraint/>
	        <Constraints>
	      ]]>
	    </r:Content>
	  </pr:Instructions>
	</pr:Used>
	<pr:Used xpath="/codeBook/stdyDscr/stdyInfo/sumDscr/anlyUnit/concept/@vocabURI">
	  <pr:Instructions>
	    <r:Content>
	      <![CDATA[
	        <Constraints>
	          <ControlledVocabularyRepositoryConstraint>
                <RepositoryType>eu.cessda.cmv.core.CessdaControlledVocabularyRepository</RepositoryType>
                <RepositoryUri>https://vocabularies.cessda.eu/v1/vocabulary-details/AnalysisUnit/en/2.0</RepositoryUri>
	          <ControlledVocabularyRepositoryConstraint>
	        <Constraints>
	      ]]>
	    </r:Content>
	  </pr:Instructions>
	</pr:Used>
	```

#### Example
* Valid, because *Individual* is item of [AnalysisUnit:2.0](https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:2.0)
	```xml
	<stdyInfo>
	 <sumDscr>
	   <anlyUnit>
	     <concept vocabURI="https://vocabularies.cessda.eu/v1/vocabulary-details/AnalysisUnit/en/2.0">Individual</concept>
	   </anlyUnit>
	 </sumDscr>
	</stdyInfo>
	```
	
* Invalid, because *Person* is **not** item of [AnalysisUnit:2.0](https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:2.0)
	```xml
	<stdyInfo>
	 <sumDscr>
	   <anlyUnit>
	     <concept vocabURI="https://vocabularies.cessda.eu/v1/vocabulary-details/AnalysisUnit/en/2.0">Person</concept>
	   </anlyUnit>
	 </sumDscr>
	</stdyInfo>
	```

### Compilable XPath

An XPath expression must be compilable. This constraint is used only for profile document validation.

```
# valid
/some/compilable/xpath
```

```
# invalid
/some/not compilable/xpath/because-of-blank
```

### Predicate-less XPath

An XPath expression must not contain predicates. This constraint is used only for profile document validation.

```
# valid
/some/xpath/without/precicate
```

```
# invalid
/some/xpath/with/precicate[@version='1.0']
```