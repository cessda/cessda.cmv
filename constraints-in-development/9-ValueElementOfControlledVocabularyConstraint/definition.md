## Constraint definition

* A field in a metadata document uses a controlled vocabulary (CV). Valid entries in the metadata document are only the defined values in the CV. 
* The metadata document is valid, only if the field element equals a defined value, otherwise invalid.


### Usage

* Valid metadata document snippet, because `Individual` is item of `AnalysisUnit:2.0` CV.
	```
	<stdyInfo>
		<sumDscr>
			<anlyUnit xml:lang="fi">Henkilö
				<concept vocab="DDI Analysis Unit" 
						vocabURI="https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:2.0">Individual</concept>
			</anlyUnit>
		</sumDscr>
	</stdyInfo>
	```
	
* Invalid metadata document snippet, because `Person` is not item of `AnalysisUnit:2.0` CV.
	```
	<stdyInfo>
		<sumDscr>
			<anlyUnit xml:lang="fi">Henkilö
				<concept vocab="DDI Analysis Unit" 
						vocabURI="https://vocabularies.cessda.eu/urn/urn:ddi:int.ddi.cv:AnalysisUnit:2.0">Person</concept>
			</anlyUnit>
		</sumDscr>
	</stdyInfo>
	```
