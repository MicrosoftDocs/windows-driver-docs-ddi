---
UID: NN:printerextension.IPrintSchemaAsyncOperation
title: IPrintSchemaAsyncOperation (printerextension.h)
description: Represents an asynchronous operation context for validation, merge or commit operations.
old-location: print\iprintschemaasyncoperation_interface.htm
tech.root: print
ms.assetid: CEA80412-4B19-493B-A85E-625915D77CA5
ms.date: 04/20/2018
ms.keywords: IPrintSchemaAsyncOperation, IPrintSchemaAsyncOperation interface [Print Devices], IPrintSchemaAsyncOperation interface [Print Devices],described, print.iprintschemaasyncoperation_interface, printerextension/IPrintSchemaAsyncOperation
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
- IPrintSchemaAsyncOperation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaAsyncOperation interface


## -description


Represents an asynchronous operation context for validation, merge or commit operations.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaAsyncOperation</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrintSchemaAsyncOperation</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintSchemaAsyncOperation</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406716">Cancel</a>
</td>
<td align="left" width="63%">
Cancels the asynchronous PrintSchema operation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973223">Start</a>
</td>
<td align="left" width="63%">
Starts the asynchronous PrintSchema operation.

</td>
</tr>
</table> 


## -remarks



Any event sink that implements <a href="https://msdn.microsoft.com/library/windows/hardware/hh451211">IPrintSchemaAsyncOperationEvent</a> is connected to the associated event source, <b>IPrintSchemaAsyncOperation</b>, via the <a href="https://msdn.microsoft.com/library/windows/desktop/ms694318(v=vs.85).aspx">IConnectionPoint</a> mechanism. You must retrieve a pointer to the <b>IConnectionPoint</b> interface by invoking <b>QueryInterface</b> on the <b>IPrinterQueue</b> object.

<div class="alert"><b>Note</b>  It is mandatory to implement <b>IDispatch::Invoke</b> on the event sink that implements <b>IPrinterQueueEvent</b>, since that is the mechanism via which events are raised. It is sufficient to provide stub implementations of the other methods on the <b>IDispatch</b> interface.
</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/desktop/ms694318(v=vs.85).aspx">IConnectionPoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451211">IPrintSchemaAsyncOperationEvent</a>
 

 

