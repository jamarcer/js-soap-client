Javascript SOAP Client
======================

Forked from http://javascriptsoapclient.codeplex.com/ and modified by gtathub.

Improvements
------------

* Parsing exceptions fixed
* Arrays as parameters correctly sets the length attribute in the type definiton
* Arrays are also parsed out of responses if they aren't listed in the wsdl
* Understands responses from php webservice (for example Magento)
* IE9 compatible

Tested
------

* Magento Webservice (PHP online store system)

Please leave me a note if you have tested other webservices or found bugs.
New versions available at: https://github.com/gtathub/js-soap-client

* Original work by Matteo Casati (based on v2.4 from 2007-12-21)
* Improved by Gordon Tschirner ([gtathub](https://github.com/gtathub))
* Licensed under GPLv2: https://github.com/gtathub/js-soap-client.git



Use
---

You can define response tag name using two parameters: tag name and tag sufix.

Response_name = tag_name [+ tag_sufix]


Before call soap service, you can define tag name and tag sufix. If none is defined, it works as before. But if defined, and especially the suffix, the new procedure is activated, and only one call is made to the service. 

So, you can implement response name:

+ method + "Result":
  tagName = null
  tagNameSufix = "Result"
+ "return":
  tagName = ''
  tagNameSufix = "result"
+ method + "Return":
  tagName = null
  tagNameSufix = "Return"


To call a Dolibarr soap service, as example:

// Set response tag name and sufix
SOAPClient.tagName = "myService";
SOAPClient.tagNameSufix = "Response";
// Invoke soap service
SOAPClient.invoke(url, action, soapParams, true, soapCallback);
