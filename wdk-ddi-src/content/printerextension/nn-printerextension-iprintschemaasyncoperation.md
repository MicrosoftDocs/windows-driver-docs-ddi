---
UID: NN:printerextension.IPrintSchemaAsyncOperation
title: IPrintSchemaAsyncOperation
author: windows-driver-content
description: Represents an asynchronous operation context for validation, merge or commit operations.
old-location: print\iprintschemaasyncoperation_interface.htm
old-project: print
ms.assetid: CEA80412-4B19-493B-A85E-625915D77CA5
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintSchemaTicket2, IPrintSchemaTicket2::GetParameterInitializer, GetParameterInitializer
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
req.alt-api: IPrintSchemaAsyncOperation
req.alt-loc: Printerextension.h
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
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaAsyncOperation interface



## -description
Represents an asynchronous operation context for validation, merge or commit operations.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaAsyncOperation</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IDispatch</b></a> interface. <b>IPrintSchemaAsyncOperation</b> also has these types of members:

The <b>IPrintSchemaAsyncOperation</b> interface has these methods.

Cancels the asynchronous PrintSchema operation.

Starts the asynchronous PrintSchema operation.

 


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
</table>Cancels the asynchronous PrintSchema operation.

Starts the asynchronous PrintSchema operation.

 


## -remarks
Any event sink that implements <a href="..\printerextension\nn-printerextension-iprintschemaasyncoperationevent.md">IPrintSchemaAsyncOperationEvent</a> is connected to the associated event source, <b>IPrintSchemaAsyncOperation</b>, via the <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ms694318(v=vs.85).aspx">IConnectionPoint</a> mechanism. You must retrieve a pointer to the <b>IConnectionPoint</b> interface by invoking <b>QueryInterface</b> on the <b>IPrinterQueue</b> object.


## -see-also
<dl>
<dt><a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ms694318(v=vs.85).aspx">IConnectionPoint</a></dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschemaasyncoperationevent.md">IPrintSchemaAsyncOperationEvent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaAsyncOperation interface%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

