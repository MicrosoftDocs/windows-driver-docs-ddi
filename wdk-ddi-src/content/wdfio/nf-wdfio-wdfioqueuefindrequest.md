---
UID: NF:wdfio.WdfIoQueueFindRequest
title: WdfIoQueueFindRequest function
author: windows-driver-content
description: The WdfIoQueueFindRequest method locates the next request in an I/O queue, or the next request that matches specified criteria, but does not grant ownership of the request to the driver.
old-location: wdf\wdfioqueuefindrequest.htm
old-project: wdf
ms.assetid: 379fc7ec-577a-48a4-83b0-4be4e8cfe1bf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_c0d57542-6256-4502-ad31-8b388857296f.xml, WdfIoQueueFindRequest, WdfIoQueueFindRequest method, kmdf.wdfioqueuefindrequest, wdf.wdfioqueuefindrequest, wdfio/WdfIoQueueFindRequest
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfIoQueueFindRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoQueueFindRequest function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueFindRequest</b> method locates the next request in an I/O queue, or the next request that matches specified criteria, but does not grant <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">ownership</a> of the request to the driver.


## -parameters




### -param Queue [in]

A handle to a framework queue object.


### -param FoundRequest [in, optional]

A request object handle that the driver received from a previous call to <b>WdfIoQueueFindRequest</b>. This parameter is optional and can be <b>NULL</b>.


### -param FileObject [in, optional]

A handle to a framework file object. This parameter is optional and can be <b>NULL</b>.


### -param Parameters [in, out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a> structure that receives parameters that are associated with the found request. This parameter is optional and can be <b>NULL</b>.


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

Calling <b>WdfIoQueueFindRequest</b> does <i>not</i> grant the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">ownership</a> of any requests. If you want your driver to obtain ownership of a request so that it can process the request, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/hh975099">WdfIoQueueRetrieveFoundRequest</a>. In fact, the driver can do only the following with the handle that it receives for the <i>OutRequest</i> parameter:

<ul>
<li>
Use it as the <i>FoundRequest</i> parameter in a subsequent call to <b>WdfIoQueueFindRequest</b>.

</li>
<li>
Use it as the <i>FoundRequest</i> parameter in a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh975099">WdfIoQueueRetrieveFoundRequest</a>.

</li>
<li>
Use it as the input parameter in a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548749">WdfObjectGetTypedContext</a> or a driver-defined method for accessing the object's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">context space</a>.

</li>
<li>
Use it as the input parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a>.

</li>
</ul>
If a call to <b>WdfIoQueueFindRequest</b> returns STATUS_NOT_FOUND, a request that was previously in the queue has been removed. The request might have been canceled. A call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh975099">WdfIoQueueRetrieveFoundRequest</a> can also return STATUS_NOT_FOUND.

For more information about the <b>WdfIoQueueFindRequest</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

<b>Example 1</b>

The following code example is from the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">PCIDRV</a> sample driver. This example searches an I/O queue for a request that contains a specified I/O function code. If a matching request is found, the example calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh975099">WdfIoQueueRetrieveFoundRequest</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
NICGetIoctlRequest(
    IN WDFQUEUE Queue,
    IN ULONG FunctionCode,
    OUT WDFREQUEST*  Request
    )
{
    NTSTATUS  status = STATUS_UNSUCCESSFUL;
    WDF_REQUEST_PARAMETERS  params;
    WDFREQUEST  tagRequest;
    WDFREQUEST  prevTagRequest;

    WDF_REQUEST_PARAMETERS_INIT(&amp;params);
 
    *Request = NULL;
    prevTagRequest = tagRequest = NULL;

    do {
        WDF_REQUEST_PARAMETERS_INIT(&amp;params);
        status = WdfIoQueueFindRequest(
                                       Queue,
                                       prevTagRequest,
                                       NULL,
                                       &amp;params,
                                       &amp;tagRequest
                                       );
        if (prevTagRequest) {
            WdfObjectDereference(prevTagRequest);
        }
        if (status == STATUS_NO_MORE_ENTRIES) {
            status = STATUS_UNSUCCESSFUL;
            break;
        }
        if (status == STATUS_NOT_FOUND) {
            //
            // The prevTagRequest request has disappeared from the
            // queue. There might be other requests that match
            // the criteria, so restart the search. 
            //
            prevTagRequest = tagRequest = NULL;
            continue;
        }
        if (!NT_SUCCESS(status)) { 
            status = STATUS_UNSUCCESSFUL;
            break;
        }
        if (FunctionCode == params.Parameters.DeviceIoControl.IoControlCode){
            //
            // Found a match. Retrieve the request from the queue.
            //
            status = WdfIoQueueRetrieveFoundRequest(
                                                    Queue,
                                                    tagRequest,
                                                    Request
                                                    );
            WdfObjectDereference(tagRequest);
            if (status == STATUS_NOT_FOUND) {
                //
                // The tagRequest request has disappeared from the
                // queue. There might be other requests that match 
                // the criteria, so restart the search. 
                //
                prevTagRequest = tagRequest = NULL;
                continue;
            }
            if (!NT_SUCCESS(status)) {
                status = STATUS_UNSUCCESSFUL;
                break;
            }
            //
            //  Found a request.
            //
            ASSERT(*Request == tagRequest);
            status =  STATUS_SUCCESS;
            break;
        } else {
            //
            // This request is not the correct one. Drop the reference 
            // on the tagRequest after the driver obtains the next request.
            //
            prevTagRequest = tagRequest;
            continue;
        }
    } while (TRUE);
    return status;

}</pre>
</td>
</tr>
</table></span></div>
<b>Example 2</b>

The following code example shows how you can create a general-purpose search routine that calls a search-specific subroutine. If your driver must search one or more queues for multiple types of information, you can provide multiple search-specific subroutines. Each time that your driver calls the general-purpose search routine, it specifies the address of one of your search-specific subroutines.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>//
// Type declaration for the driver's search-specific subroutines. 
//
typedef BOOLEAN (*PFN_CALLBACK_COMPARE)(WDFREQUEST, ULONG);

//
// General-purpose search routine. One of the routine's
// parameters is the address of a search-specific
// subroutine. The search routine calls back to the
// subroutine.
//
WDFREQUEST
FindRequestWithMatchingData(
    __in WDFQUEUE Queue,
    __in PFN_CALLBACK_COMPARE CallbackCompare,
    __in ULONG Data
    )
{
    WDFREQUEST  prevTagRequest = NULL;
    WDFREQUEST  tagRequest = NULL;
    WDFREQUEST  outRequest = NULL;
    NTSTATUS  status = STATUS_INVALID_DEVICE_REQUEST;

    PAGED_CODE();

    do {
        status = WdfIoQueueFindRequest(Queue,
                                       prevTagRequest,
                                       NULL,
                                       NULL,
                                       &amp;tagRequest);
        if (prevTagRequest) {
            //
            // WdfIoQueueFindRequest incremented the
            // reference count of the prevTagRequest object,
            // so we decrement the count here.
            //
            WdfObjectDereference(prevTagRequest);
        }
        if (status == STATUS_NO_MORE_ENTRIES) {
            KdPrint(("WdfIoQueueFindRequest returned status 0x%x\n", status));
            break;
        }
        if (status == STATUS_NOT_FOUND) {
            //
            // The prevTagRequest object is no longer
            // in the queue.
            //
            prevTagRequest = tagRequest = NULL;
            continue;
        }
        if ( !NT_SUCCESS(status)) {
            KdPrint(("WdfIoQueueFindRequest failed 0x%x\n", status));
            break;
        }

        //
        // We have a handle to the next request that is
        // in the queue. Now we call the subroutine
        // that determines if this request matches our 
        // search criteria.
        //
        if (CallbackCompare(tagRequest, Data)) {
            // 
            // We found a match. Get the request handle.
            // 
            status = WdfIoQueueRetrieveFoundRequest(Queue,
                                                    tagRequest,
                                                    &amp;outRequest);
            //
            // WdfIoQueueRetrieveFoundRequest incremented the
            // reference count of the TagRequest object,
            // so we decrement the count here.
            //
            WdfObjectDereference(tagRequest);

            if (status == STATUS_NOT_FOUND) {
                //
                // The TagRequest object is no longer
                // in the queue. But other requests might
                // match our criteria, so we restart the search.
                //
                prevTagRequest = tagRequest = NULL;
                continue;
            }

            if (!NT_SUCCESS(status)) {
                KdPrint(("WdfIoQueueRetrieveFoundRequest failed 0x%x\n", 
                          status));
            }

            //
            // We found the request we were looking for. 
            //
            break;

        } else {
            //
            // The request did not match our criteria.
            // Get another request.
            //
            prevTagRequest = tagRequest;
            continue;
        }
    } while(TRUE);
    return outRequest;
 }

/
// An example of a driver's search-specific subroutine.
// Your driver can have multiple subroutines to handle
// multiple types of searches.
//
BOOLEAN
CallbackCheckForInfo1(
    __in WDFREQUEST Request,
    __in ULONG DataToBeMatched
    )
{
    PREQUEST_CONTEXT reqContext;

    PAGED_CODE();

    //
    // Retrieve information that the driver has stored
    // in the request object's context space.
    //
    reqContext = GetRequestContext(Request);
    if (reqContext-&gt;ContextInfo1 == DataToBeMatched) {
        return TRUE;
    }
    else {
        return FALSE;
    }
}

//
// This code shows a call to the FindRequestWithMatchingData routine.
//
WDFREQUEST  matchedRequest = NULL;
...
matchedRequest = FindRequestWithMatchingData(readQueue,
                                             CallbackCheckForInfo1,
                                             INFO_VALUE);
if (matchedRequest != NULL) {
    // 
    // Found a request with a context value of INFO_VALIUE.
    //
...
}
... </pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975099">WdfIoQueueRetrieveFoundRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548482">WdfIoQueueStop</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a>
 

 

