# Glossary

## Document

* A document is a file containing social science metadata expressed in
  [DDI Lifecycle](https://ddialliance.org/explore-documentation) or
  [DDI Codebook](https://ddialliance.org/explore-documentation).
* A document is the subject of validation.

## Profile

* A profile holds a set of [constraints](\#Constraint).
* A profile is itself a document.

## Constraint

* A constraint is a requirement a [document](\#Document) satisfies or violates.
* A constraint is expressed as XPath location path together with needed
  properties.
* Within the context of a [document](\#Document),
  a [constraint](\#Constraint) builds [validators](\#Validator).

## Validation Gate

* A validation gate holds a set of constraint types and serves as validation
  executor.
* A [constraint](\#Constraint) is ignored if its constraint type is not part
  of the validation gate.
* CMV defines four, hierarchically structured validation gates:
  Basic, Standard, Extended and Strict.

## Validator

* A validator is called by a validation gate to answer the question if the
  underlying constraint is satisfied or violated.
