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
