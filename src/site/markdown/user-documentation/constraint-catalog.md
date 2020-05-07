## Constraint Catalog

|                                                                    | Basic | Standard | Extended | Strict |
|--------------------------------------------------------------------|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|
| [Mandatory Node](\#Mandatory_Node)                                 | ![X](../images/table-x.png) | ![X](../images/table-x.png) | ![X](../images/table-x.png) | ![X](../images/table-x.png) |
| [Recommended Node](\#Recommended_Node)                             |                             | ![X](../images/table-x.png) | ![X](../images/table-x.png) | ![X](../images/table-x.png) |
| [Value of Controlled Vocabulary](\#Value_of_Controlled_Vocabulary) |                             | ![X](../images/table-x.png) |                             | ![X](../images/table-x.png) |
| [Compilable XPath](\#Compilable_XPath)                             |                             |                             |                             | ![X](../images/table-x.png) |
| [Predicate-less XPath](\#Predicate-less_XPath)                     |                             |                             |                             | ![X](../images/table-x.png) |

### Mandatory Node

An XML node (element or attribute) described by a predicate-less XPath expression is mandatory to be used within the metadata document. 
The node MUST be at least once in the metadata document. This constraint is used for metadata document validation.

```
# ddi profile mapping
<pr:Used xpath="/codeBook/docDscr/citation/holdings/@URI" isRequired="true"/>
```

```
# validated metadata document
... nn
```

```
# in-validated metadata document
... nn
```


### Recommended Node

An XML node (element or attribute) described by a predicate-less XPath expression is recommended to be used within the metadata document.
The node MAY be in the metadata document. This constraint is used for metadata document validation.

```
# ddi profile mapping
<pr:Used xpath="/codeBook/docDscr/citation/holdings/@URI" isRequired="false"/>
```

```
# validated metadata document
... nn
```

```
# in-validated metadata document
... nn
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

### Value of Controlled Vocabulary 

> NOTE: Work in progress, see [#9](https://bitbucket.org/cessda/cessda.cmv/issues/9)

#### Definition

* A field element in a metadata document uses a controlled vocabulary (CV). 
* The metadata document is valid, only if the field element value equals one of the defined values of the given CV, otherwise invalid.

#### Example
* Valid, because *Individual* is item of *AnalysisUnit:2.0* CV
	```xml
	<stdyInfo>
	 <sumDscr>
	  <anlyUnit xml:lang="fi">Henkil
	   <concept vocab="DDI Analysis Unit" 
	            vocabURI="https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:2.0">Individual</concept>
	  </anlyUnit>
	 </sumDscr>
	</stdyInfo>
	```
	
* Invalid, because *Person* is **not** item of *AnalysisUnit:2.0* CV
	```xml
	<stdyInfo>
	 <sumDscr>
	  <anlyUnit xml:lang="fi">Henkil
	   <concept vocab="DDI Analysis Unit" 
	            vocabURI="https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:2.0">Person</concept>
	  </anlyUnit>
	 </sumDscr>
	</stdyInfo>
	```
	
#### Profile Mapping

```xml
<pr:Used ... n.n./>

```
