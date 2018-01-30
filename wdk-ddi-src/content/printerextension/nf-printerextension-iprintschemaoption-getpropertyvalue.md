---
UID: NF:printerextension.IPrintSchemaOption.GetPropertyValue
title: IPrintSchemaOption::GetPropertyValue method
author: windows-driver-content
description: Gets the XML node for the &#0034;value&#0034; child element of a &#0034;Property&#0034; or a &#0034;ScoredProperty&#0034; element with the given name.
old-location: print\iprintschemaoption_getpropertyvalue.htm
old-project: print
ms.assetid: 6CD5202C-7852-46AA-90ED-3477E6654188
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintSchemaOption, GetPropertyValue method [Print Devices], IPrintSchemaOption interface, IPrintSchemaOption interface [Print Devices], GetPropertyValue method, IPrintSchemaOption::GetPropertyValue, GetPropertyValue method [Print Devices], GetPropertyValue, printerextension/IPrintSchemaOption::GetPropertyValue, print.iprintschemaoption_getpropertyvalue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrintSchemaOption.GetPropertyValue
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaOption::GetPropertyValue method


## -description


Gets the XML node for the "value" child element of a "Property"  or a "ScoredProperty" element with the given name.


## -syntax


````
HRESULT GetPropertyValue(
  [in]          BSTR        bstrName,
  [in]          BSTR        bstrNamespaceUri,
  [out, retval] IXMLDOMNode **ppXmlNodeValue
);
````


## -parameters




### -param bstrName [in]

The base value of the "name" attribute of the "Property" or the "ScoredProperty" element.


### -param bstrNamespaceUri [in]

The namespace URI value of the "name" attribute of the "Property" or the "ScoredProperty" element.


### -param ppXmlValueNode





#### - ppXmlNodeValue [out, retval]

The XML node for the "value" child element.


## -returns


Returns an <b>HRESULT</b> value. If the method call was not successful,  it returns the appropriate <b>HRESULT</b> error code.



## -remarks


When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a> object and query it via <a href="https://msdn.microsoft.com/053BFE59-FDC6-42F3-BE14-CE63D5637D62">IPrintSchemaCapabilities::GetFeatureByKeyName</a> or via <a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>.



## -see-also

<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>

<a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a>

<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaOption::GetPropertyValue method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

