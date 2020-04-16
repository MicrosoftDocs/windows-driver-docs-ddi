---
UID: NF:printerextension.IPrinterPropertyBag.GetWriteStream
title: IPrinterPropertyBag::GetWriteStream (printerextension.h)
description: Gets a stream in order to write a stream property.
old-location: print\iprinterpropertybag_getwritestream.htm
tech.root: print
ms.assetid: 47F535C0-57C7-407B-B47B-188EB6434F2E
ms.date: 04/20/2018
keywords: ["IPrinterPropertyBag::GetWriteStream"]
ms.keywords: GetWriteStream, GetWriteStream method [Print Devices], GetWriteStream method [Print Devices],IPrinterPropertyBag interface, IPrinterPropertyBag interface [Print Devices],GetWriteStream method, IPrinterPropertyBag.GetWriteStream, IPrinterPropertyBag::GetWriteStream, print.iprinterpropertybag_getwritestream, printerextension/IPrinterPropertyBag::GetWriteStream
f1_keywords:
 - "printerextension/IPrinterPropertyBag.GetWriteStream"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrinterPropertyBag.GetWriteStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterPropertyBag::GetWriteStream


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterpropertybag">IPrinterPropertyBag</a>
 

 

