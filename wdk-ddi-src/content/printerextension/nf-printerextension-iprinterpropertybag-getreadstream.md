---
UID: NF:printerextension.IPrinterPropertyBag.GetReadStream
title: IPrinterPropertyBag::GetReadStream method
author: windows-driver-content
description: Gets a stream in order to read from a stream property.
old-location: print\iprinterpropertybag_getreadstream.htm
old-project: print
ms.assetid: BDA58F6A-A245-4616-866C-6D1734EFB469
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetReadStream method [Print Devices], GetReadStream method [Print Devices], IPrinterPropertyBag interface, GetReadStream,IPrinterPropertyBag.GetReadStream, IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], GetReadStream method, IPrinterPropertyBag::GetReadStream, print.iprinterpropertybag_getreadstream, printerextension/IPrinterPropertyBag::GetReadStream
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
-	IPrinterPropertyBag.GetReadStream
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterPropertyBag::GetReadStream method


## -description


Gets a stream in order to read from a stream property.


## -parameters




### -param bstrName [in]

The property to read.


### -param ppValue






#### - ppValueStream [out]

The returned stream.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



This method does not work with non-stream properties.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439547">IPrinterPropertyBag</a>
 

 

