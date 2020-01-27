---
UID: NN:printerextension.IPrinterQueue
title: IPrinterQueue (printerextension.h)
description: Represents a single printer queue.
old-location: print\iprinterqueue_interface.htm
tech.root: print
ms.assetid: 2DB57234-E783-4C6B-A743-F1E9F7D34D97
ms.date: 04/20/2018
ms.keywords: IPrinterQueue, IPrinterQueue interface [Print Devices], IPrinterQueue interface [Print Devices],described, print.iprinterqueue_interface, printerextension/IPrinterQueue
f1_keywords:
 - "printerextension/IPrinterQueue"
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrinterQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueue interface


## -description


Represents a single printer queue.


## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IPrinterQueue</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrinterQueue</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -remarks



Any event sink that implements <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterqueueevent">IPrinterQueueEvent</a> is connected to the associated event source, <b>IPrinterQueue</b>, via the <a href="https://docs.microsoft.com/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint">IConnectionPoint</a> mechanism. You must retrieve a pointer to the <b>IConnectionPoint</b> interface by invoking <b>QueryInterface</b> on the <b>IPrinterQueue</b> object.

<div class="alert"><b>Note</b>  It is mandatory to implement <b>IDispatch::Invoke</b> on the event sink that implements <b>IPrinterQueueEvent</b>, since that is the mechanism via which events are raised. It is sufficient to provide stub implementations of the other methods on the <b>IDispatch</b> interface.
</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint">IConnectionPoint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterqueueevent">IPrinterQueueEvent</a>
 

 

