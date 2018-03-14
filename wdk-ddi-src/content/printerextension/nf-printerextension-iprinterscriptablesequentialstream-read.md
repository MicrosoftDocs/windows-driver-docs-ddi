---
UID: NF:printerextension.IPrinterScriptableSequentialStream.Read
title: IPrinterScriptableSequentialStream::Read method
author: windows-driver-content
description: The Read method reads bytes from the stream and returns them as a JavaScript array.
old-location: print\iprinterscriptablesequentialstream_read.htm
old-project: print
ms.assetid: 1E13DF22-9C45-4475-8912-CC836EFC0A22
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterScriptableSequentialStream, IPrinterScriptableSequentialStream interface [Print Devices], Read method, IPrinterScriptableSequentialStream::Read, Read method [Print Devices], Read method [Print Devices], IPrinterScriptableSequentialStream interface, Read,IPrinterScriptableSequentialStream.Read, print.iprinterscriptablesequentialstream_read, printerextension/IPrinterScriptableSequentialStream::Read
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
-	printerextension.h
api_name:
-	IPrinterScriptableSequentialStream.Read
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterScriptableSequentialStream::Read method


## -description


The Read method reads bytes from the stream and returns them as a JavaScript array.


## -syntax


````
HRESULT Read(
  [in]          LONG      cbRead,
  [out, retval] IDispatch **ppdispArray
);
````


## -parameters




### -param cbRead [in]

The number of bytes to read.


### -param ppArray






#### - ppdispArray [out, retval]

The returned array.


## -returns



This method returns an <b>HRESULT</b> value.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterscriptablesequentialstream.md">IPrinterScriptableSequentialStream</a>



 

 


