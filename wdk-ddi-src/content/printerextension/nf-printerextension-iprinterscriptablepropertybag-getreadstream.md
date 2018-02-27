---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetReadStream
title: IPrinterScriptablePropertyBag::GetReadStream method
author: windows-driver-content
description: Gets a read stream and uses it to read from a property.
old-location: print\iprinterscriptablepropertybag_getreadstream.htm
old-project: print
ms.assetid: 493E6C55-DC3B-4160-9642-BDABADD575B8
ms.author: windowsdriverdev
ms.date: 2/23/2018
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

<a href="..\printerextension\nn-printerextension-iprinterscriptablestream.md">IPrinterScriptableStream</a>



<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptablePropertyBag::GetReadStream method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

