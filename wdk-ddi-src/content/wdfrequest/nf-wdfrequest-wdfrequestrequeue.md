---
UID: NF:wdfrequest.WdfRequestRequeue
title: WdfRequestRequeue function (wdfrequest.h)
description: The WdfRequestRequeue method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.
old-location: wdf\wdfrequestrequeue.htm
tech.root: wdf
ms.assetid: 955859d2-7c4f-454c-8621-84bacf0b9770
ms.date: 02/26/2018
keywords: ["WdfRequestRequeue function"]
ms.keywords: DFRequestObjectRef_a51243a8-1412-4765-93a1-7a8f3ab17814.xml, WdfRequestRequeue, WdfRequestRequeue method, kmdf.wdfrequestrequeue, wdf.wdfrequestrequeue, wdfrequest/WdfRequestRequeue
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRequestRequeue
 - wdfrequest/WdfRequestRequeue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfRequestRequeue
---

# WdfRequestRequeue function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestRequeue</b> method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.

## -parameters

### -param Request 

[in]
A handle to a framework request object.

## -returns

<b>WdfRequestRequeue</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
This value is returned if one of the following occurs:

<ul>
<li>
The specified I/O request did not come from an I/O queue.

</li>
<li>
The driver does not own the I/O request.

</li>
<li>
The request is cancelable.

</li>
<li>
The queue's dispatching method is not manual.

</li>
</ul>
</td>
</tr>
</table>
 

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.

## -remarks

A driver can call <b>WdfRequestRequeue</b> only if it using the manual dispatching method for the I/O queue.

If the driver calls <b>WdfRequestRequeue</b> after calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a>, the requeue attempt may succeed before the purge is complete. In versions 1.9 and earlier of KMDF, this 
sequence causes the operating system to crash.  This problem is fixed in KMDF version 1.11 and later.

For more information about <b>WdfRequestRequeue</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/requeuing-i-o-requests">Requeuing I/O Requests</a>.


#### Examples

The following code example returns a specified I/O request to the queue from which the driver received the request.

```cpp
NTSTATUS status;

status = WdfRequestRequeue(request);
```

