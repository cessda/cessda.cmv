### Constraint Catalogue

---

* Each constraint is described by its semantic definition, xml representation and example usage. 
* Constraints are assigned to pre-defined [validation gates](../user-documentation/glossary.html#Validation_Gate) `Basic`, `Standard`, `Extended` and `Strict` to support different levels of validation strictness.

|                                                                            |            Basic            |           Standard          |           Extended          |            Strict           |
|----------------------------------------------------------------------------|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|
| [Mandatory Node](\#Mandatory_Node)                                         | ![X](../images/cessda/table-x.png) | ![X](../images/cessda/table-x.png) | ![X](../images/cessda/table-x.png) | ![X](../images/cessda/table-x.png) |
| [Recommended Node](\#Recommended_Node)                                     |                             | ![X](../images/cessda/table-x.png) | ![X](../images/cessda/table-x.png) | ![X](../images/cessda/table-x.png) |
| [Optional Node](\#Optional_Node)                                           |                             |                             |                             | ![X](../images/cessda/table-x.png) |
| [Code Value of Controlled Vocabulary](\#Code_Value_of_Controlled_Vocabulary) |                             | ![X](../images/cessda/table-x.png) | ![X](../images/cessda/table-x.png) | ![X](../images/cessda/table-x.png) |
| [Maximum Node Occurrence](\#Maximum_Node_Occurrence])                      |                             |                             | ![X](../images/cessda/table-x.png) | ![X](../images/cessda/table-x.png) |
| [Compilable XPath](\#Compilable_XPath)                                     |                             |                             |                             |                             |
| [Predicate-less XPath](\#Predicate-less_XPath)                             |                             |                             |                             |                             |

### Mandatory Node

#### Definition

* An XML node (element or attribute) described by a predicate-less XPath expression is mandatory to be used within the metadata document. 
* This constraint includes [Not Blank Node](\#Not_Blank_Node) constraint.
* The metadata document is valid, only if the element is present at least once and the node is not blank, otherwise invalid.

#### Representation

* DDI Profile
	```xml
	<pr:Used xpath="/codeBook/docDscr/citation/titlStmt/titl" isRequired="true"/>
	```
#### Example
* Valid, because *titl* element is present and not blank
	```xml
	<docDscr>
	  <citation>
	    <titlStmt>
	      <titl>DDI2.5 XML CODEBOOK RECORD FOR STUDY NUMBER 2000</titl>
	    </titlStmt>      
	  </citation>
	</docDscr>
	```
	
* Invalid, because *titl* element is not present
	```xml
	<docDscr>
	  <citation>
	    <titlStmt>
	    </titlStmt>      
	  </citation>
	</docDscr>
	```
* Invalid, because *titl* element is blank
	```xml
	<docDscr>
	  <citation>
	    <titlStmt>
	      <titl></titl>
	      <!--or <titl>  </titl> -->
	    </titlStmt>      
	  </citation>
	</docDscr>
	```

### Recommended Node

#### Definition

* An XML node (element or attribute) described by a predicate-less XPath expression is recommended to be used within the metadata document. 
* This constraint includes [Not Blank Node](\#Not_Blank_Node) constraint.
* The metadata document is valid, only if the element is present at least once and the node is not blank, otherwise invalid.

#### Representation

* DDI Profile
	```xml
	<pr:Used xpath="/codeBook/stdyDscr/citation/rspStmt/AuthEnty" isRequired="false">
	  <pr:Instructions>
	    <r:Content>
	      <![CDATA[
	        <Constraints>
	          <RecommendedNodeConstraint/>
	        </Constraints>
	      ]]>
	    </r:Content>
	  </pr:Instructions>
	</pr:Used>
	```

#### Example
* Valid, because *AuthEnty* element is present and not blank
	```xml
	<stdyDscr>
	  <citation>
	    <rspStmt>
	      <AuthEnty>Lummis, T., University of Essex. Department of Sociology</AuthEnty>
	    </rspStmt>
	  </citation>
	</stdyDscr>
	```

* Invalid, because *AuthEnty* element is not present
	```xml
	<stdyDscr>
	  <citation>
	    <rspStmt/>
	  </citation>
	</stdyDscr>
	```
* Invalid, because *AuthEnty* element is blank
	```xml
	<stdyDscr>
	  <citation>
	    <rspStmt>
	      <AuthEnty></AuthEnty>
	      <!--or <AuthEnty>     </AuthEnty> -->
	    </rspStmt>
	  </citation>
	</stdyDscr>
	```

### Optional Node

#### Definition

* An XML node (element or attribute) described by a predicate-less XPath expression is optional to be used within the metadata document. 
* This constraint includes [Not Blank Node](\#Not_Blank_Node) constraint.
* The metadata document is valid, only if the element is present at least once and the node is not blank, otherwise invalid.

#### Representation

* DDI Profile
	```xml
	<pr:Used xpath="/codeBook/stdyDscr/citation/rspStmt/AuthEnty" isRequired="false"/>
	```

#### Example
* Valid, because *AuthEnty* element is present and not blank
	```xml
	<stdyDscr>
	  <citation>
	    <rspStmt>
	      <AuthEnty>Lummis, T., University of Essex. Department of Sociology</AuthEnty>
	    </rspStmt>
	  </citation>
	</stdyDscr>
	```

* Invalid, because *AuthEnty* element is not present
	```xml
	<stdyDscr>
	  <citation>
	    <rspStmt/>
	  </citation>
	</stdyDscr>
	```
* Invalid, because *AuthEnty* element is blank
	```xml
	<stdyDscr>
	  <citation>
	    <rspStmt>
	      <AuthEnty></AuthEnty>
	      <!--or <AuthEnty>     </AuthEnty> -->
	    </rspStmt>
	  </citation>
	</stdyDscr>
	```


### Code Value of Controlled Vocabulary 

>
> #### NOTE
>
> - Work in progress
> - Semantics and DDI representation not stable
> - For more information, please see [#9](https://bitbucket.org/cessda/cessda.cmv/issues/9)
>

#### Definition

* A field element in a metadata document uses a controlled vocabulary (CV). 
* The metadata document is valid, only if the field element is a codeValue of the given CV, otherwise invalid.

#### Representation

* DDI Profile
	```xml
	<pr:Used xpath="/codeBook/stdyDscr/stdyInfo/sumDscr/anlyUnit/concept">
	  <pr:Instructions>
	    <r:Content>
	      <![CDATA[
	        <Constraints>
	          <CodeValueOfControlledVocabularyConstraint/>
	        </Constraints>
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
                <RepositoryUri>https://vocabularies.cessda.eu/v1/vocabulary-details/AnalysisUnit/en/2.0</RepositoryUri>
                <RepositoryType>eu.cessda.cmv.core.controlledvocabulary.CessdaControlledVocabularyRepository</RepositoryType>
	          </ControlledVocabularyRepositoryConstraint>
	          <ControlledVocabularyRepositoryConstraint>
                <RepositoryUri>https://vocabularies.cessda.eu/v1/vocabulary-details/AnalysisUnit/en/1.0</RepositoryUri>
                <RepositoryType>eu.cessda.cmv.core.controlledvocabulary.CessdaControlledVocabularyRepository</RepositoryType>
	          </ControlledVocabularyRepositoryConstraint>
	        </Constraints>
	      ]]>
	    </r:Content>
	  </pr:Instructions>
	</pr:Used>
	```

#### Example
* Valid, because *Individual* is a codeValue of [AnalysisUnit:2.0](https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:2.0) and *TextUnit* is a codeValue of [AnalysisUnit:1.0](https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:1.0)
	```xml
	<stdyInfo>
	 <sumDscr>
	   <anlyUnit>
	     <concept vocabURI="https://vocabularies.cessda.eu/v1/vocabulary-details/AnalysisUnit/en/2.0">Individual</concept>
	     <concept vocabURI="https://vocabularies.cessda.eu/v1/vocabulary-details/AnalysisUnit/en/1.0">TextUnit</concept>
	   </anlyUnit>
	 </sumDscr>
	</stdyInfo>
	```
	
* Invalid, because *Person* is **not** a codeValue of [AnalysisUnit:2.0](https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:2.0)
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