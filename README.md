
#Build REST API on top of SOAP based Weather Web Service

#Motivation :

a) As part of Digital Transformation Journey, an existing set of SOAP based services that business would like to expose through APIs in order to foster growth within the mobile and device market. 
b) The  A business team knows that an increased mobile and device application presence will enhance their brand image and increase customer satisfaction.
c) The  A business team have had requirements from their mobile application developers to expose their existing web services as JSON REST APIs. 
d) JSON Payloads are smaller than the same data in SOAP format which reduces the amount of bandwidth required for mobile applications. JSON is also an easier data format to work with in JavaScript which is a popular programming language for mobile development.
e) After considering building their own API management solution, the  Architect and CTO  team has decided to implement an iPaaS solution using Mulesoft as a strategic platform as it will allow them to enter the market quickly at a reduced cost.

#RESTful design principles : 

a) API Version : The API Version will be managed on the service level (fine-grained). The service version will be defined as a parameter version of the service’s RESTful URI, and the value will be the version of the service
b) HTTP Status Usage : A successful execution of the  API service request should return HTTP status of 200 OK with the corresponding JSON payload. Business exceptions (those determined by the back-end service Providers) will be indicated through the status block in the JSON payload.
The following HTTP status codes will be returned by  API in case an error condition had been detected. Additional codes, when meaningful, can be added to the below list over time
 #400 – Bad Request
 #401 – Unauthorized
 #403 - Forbidden
 #404 – Not Found
 #405 - Method Not Allowed

c) API Model and JSON Structure : REST API definition begins by modelling a set of resources to expose API fo partner or external World. Used RESTful API Modeling Language (RAML) to define API spec and JSON schema to validate the API
request/Response Model

d) API Specification: A single monolithic word document covering all your APIs which replaced separate word documents and difficult to maintain and do not provide an easy way to to
link User Stories to API Specifications. This is a holistic explanation? of the API for Weather Information that can easily accessable by Partner or 3rd Party who wants to consume
this API

#RAML File :
#Location : /rest-api-howto_1.0.0/src/main/api/api.raml

#Mule Flow
a) The API designed using RESTful design principles.(RAML and JSON Schema)
b) The API must use DataWeave code to transform the message. (REST to SOAP transform)
c) The API must provide suitable error handling (Customized Error handle using Ref Exception Strategy)

#Build Process:
The application is created using Maven build (rest-api-howto_1.0.0\mule-project.xml)
For On Premise deployment , follow below steps
Run As ---> 1. Mule Application (refer below screenshot)

#Unit Testing :
Developed MUnit ( application testing framework ) test cases which allows to build automated tests for your Mule integrations and API's for Weather info API. Defined here two Munit test cases for Get Weather info and GetCitiesByCountry API
I have used Assert? ?Payload?,to define Expected? ?Value? and in this case, it will be payload. Also, provide Test Failure Message

