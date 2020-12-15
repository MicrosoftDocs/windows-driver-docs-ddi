---
UID: NF:wdfio.WdfIoQueueRetrieveFoundRequest
title: WdfIoQueueRetrieveFoundRequest function (wdfio.h)
description: The WdfIoQueueRetrieveFoundRequest method delivers a specified request to the driver, so that the driver can process the request.
old-location: wdf\wdfioqueueretrievefoundrequest.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfIoQueueRetrieveFoundRequest function"]
ms.keywords: DFQueueObjectRef_17174143-5657-4500-bd07-bf9487e8048e.xml, WdfIoQueueRetrieveFoundRequest, WdfIoQueueRetrieveFoundRequest method, kmdf.wdfioqueueretrievefoundrequest, wdf.wdfioqueueretrievefoundrequest, wdfio/WdfIoQueueRetrieveFoundRequest
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfIoQueueRetrieveFoundRequest
 - wdfio/WdfIoQueueRetrieveFoundRequest
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
 - WdfIoQueueRetrieveFoundRequest
---

# WdfIoQueueRetrieveFoundRequest function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueueRetrieveFoundRequest</b> method delivers a specified request to the driver, so that the driver can process the request.

## -parameters

### -param Queue 

[in]
A handle to a framework queue object.

### -param FoundRequest 

[in]
A handle to a framework request object that was obtained by calling <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuefindrequest">WdfIoQueueFindRequest</a>.

### -param OutRequest 

[out]
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
 

This method also might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

After calling <b>WdfIoQueueRetrieveFoundRequest</b> to obtain an I/O request, the driver <a href="/windows-hardware/drivers/wdf/request-ownership">owns</a> the request and must <a href="/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">process the I/O request</a> in some manner.

Before calling <b>WdfIoQueueRetrieveFoundRequest</b>, the driver must call <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuefindrequest">WdfIoQueueFindRequest</a>, which retrieves a handle that the driver can use as the <i>FoundRequest</i> parameter to <b>WdfIoQueueRetrieveFoundRequest</b>.

If your driver was built with KMDF version 1.11 or later, the driver can call <b>WdfIoQueueRetrieveFoundRequest</b> without first calling <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuefindrequest">WdfIoQueueFindRequest</a>. In this case, the driver must ensure that the request object is still valid and in the queue.

If a call to <b>WdfIoQueueRetrieveFoundRequest</b> returns STATUS_NOT_FOUND, a request that was previously in the queue has been removed. The request might have been canceled. 

For more information about the <b>WdfIoQueueRetrieveFoundRequest</b> method, see <a href="/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

For a code example that uses <b>WdfIoQueueRetrieveFoundRequest</b>, see <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuefindrequest">WdfIoQueueFindRequest</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuefindrequest">WdfIoQueueFindRequest</a>



<a href="/windows-hardware/drivers/devtest/kmdf-wdfioqueueretrievenextrequest">WdfIoQueueRetrieveNextRequest</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueueretrieverequestbyfileobject">WdfIoQueueRetrieveRequestByFileObject</a>
