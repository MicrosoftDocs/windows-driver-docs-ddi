---
UID: NN:printerextension.IPrinterQueueEvent
title: IPrinterQueueEvent (printerextension.h)
description: Provides the event delegate for printer queue events.
old-location: print\iprinterqueueevent_interface.htm
tech.root: print
ms.assetid: AA4B2578-61C9-47C3-A114-4B873B475124
ms.date: 04/20/2018
ms.keywords: IPrinterQueueEvent, IPrinterQueueEvent interface [Print Devices], IPrinterQueueEvent interface [Print Devices],described, print.iprinterqueueevent_interface, printerextension/IPrinterQueueEvent
ms.topic: interface
f1_keywords:
 - "printerextension/IPrinterQueueEvent"
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
- IPrinterQueueEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueueEvent interface


## -description


Provides the event delegate for printer queue events.


## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IPrinterQueueEvent</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrinterQueueEvent</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks



An event sink that implements <b>IPrinterQueueEvent</b> and the event source, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterqueue">IPrinterQueue</a> are connected via the <a href="https://docs.microsoft.com/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint">IConnectionPoint</a> mechanism. You must retrieve a pointer to the <b>IConnectionPoint</b> interface by invoking <b>QueryInterface</b> on the <b>IPrinterQueue</b> object.

<div class="alert"><b>Note</b>  It is mandatory to implement <b>IDispatch::Invoke</b> on the event sink that implements <b>IPrinterQueueEvent</b>, since that is the mechanism via which events are raised. It is sufficient to provide stub implementations of the other methods on the <b>IDispatch</b> interface.
</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint">IConnectionPoint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterqueue">IPrinterQueue</a>
 

 

