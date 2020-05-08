## Glossary

#### Profile
* A profile holds a set of constraints. 

#### Constraint
* A constraint is a requirement a metadata document satisfies or violates. 
* A constraint is expressed as XPath location path together with needed properties.
* Within the context of a metadata document, a constraint builds concrete validators.      

#### Validation Gate
* A validation gate holds a set of constraint types against which the validation is executed. 
* A constraint is ignored if its constraint type is not part of the validation gate. 
* CMV defines four, hierarchically structured validation gates: Basic, Standard, Extended and Strict.   

#### Document
* A document is a resource containing social science metadata expressed as DDI Lifecycle oder DDI Codebook.
* A document is the subject of validation.