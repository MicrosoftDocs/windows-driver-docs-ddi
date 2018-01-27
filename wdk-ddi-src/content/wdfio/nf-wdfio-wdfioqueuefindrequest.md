---
UID: NF:wdfio.WdfIoQueueFindRequest
title: WdfIoQueueFindRequest function
author: windows-driver-content
description: The WdfIoQueueFindRequest method locates the next request in an I/O queue, or the next request that matches specified criteria, but does not grant ownership of the request to the driver.
old-location: wdf\wdfioqueuefindrequest.htm
old-project: wdf
ms.assetid: 379fc7ec-577a-48a4-83b0-4be4e8cfe1bf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfio/WdfIoQueueFindRequest, PFN_WDFIOQUEUEFINDREQUEST, DFQueueObjectRef_c0d57542-6256-4502-ad31-8b388857296f.xml, WdfIoQueueFindRequest, wdf.wdfioqueuefindrequest, kmdf.wdfioqueuefindrequest, WdfIoQueueFindRequest method
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, wdfioqueuefindrequestfailed, wdfioqueueretrievefoundrequest, wdfioqueueretrievenextrequest
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
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
-	WdfIoQueueFindRequest
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueueFindRequest function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueFindRequest</b> method locates the next request in an I/O queue, or the next request that matches specified criteria, but does not grant <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">ownership</a> of the request to the driver.


## -syntax


````
NTSTATUS WdfIoQueueFindRequest(
  _In_     WDFQUEUE                Queue,
  _In_opt_ WDFREQUEST              FoundRequest,
  _In_opt_ WDFFILEOBJECT           FileObject,
  _Inout_  PWDF_REQUEST_PARAMETERS Parameters,
  _Out_    WDFREQUEST              *OutRequest
);
````


## -parameters




### -param Queue [in]

A handle to a framework queue object.


### -param FoundRequest [in, optional]

A request object handle that the driver received from a previous call to <b>WdfIoQueueFindRequest</b>. This parameter is optional and can be <b>NULL</b>.


### -param FileObject [in, optional]

A handle to a framework file object. This parameter is optional and can be <b>NULL</b>.


### -param Parameters [in, out]

A pointer to a driver-allocated <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> structure that receives parameters that are associated with the found request. This parameter is optional and can be <b>NULL</b>.


### -param OutRequest [out]

A pointer to a location that receives a handle to the found request. If no match is found, the location receives <b>NULL</b>.


## -returns


<b>WdfIoQueueFindRequest</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
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
The driver supplies an invalid handle.

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


The <b>WdfIoQueueFindRequest</b> method searches a specified I/O queue and attempts to find an I/O request. 

Your driver can call <b>WdfIoQueueFindRequest</b> only if the driver is using the manual <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">dispatching method</a> for the specified I/O queue.

If <i>FileObject</i> is not <b>NULL</b>, <b>WdfIoQueueFindRequest</b> only examines requests that are associated with the specified file object handle.

If <i>FoundRequest</i> is <b>NULL</b>, this method locates the first request in the I/O queue that matches the <i>FileObject</i> value. If <i>FoundRequest</i> is not <b>NULL</b>, the method begins searching at the request that is identified by <i>FoundRequest</i>. To create an iterative loop, specify <b>NULL</b> for the first call, and then use the returned handle as the <i>FoundRequest</i> parameter for subsequent calls.

If <i>Parameters</i> is not <b>NULL</b>, this method copies the found request's parameters into the driver-supplied structure.

Every call to <b>WdfIoQueueFindRequest</b> that returns STATUS_SUCCESS increments the reference count of the request object whose handle is returned in <i>OutRequest</i>. Therefore, your driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a> after you have finished using the handle. 

Calling <b>WdfIoQueueFindRequest</b> does <i>not</i> grant the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">ownership</a> of any requests. If you want your driver to obtain ownership of a request so that it can process the request, the driver must call <a href="..\wdfio\nf-wdfio-wdfioqueueretrievefoundrequest.md">WdfIoQueueRetrieveFoundRequest</a>. In fact, the driver can do only the following with the handle that it receives for the <i>OutRequest</i> parameter:
<ul>
<li>
Use it as the <i>FoundRequest</i> parameter in a subsequent call to <b>WdfIoQueueFindRequest</b>.

</li>
<li>
Use it as the <i>FoundRequest</i> parameter in a subsequent call to <a href="..\wdfio\nf-wdfio-wdfioqueueretrievefoundrequest.md">WdfIoQueueRetrieveFoundRequest</a>.

</li>
<li>
Use it as the input parameter in a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548749">WdfObjectGetTypedContext</a> or a driver-defined method for accessing the object's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">context space</a>.

</li>
<li>
Use it as the input parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a>.

</li>
</ul>If a call to <b>WdfIoQueueFindRequest</b> returns STATUS_NOT_FOUND, a request that was previously in the queue has been removed. The request might have been canceled. A call to <a href="..\wdfio\nf-wdfio-wdfioqueueretrievefoundrequest.md">WdfIoQueueRetrieveFoundRequest</a> can also return STATUS_NOT_FOUND.

For more information about the <b>WdfIoQueueFindRequest</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.



## -see-also

<a href="..\wdfio\nf-wdfio-wdfioqueuestop.md">WdfIoQueueStop</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a>

<a href="..\wdfio\nf-wdfio-wdfioqueueretrievefoundrequest.md">WdfIoQueueRetrieveFoundRequest</a>

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueFindRequest method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

