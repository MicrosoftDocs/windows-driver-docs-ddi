---
UID: NF:wdfio.WdfIoQueueRetrieveFoundRequest
title: WdfIoQueueRetrieveFoundRequest function
author: windows-driver-content
description: The WdfIoQueueRetrieveFoundRequest method delivers a specified request to the driver, so that the driver can process the request.
old-location: wdf\wdfioqueueretrievefoundrequest.htm
old-project: wdf
ms.assetid: 34447879-1a2e-45de-b754-121a5956330a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoQueueRetrieveFoundRequest, DFQueueObjectRef_17174143-5657-4500-bd07-bf9487e8048e.xml, wdf.wdfioqueueretrievefoundrequest, wdfio/WdfIoQueueRetrieveFoundRequest, kmdf.wdfioqueueretrievefoundrequest, WdfIoQueueRetrieveFoundRequest method, PFN_WDFIOQUEUERETRIEVEFOUNDREQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DoubleCompletion, DriverCreate, KmdfIrql, KmdfIrql2, wdfioqueuefindrequestfailed, wdfioqueueretrievefoundrequest
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfIoQueueRetrieveFoundRequest
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueueRetrieveFoundRequest function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueRetrieveFoundRequest</b> method delivers a specified request to the driver, so that the driver can process the request.


## -syntax


````
NTSTATUS WdfIoQueueRetrieveFoundRequest(
  _In_  WDFQUEUE   Queue,
  _In_  WDFREQUEST FoundRequest,
  _Out_ WDFREQUEST *OutRequest
);
````


## -parameters




#### - Queue [in]

A handle to a framework queue object.


#### - FoundRequest [in]

A handle to a framework request object that was obtained by calling <a href="..\wdfio\nf-wdfio-wdfioqueuefindrequest.md">WdfIoQueueFindRequest</a>.


#### - OutRequest [out]

A pointer to a location that receives a handle to a framework request object. The driver must use this handle when processing the request.


## -returns


<b>WdfIoQueueRetrieveFoundRequest</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
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
The driver supplied an invalid handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The request that is identified by the <i>FoundRequest</i> parameter cannot be found in the I/O queue.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
The framework reached the end of the I/O queue without finding a request that matches the search criteria.

</td>
</tr>
</table> 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


After calling <b>WdfIoQueueRetrieveFoundRequest</b> to obtain an I/O request, the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">owns</a> the request and must <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">process the I/O request</a> in some manner.

Before calling <b>WdfIoQueueRetrieveFoundRequest</b>, the driver must call <a href="..\wdfio\nf-wdfio-wdfioqueuefindrequest.md">WdfIoQueueFindRequest</a>, which retrieves a handle that the driver can use as the <i>FoundRequest</i> parameter to <b>WdfIoQueueRetrieveFoundRequest</b>.

If your driver was built with KMDF version 1.11 or later, the driver can call <b>WdfIoQueueRetrieveFoundRequest</b> without first calling <a href="..\wdfio\nf-wdfio-wdfioqueuefindrequest.md">WdfIoQueueFindRequest</a>. In this case, the driver must ensure that the request object is still valid and in the queue.

If a call to <b>WdfIoQueueRetrieveFoundRequest</b> returns STATUS_NOT_FOUND, a request that was previously in the queue has been removed. The request might have been canceled. 

For more information about the <b>WdfIoQueueRetrieveFoundRequest</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.



## -see-also

<a href="..\wdfio\nf-wdfio-wdfioqueueretrievenextrequest.md">WdfIoQueueRetrieveNextRequest</a>

<a href="..\wdfio\nf-wdfio-wdfioqueuefindrequest.md">WdfIoQueueFindRequest</a>

<a href="..\wdfio\nf-wdfio-wdfioqueueretrieverequestbyfileobject.md">WdfIoQueueRetrieveRequestByFileObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueRetrieveFoundRequest method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

