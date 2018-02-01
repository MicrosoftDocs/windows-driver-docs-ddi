---
UID: NF:printerextension.IPrintSchemaCapabilities.GetOptions
title: IPrintSchemaCapabilities::GetOptions method
author: windows-driver-content
description: Gets all the options of a feature.
old-location: print\iprintschemacapabilities_getoptions.htm
old-project: print
ms.assetid: 0A8271AC-389F-4E04-8691-CBED1391B453
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.iprintschemacapabilities_getoptions, printerextension/IPrintSchemaCapabilities::GetOptions, GetOptions, IPrintSchemaCapabilities, GetOptions method [Print Devices], IPrintSchemaCapabilities::GetOptions, IPrintSchemaCapabilities interface [Print Devices], GetOptions method, GetOptions method [Print Devices], IPrintSchemaCapabilities interface
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
-	IPrintSchemaCapabilities.GetOptions
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaCapabilities::GetOptions method


## -description


Gets all the options of a feature.


## -syntax


````
HRESULT GetOptions(
  [in]          IPrintSchemaFeature          *pFeature,
  [out, retval] IPrintSchemaOptionCollection **ppOptions
);
````


## -parameters




### -param pFeature [in]

The specified feature.


### -param ppOptionCollection





#### - ppOptions [out, retval]

The returned options.


## -returns


This method returns an <b>HRESULT</b> value.



## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>

<a href="..\printerextension\nn-printerextension-iprintschemaoptioncollection.md">IPrintSchemaOptionCollection</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaCapabilities::GetOptions method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

