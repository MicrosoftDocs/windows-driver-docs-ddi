---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetReadStream
title: IPrinterScriptablePropertyBag::GetReadStream method
author: windows-driver-content
description: Gets a read stream and uses it to read from a property.
old-location: print\iprinterscriptablepropertybag_getreadstream.htm
old-project: print
ms.assetid: 493E6C55-DC3B-4160-9642-BDABADD575B8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetReadStream method [Print Devices], GetReadStream method [Print Devices], IPrinterScriptablePropertyBag interface, GetReadStream,IPrinterScriptablePropertyBag.GetReadStream, IPrinterScriptablePropertyBag, IPrinterScriptablePropertyBag interface [Print Devices], GetReadStream method, IPrinterScriptablePropertyBag::GetReadStream, print.iprinterscriptablepropertybag_getreadstream, printerextension/IPrinterScriptablePropertyBag::GetReadStream
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
-	IPrinterScriptablePropertyBag.GetReadStream
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterScriptablePropertyBag::GetReadStream method


## -description


Gets a read stream and uses it to read  from a property.


## -syntax


````
HRESULT GetReadStream(
  [in]          BSTR                     bstrName,
  [out, retval] IPrinterScriptableStream **ppStream
);
````


## -parameters




### -param bstrName [in]

The property to read.


### -param ppStream [out, retval]

        The returned stream.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



<b>GetReadStream</b> does not work with non-stream properties.

A call to <b>GetReadStream</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>



<a href="..\printerextension\nn-printerextension-iprinterscriptablestream.md">IPrinterScriptableStream</a>



 

 


