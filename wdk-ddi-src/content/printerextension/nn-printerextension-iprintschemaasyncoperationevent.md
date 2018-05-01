---
UID: NN:printerextension.IPrintSchemaAsyncOperationEvent
title: IPrintSchemaAsyncOperationEvent
author: windows-driver-content
description: Exposes a validation, merge, or commit completion event delegate.
old-location: print\iprintschemaasyncoperationevent_interface.htm
old-project: print
ms.assetid: 4ADF74C0-F196-476F-889D-EB1A0B881920
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintSchemaAsyncOperationEvent, IPrintSchemaAsyncOperationEvent interface [Print Devices], IPrintSchemaAsyncOperationEvent interface [Print Devices],described, print.iprintschemaasyncoperationevent_interface, printerextension/IPrintSchemaAsyncOperationEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaAsyncOperationEvent
product: Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaAsyncOperationEvent interface


## -description


Exposes a validation, merge, or commit completion event delegate. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaAsyncOperationEvent</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrintSchemaAsyncOperationEvent</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintSchemaAsyncOperationEvent</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265386">Completed</a>
</td>
<td align="left" width="63%">
Is called when asynchronous PrintSchema operation that is represented by an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451224">IPrintSchemaAsyncOperation</a> context is completed.

</td>
</tr>
</table> 


## -remarks



An event sink that implements <b>IPrintSchemaAsyncOperationEvent</b> and the event source, <a href="https://msdn.microsoft.com/library/windows/hardware/hh451224">IPrintSchemaAsyncOperation</a> are connected via the <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ms694318(v=vs.85).aspx">IConnectionPoint</a> mechanism. You must retrieve a pointer to the <b>IConnectionPoint</b> interface by invoking <b>QueryInterface</b> on the <b>IPrinterQueue</b> object.

<div class="alert"><b>Note</b>  It is mandatory to implement <b>IDispatch::Invoke</b> on the event sink that implements <b>IPrinterQueueEvent</b>, since that is the mechanism via which events are raised. It is sufficient to provide stub implementations of the other methods on the <b>IDispatch</b> interface.
</div>
<div> </div>



## -see-also




<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ms694318(v=vs.85).aspx">IConnectionPoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451224">IPrintSchemaAsyncOperation</a>
 

 

