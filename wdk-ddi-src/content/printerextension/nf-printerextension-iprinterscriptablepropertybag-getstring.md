---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetString
title: IPrinterScriptablePropertyBag::GetString method
author: windows-driver-content
description: Gets a string property.
old-location: print\iprinterscriptablepropertybag_getstring.htm
old-project: print
ms.assetid: FA14B81D-0B51-4C07-96BC-38CAABED735A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetString method [Print Devices], GetString method [Print Devices], IPrinterScriptablePropertyBag interface, GetString,IPrinterScriptablePropertyBag.GetString, IPrinterScriptablePropertyBag, IPrinterScriptablePropertyBag interface [Print Devices], GetString method, IPrinterScriptablePropertyBag::GetString, print.iprinterscriptablepropertybag_getstring, printerextension/IPrinterScriptablePropertyBag::GetString
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



 

 


