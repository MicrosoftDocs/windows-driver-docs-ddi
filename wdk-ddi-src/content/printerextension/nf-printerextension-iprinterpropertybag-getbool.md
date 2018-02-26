---
UID: NF:printerextension.IPrinterPropertyBag.GetBool
title: IPrinterPropertyBag::GetBool method
author: windows-driver-content
description: Reads a specified boolean property.
old-location: print\iprinterpropertybag_getbool.htm
old-project: print
ms.assetid: 0C7ED962-F4E2-4F2F-B2CF-96DCFC71C4DD
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, B, G, GetBool method [Print Devices], GetBool method [Print Devices], IPrinterPropertyBag interface, GetBool,IPrinterPropertyBag.GetBool, I, IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], GetBool method, IPrinterPropertyBag::GetBool, P, a, e, g, i, l, n, o, p, print.iprinterpropertybag_getbool, printerextension/IPrinterPropertyBag::GetBool, r, t, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: Printerextension.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
-	IPrinterPropertyBag.GetBool
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterPropertyBag::GetBool method


## -description


Reads a specified boolean property.


## -syntax


````
HRESULT GetBool(
  [in]          BSTR bstrName,
  [out, retval] BOOL *pbValue
);
````


## -parameters




### -param bstrName [in]

The name of the property.


### -param pbValue [out, retval]

The returned property value.


## -returns



This method returns an <b>HRESULT</b> value.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterPropertyBag::GetBool method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

