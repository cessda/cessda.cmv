## Constraint Catalog

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

* A field element in a metadata document uses a controlled vocabulary (CV). 
* The metadata document is valid, only if the field element value equals one of the defined values of the given CV, otherwise invalid.

```xml
<!-- Valid metadata document snippet, because `Individual` is item of `AnalysisUnit:2.0` CV -->
<stdyInfo>
 <sumDscr>
  <anlyUnit xml:lang="fi">Henkil
   <concept vocab="DDI Analysis Unit" 
            vocabURI="https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:2.0">Individual</concept>
  </anlyUnit>
 </sumDscr>
</stdyInfo>
```

```xml
<!-- Invalid metadata document snippet, because `Person` is item of `AnalysisUnit:2.0` CV -->
<stdyInfo>
 <sumDscr>
  <anlyUnit xml:lang="fi">Henkil
   <concept vocab="DDI Analysis Unit" 
            vocabURI="https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:2.0">Person</concept>
  </anlyUnit>
 </sumDscr>
</stdyInfo>
```

* Test lore ipsum
	```xml
	<!-- Invalid metadata document snippet, because `Person` is item of `AnalysisUnit:2.0` CV -->
	<stdyInfo>
	 <sumDscr>
	  <anlyUnit xml:lang="fi">Henkil
	   <concept vocab="DDI Analysis Unit" 
	            vocabURI="https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:2.0">Person</concept>
	  </anlyUnit>
	 </sumDscr>
	</stdyInfo>
	```
