---
UID: NF:printerextension.IPrinterPropertyBag.GetBytes
title: IPrinterPropertyBag::GetBytes method
author: windows-driver-content
description: Reads a byte array property.
old-location: print\iprinterpropertybag_getbytes.htm
old-project: print
ms.assetid: F75E182D-90FA-4597-95E0-60A6326CF68D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetBytes method [Print Devices], GetBytes method [Print Devices], IPrinterPropertyBag interface, GetBytes,IPrinterPropertyBag.GetBytes, IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], GetBytes method, IPrinterPropertyBag::GetBytes, print.iprinterpropertybag_getbytes, printerextension/IPrinterPropertyBag::GetBytes
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
-	IPrinterPropertyBag.GetBytes
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterPropertyBag::GetBytes method


## -description


Reads a byte array property.

The <a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a> interface is used by all the printer property bags, including driver property bag, user property bag, queue property bag, and DEVMODE property bag.


## -syntax


````
HRESULT GetBytes(
  [in]  BSTR  bstrName,
  [out] DWORD *pcbValue,
  [out] BYTE  *rgbValue
);
````


## -parameters




### -param bstrName [in]

The property to read.


### -param pcbValue [out]

The number of bytes read.


### -param ppValue






#### - rgbValue [out]

The returned array. This array must be freed by using CoTaskFree.


## -returns



This method returns an <b>HRESULT</b> value.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterPropertyBag::GetBytes method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

