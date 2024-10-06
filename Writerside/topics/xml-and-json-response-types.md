# XML and JSON response types

## Introduction

When it comes to displaying output, an API developer should always allow the client to request the preferred content
type, such as JSON or XML. Clients can do this by supplying an additional header called 'Accept' in the request header.
You learned about this in the
reading, [HTTP methods, status codes and response types](https://www.coursera.org/learn/apis/supplement/epTtA/http-methods-status-codes-and-response-types "Link to HTTP methods, status codes and response types reading")

. In this way, the client has full flexibility to use the content in the way they want to. In this reading, you’ll learn
more about the two data formats that you will encounter the most in requests from clients, JSON and XML.

## Request headers

Client applications need to send Accept request headers with every HTTP request to receive the output in JSON or XML.
For example:

| **Response type** | **Request header**                                        |
|-------------------|-----------------------------------------------------------|
| JSON              | Accept: application/json                                  |
| XML               | Accept: application/xml<br></br><br></br>Accept: text/xml |

The client can send an Accept header in an HTTP GET request, and depending on the request header, the same data will be
displayed differently in JSON and XML. Below is a screenshot of an API request for a JSON response.

![An API request for a JSON response](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/RzgYjx3eT6CoGJHlPNXs2A_108a1d666e184c9db155faa674102ee1_XML-and-JSON-response-types-1.png?expiry=1727827200000&hmac=zp04wPSw1xtFr6DlSh3vPvp3OXhpK85rHkZgb6x77Ds)

And here is the same API request but for an XML response.

![An API request for an XML response](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/MioGJocwTi-YD2rF5rQTng_d978a48fe13846f9999cb71699155ce1_XML-and-JSON-response-types-2.png?expiry=1727827200000&hmac=6tFDXrAg-DlNlSzoOPPiIOwP25tf8UBNdoi5pMcpMK8)

## Data conversion

In this course, you will build APIs using Django and Django REST Framework, also called DRF. DRF has built-in renderers
that can convert your data to JSON and represent it in an interactive, browsable API viewer. There are also third-party
renderer classes that can convert these data to XML or YAML. You will learn about these features and write actual code
later in this course.

## JSON versus XML

JSON gained popularity because it’s straightforward and lightweight. And creating JSON data or parsing it is easier than
XML. However, XML has its own advantages too. XML is more readable and supports data attributes that are not possible in
JSON. And you can represent complex data in XML and still keep it readable. JSON is very popular among JavaScript
developers because they can instantly read and write JSON data just like a regular object.

The table below compares some features of both formats.

| **JSON**                                                                                                                                                    | **XML**                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| JSON or **JavaScript Object Notation** is a lightweight and dependency-free data format.                                                                    | XML or **Extensible Markup Language** is a powerful, tag-based data format. It is similar to HTML. XML data can be fairly complex.                                                                                                                                                                                                                                                                                                                                    |
| The size of JSON data is smaller than XML. So, it takes less bandwidth.                                                                                     | XML data is lengthier than JSON and takes up more bandwidth.                                                                                                                                                                                                                                                                                                                                                                                                          |
| JSON data is like keys and values.<br></br><br></br>{<br></br><br></br>"author": "Jack London",<br></br><br></br>"title": "The Sea Wolf"<br></br><br></br>} | XML is completely tag-based, it does not have key-value pairs like JSON.<br></br><br></br><?xml version="1.0" encoding="UTF-8"?><br></br><br></br><root><br></br><br></br>   <author>Jack London</author><br></br><br></br>   <title>The Sea Wolf</title><br></br><br></br></root>                                                                                                                                                                                    |
| Representing array elements is simpler in JSON. Here’s an example:<br></br><br></br>{<br></br><br></br>"items": [1,2,3,4,5]<br></br><br></br>}              | You can still display array elements in XML but it’s very verbose.<br></br><br></br><?xml version="1.0"<br></br><br></br>encoding="UTF-8"?><br></br><br></br><root><br></br><br></br>   <items><br></br><br></br>   <element>1</element><br></br><br></br>   <element>2</element><br></br><br></br>   <element>3</element><br></br><br></br>   <element>4</element><br></br><br></br>      <element>5</element><br></br><br></br>   </items><br></br><br></br></root> |
| Generating and parsing JSON data is faster than XML and this conversion process requires less memory and computing power.                                   | Generating and parsing XML is a complex process, and it usually takes more processing power and memory than processing JSON.                                                                                                                                                                                                                                                                                                                                          |
| There is no way to include comments in JSON data.                                                                                                           | XML data can include comments.                                                                                                                                                                                                                                                                                                                                                                                                                                        |

## Conclusion

It is clear that JSON and XML both have benefits and limitations. Later in this course, you will learn how to display
API output in both formats, but you will mostly use JSON in this course.