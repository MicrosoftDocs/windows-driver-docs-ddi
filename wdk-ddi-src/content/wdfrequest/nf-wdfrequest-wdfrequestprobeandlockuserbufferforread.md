---
UID: NF:wdfrequest.WdfRequestProbeAndLockUserBufferForRead
title: WdfRequestProbeAndLockUserBufferForRead function
author: windows-driver-content
description: The WdfRequestProbeAndLockUserBufferForRead method verifies that an I/O request's user-mode buffer is readable, and then it locks the buffer's physical memory pages so drivers in the driver stack can read the buffer.
old-location: wdf\wdfrequestprobeandlockuserbufferforread.htm
old-project: wdf
ms.assetid: 68fbaa04-ca7a-46b4-a7ca-c3d44443c2af
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_01a2309b-8cae-4a38-9e47-68619f422af2.xml, WdfRequestProbeAndLockUserBufferForRead, WdfRequestProbeAndLockUserBufferForRead method, kmdf.wdfrequestprobeandlockuserbufferforread, wdf.wdfrequestprobeandlockuserbufferforread, wdfrequest/WdfRequestProbeAndLockUserBufferForRead
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfRequestProbeAndLockUserBufferForRead
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestProbeAndLockUserBufferForRead function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestProbeAndLockUserBufferForRead</b> method verifies that an I/O request's user-mode buffer is readable, and then it locks the buffer's physical memory pages so drivers in the driver stack can read the buffer.


## -parameters




### -param Request [in]

A handle to a framework request object. 


### -param Buffer [in]

A pointer to the request's input buffer. For more information, see the following Remarks section.


### -param Length [in]

The length, in bytes, of the request's input buffer.


### -param MemoryObject [out]

A pointer to a location that receives a handle to a framework memory object that represents the user input buffer.


## -returns



<b>WdfRequestProbeAndLockUserBufferForRead</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
<dt><b>STATUS_INVALID_USER_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Length</i> parameter is zero.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The request has already been completed or is otherwise invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>
</td>
<td width="60%">
The current thread is not the creator of the I/O request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory to complete the operation.

</td>
</tr>
</table>
 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Only a top-level driver can call the <b>WdfRequestProbeAndLockUserBufferForRead</b> method, because the method requires the process context of the process that created the I/O request.

The user input buffer typically contains information to be written to the device.

The user-mode buffer that the <i>Buffer</i> parameter specifies can be the buffer that <a href="https://msdn.microsoft.com/library/windows/hardware/ff550022">WdfRequestRetrieveUnsafeUserInputBuffer</a> retrieves, or it can be a different user-mode input buffer. For example, an I/O control code that uses the buffered access method might pass a structure that contains an embedded pointer to a user-mode buffer. In such a case, the driver can use<b>WdfRequestProbeAndLockUserBufferForRead</b> to obtain a memory object for the buffer. 

The buffer length that the <i>Length</i> parameter specifies must not be larger than the buffer's actual size. Otherwise, drivers can access memory outside of the buffer, which is a security risk.

If <b>WdfRequestProbeAndLockUserBufferForRead</b> returns STATUS_SUCCESS, the driver receives a handle to a framework memory object that represents the user-mode buffer. To access the buffer, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a>.

For more information about <b>WdfRequestProbeAndLockUserBufferForRead</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.


#### Examples

The following code example is a shortened version of the <a href="https://msdn.microsoft.com/b8bcea29-e404-490e-9d0c-02c96a5690ab">EvtIoInCallerContext</a> callback function that the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">NONPNP</a> sample driver contains. When the callback function receives an I/O request, it determines if the request contains an I/O control code with a transfer type of METHOD_NEITHER. If the request does contain such an I/O control code, the function:

<ol>
<li>
Calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550022">WdfRequestRetrieveUnsafeUserInputBuffer</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550024">WdfRequestRetrieveUnsafeUserOutputBuffer</a> to obtain the virtual addresses of the request's read and write buffers.

</li>
<li>
Calls <b>WdfRequestProbeAndLockUserBufferForRead</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549989">WdfRequestProbeAndLockUserBufferForWrite</a> to probe and lock the buffers and to obtain a handle to a framework memory object that represents each buffer.

</li>
</ol>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
NonPnpEvtIoInCallerContext(
    IN WDFDEVICE  Device,
    IN WDFREQUEST Request
    )
{
    NTSTATUS  status = STATUS_SUCCESS;
    PREQUEST_CONTEXT  reqContext = NULL;
    WDF_OBJECT_ATTRIBUTES  attributes;
    WDF_REQUEST_PARAMETERS  params;
    size_t  inBufLen, outBufLen;
    PVOID  inBuf, outBuf;

    WDF_REQUEST_PARAMETERS_INIT(&amp;params);
    WdfRequestGetParameters(
                            Request,
                            &amp;params
                            );

    //
    // Check to see whether the driver received a METHOD_NEITHER I/O control code.
    // If not, just send the request back to the framework.
    //
    if(!(params.Type == WdfRequestTypeDeviceControl &amp;&amp;
            params.Parameters.DeviceIoControl.IoControlCode ==
                                    IOCTL_NONPNP_METHOD_NEITHER)) {
        status = WdfDeviceEnqueueRequest(
                                         Device,
                                         Request
                                         );
        if( !NT_SUCCESS(status) ) {
            goto End;
        }
        return;
    }

    //
    // The I/O control code is METHOD_NEITHER.
    // First, retrieve the virtual addresses of 
    // the input and output buffers.
    //
    status = WdfRequestRetrieveUnsafeUserInputBuffer(
                                                     Request,
                                                     0,
                                                     &amp;inBuf,
                                                     &amp;inBufLen
                                                     );
    if(!NT_SUCCESS(status)) {
        goto End;
    }
    status = WdfRequestRetrieveUnsafeUserOutputBuffer(
                                                      Request,
                                                      0,
                                                      &amp;outBuf,
                                                      &amp;outBufLen
                                                      );
    if(!NT_SUCCESS(status)) {
       goto End;
    }

    //
    // Next, allocate context space for the request, so that the
    // driver can store handles to the memory objects that will
    // be created for input and output buffers.
    //
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;attributes,
                                        REQUEST_CONTEXT);
    status = WdfObjectAllocateContext(
                                      Request,
                                      &amp;attributes,
                                      &amp;reqContext
                                      );
    if(!NT_SUCCESS(status)) {
        goto End;
    }

    //
    // Next, probe and lock the read and write buffers.
    //
    status = WdfRequestProbeAndLockUserBufferForRead(
                                                     Request,
                                                     inBuf,
                                                     inBufLen,
                                                     &amp;reqContext-&gt;InputMemoryBuffer
                                                     );
    if(!NT_SUCCESS(status)) {
        goto End;
    }

    status = WdfRequestProbeAndLockUserBufferForWrite(
                                                      Request,
                                                      outBuf,
                                                      outBufLen,
                                                      &amp;reqContext-&gt;OutputMemoryBuffer
                                                      );
    if(!NT_SUCCESS(status)) {
        goto End;
    }

    //
    // Finally, return the request to the framework.
    //
    status = WdfDeviceEnqueueRequest(
                                     Device,
                                     Request
                                     );
    if(!NT_SUCCESS(status)) {
        goto End;
    }
    return;

End:
    WdfRequestComplete(
                       Request,
                       status
                       );
    return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549989">WdfRequestProbeAndLockUserBufferForWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550022">WdfRequestRetrieveUnsafeUserInputBuffer</a>
 

 

