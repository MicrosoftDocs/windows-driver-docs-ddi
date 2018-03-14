---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetWriteStream
title: IPrinterScriptablePropertyBag::GetWriteStream method
author: windows-driver-content
description: Gets a stream and uses it to write to a stream property.
old-location: print\iprinterscriptablepropertybag_getwritestream.htm
old-project: print
ms.assetid: EFF55B5C-55E2-4E03-9D96-FDB1BC550A53
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetWriteStream method [Print Devices], GetWriteStream method [Print Devices], IPrinterScriptablePropertyBag interface, GetWriteStream,IPrinterScriptablePropertyBag.GetWriteStream, IPrinterScriptablePropertyBag, IPrinterScriptablePropertyBag interface [Print Devices], GetWriteStream method, IPrinterScriptablePropertyBag::GetWriteStream, print.iprinterscriptablepropertybag_getwritestream, printerextension/IPrinterScriptablePropertyBag::GetWriteStream
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
-	IPrinterScriptablePropertyBag.GetWriteStream
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterScriptablePropertyBag::GetWriteStream method


## -description


Gets a stream and uses it  to write to a stream property.


## -syntax


````
HRESULT GetWriteStream(
  [in]          BSTR                      bstrName,
  [out, retval] IPrinterScriptableStream **ppStream
);
````


## -parameters




### -param bstrName [in]

The property to write.


### -param ppStream [out, retval]

The retrieved stream.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



<b>GetWriteStream</b> does not work with non-stream properties.

A call to <b>GetWriteStream</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>



<a href="..\printerextension\nn-printerextension-iprinterscriptablestream.md">IPrinterScriptableStream</a>



 

 


