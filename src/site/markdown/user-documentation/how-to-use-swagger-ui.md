# How to use Swagger UI

## Step 1

* Click on [REST API](../api/swagger)

![Step 1](../images/uml/swagger-tutorial-01.png)

## Step 2

* Click on endpoint `POST /api/V0/Validation` (green box)
* Click on the button `Try it out`

![Step 2](../images/user-documentation/swagger-tutorial-02.png)

## Step 3

* Enter an url for the document, e.g.
  https://bitbucket.org/cessda/cessda.cmv.core/raw/8d0ea9d6a731fa06bde8c8f2b231c2e974aa7130/src/main/resources/demo-documents/ddi-v25/ukds-2000.xml
* Enter an url for the profile, e.g.
  https://bitbucket.org/cessda/cessda.cmv.core/raw/8d0ea9d6a731fa06bde8c8f2b231c2e974aa7130/src/main/resources/demo-documents/ddi-v25/cdc25_profile.xml
* Select a validation gate
* Click on button `Execute`

![Step 3](../images/user-documentation/swagger-tutorial-03.png)

## Step 4

* Scroll down and see constraint violation messages in the response body
* If this list is empty, the document is valid

![Step 4](../images/user-documentation/swagger-tutorial-04.png)
