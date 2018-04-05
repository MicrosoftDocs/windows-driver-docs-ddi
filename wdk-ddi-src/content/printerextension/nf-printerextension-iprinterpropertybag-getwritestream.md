---
UID: NF:printerextension.IPrinterPropertyBag.GetWriteStream
title: IPrinterPropertyBag::GetWriteStream method
author: windows-driver-content
description: Gets a stream in order to write a stream property.
old-location: print\iprinterpropertybag_getwritestream.htm
old-project: print
ms.assetid: 47F535C0-57C7-407B-B47B-188EB6434F2E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetWriteStream method [Print Devices], GetWriteStream method [Print Devices], IPrinterPropertyBag interface, GetWriteStream,IPrinterPropertyBag.GetWriteStream, IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], GetWriteStream method, IPrinterPropertyBag::GetWriteStream, print.iprinterpropertybag_getwritestream, printerextension/IPrinterPropertyBag::GetWriteStream
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
-	IPrinterPropertyBag.GetWriteStream
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterPropertyBag::GetWriteStream method


## -description


Gets a stream in order to write a stream property.


## -parameters




### -param bstrName [in]

The property to write.


### -param ppValue






#### - ppValueStream [out, retval]

The retrieved stream.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



This method does not work with non-stream properties.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439547">IPrinterPropertyBag</a>
 

 

