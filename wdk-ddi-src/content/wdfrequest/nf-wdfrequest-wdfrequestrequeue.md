---
UID: NF:wdfrequest.WdfRequestRequeue
title: WdfRequestRequeue function
author: windows-driver-content
description: The WdfRequestRequeue method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.
old-location: wdf\wdfrequestrequeue.htm
old-project: wdf
ms.assetid: 955859d2-7c4f-454c-8621-84bacf0b9770
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRequestRequeue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfRequestRequeue
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
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
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestRequeue function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestRequeue</b> method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.



## -syntax

````
NTSTATUS WdfRequestRequeue(
  _In_ WDFREQUEST Request
);
````


## -parameters

### -param Request [in]

A handle to a framework request object. 


## -returns
<b>WdfRequestRequeue</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter is invalid.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>This value is returned if one of the following occurs:

The specified I/O request did not come from an I/O queue.

The driver does not own the I/O request.

The request is cancelable.

The queue's dispatching method is not manual.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.


## -remarks
A driver can call <b>WdfRequestRequeue</b> only if it using the manual dispatching method for the I/O queue.

If the driver calls <b>WdfRequestRequeue</b> after calling <a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a>, the requeue attempt may succeed before the purge is complete. In versions 1.9 and earlier of KMDF, this 
sequence causes the operating system to crash.  This problem is fixed in KMDF version 1.11 and later.

For more information about <b>WdfRequestRequeue</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/requeuing-i-o-requests">Requeuing I/O Requests</a>.

The following code example returns a specified I/O request to the queue from which the driver received the request.</p>