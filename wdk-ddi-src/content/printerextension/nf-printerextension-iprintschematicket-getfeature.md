---
UID: NF:printerextension.IPrintSchemaTicket.GetFeature
title: IPrintSchemaTicket::GetFeature method
author: windows-driver-content
description: Gets a named feature from the PrintTicket, by name and full namespace URI.
old-location: print\iprintschematicket_getfeature.htm
old-project: print
ms.assetid: 2E65BDF2-9539-402B-AF19-8CBC84F9C018
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetFeature method [Print Devices], GetFeature method [Print Devices], IPrintSchemaTicket interface, GetFeature,IPrintSchemaTicket.GetFeature, IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices], GetFeature method, IPrintSchemaTicket::GetFeature, print.iprintschematicket_getfeature, printerextension/IPrintSchemaTicket::GetFeature
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaTicket.GetFeature
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaTicket::GetFeature method


## -description


Gets a named feature from the PrintTicket, by name and full namespace URI.


## -syntax


````
HRESULT GetFeature(
  [in]          BSTR                bstrName,
  [in]          BSTR                bstrNamespaceUri,
  [out, retval] IPrintSchemaFeature **ppFeature
);
````


## -parameters




### -param bstrName [in]

The base name of the <b>name</b> attribute value of the feature element.
For example, for the Print Schema feature &lt;psf:Feature name="psk:JobOutputBin"&gt;, the base name of the feature is "JobOutputBin".


### -param bstrNamespaceUri [in]

The namespace URI of the <b>name</b> attribute value of the feature element.
For example, the namespace URI of the public Print Schema feature "JobOutputBin" is "http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords".
If the feature is not defined in the public Print Schema, then this should be the URI of the private namespace defining the feature.


### -param ppFeature [out, retval]

The returned feature.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a> object and query it via <a href="https://msdn.microsoft.com/053BFE59-FDC6-42F3-BE14-CE63D5637D62">IPrintSchemaCapabilities::GetFeatureByKeyName</a> or via <a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>.




## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>



<a href="..\printerextension\nn-printerextension-iprintschemafeature.md">IPrintSchemaFeature</a>



<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>



<a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>



<a href="https://msdn.microsoft.com/053BFE59-FDC6-42F3-BE14-CE63D5637D62">IPrintSchemaCapabilities::GetFeatureByKeyName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaTicket::GetFeature method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

