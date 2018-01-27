---
UID: NF:printerextension.IPrintSchemaFeature.GetOption
title: IPrintSchemaFeature::GetOption method
author: windows-driver-content
description: Gets the option with the given name.
old-location: print\iprintschemafeature_getoption.htm
old-project: print
ms.assetid: C9C4E085-1F2A-4610-AF2A-8F87E5CE7BCA
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintSchemaFeature, print.iprintschemafeature_getoption, IPrintSchemaFeature::GetOption, IPrintSchemaFeature interface [Print Devices], GetOption method, GetOption method [Print Devices], IPrintSchemaFeature interface, GetOption, GetOption method [Print Devices], printerextension/IPrintSchemaFeature::GetOption
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
-	IPrintSchemaFeature.GetOption
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaFeature::GetOption method


## -description


Gets the option with the given name.


## -syntax


````
HRESULT GetOption(
  [in]          BSTR               bstrName,
  [in]          BSTR               bstrNamespaceUri = PRINTSCHEMA_KEYWORDS_NAMESPACE_URI,
  [out, retval] IPrintSchemaOption **ppOption
);
````


## -parameters




### -param bstrName [in]

The name of the option.


### -param bstrNamespaceUri [in]

The namespace URI of the option.


### -param ppOption [out, retval]

The returned option.


## -returns


This method returns an <b>HRESULT</b> value, if the call was successful. Otherwise it returns the appropriate error code.



## -remarks


When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a> object and query it via <a href="https://msdn.microsoft.com/053BFE59-FDC6-42F3-BE14-CE63D5637D62">IPrintSchemaCapabilities::GetFeatureByKeyName</a> or via <a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>.



## -see-also

<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>

<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>

<a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a>

<a href="..\printerextension\nn-printerextension-iprintschemafeature.md">IPrintSchemaFeature</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaFeature::GetOption method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

