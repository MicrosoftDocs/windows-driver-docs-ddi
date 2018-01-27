---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetString
title: IPrinterScriptablePropertyBag::GetString method
author: windows-driver-content
description: Gets a string property.
old-location: print\iprinterscriptablepropertybag_getstring.htm
old-project: print
ms.assetid: FA14B81D-0B51-4C07-96BC-38CAABED735A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrinterScriptablePropertyBag interface [Print Devices], GetString method, IPrinterScriptablePropertyBag::GetString, GetString, printerextension/IPrinterScriptablePropertyBag::GetString, print.iprinterscriptablepropertybag_getstring, GetString method [Print Devices], IPrinterScriptablePropertyBag interface, IPrinterScriptablePropertyBag, GetString method [Print Devices]
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
-	IPrinterScriptablePropertyBag.GetString
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterScriptablePropertyBag::GetString method


## -description


Gets a string property.


## -syntax


````
HRESULT GetString(
  [in]          BSTR bstrName,
  [out, retval] BSTR *pbstrValue
);
````


## -parameters




### -param bstrName [in]

The property to read.


### -param pbstrValue [out, retval]

        The value read.


## -returns


This method returns an <b>HRESULT</b> value.



## -remarks


A call to <b>GetString</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.



## -see-also

<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptablePropertyBag::GetString method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

