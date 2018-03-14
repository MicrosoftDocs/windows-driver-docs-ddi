---
UID: NF:wdfrequest.WdfRequestRetrieveOutputBuffer
title: WdfRequestRetrieveOutputBuffer function
author: windows-driver-content
description: The WdfRequestRetrieveOutputBuffer method retrieves an I/O request's output buffer.
old-location: wdf\wdfrequestretrieveoutputbuffer.htm
old-project: wdf
ms.assetid: 5f12dd97-d8e7-4fef-91bf-00243c0cdd52
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_05ab728b-3b70-4095-acca-294443797557.xml, WdfRequestRetrieveOutputBuffer, WdfRequestRetrieveOutputBuffer method, kmdf.wdfrequestretrieveoutputbuffer, wdf.wdfrequestretrieveoutputbuffer, wdfrequest/WdfRequestRetrieveOutputBuffer
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
req.ddi-compliance: BufAfterReqCompletedIntIoctl, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctl, BufAfterReqCompletedIoctlA, BufAfterReqCompletedRead, BufAfterReqCompletedReadA, BufAfterReqCompletedWrite, DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, OutputBufferAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
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
-	WdfRequestRetrieveOutputBuffer
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestRetrieveOutputBuffer function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestRetrieveOutputBuffer</b> method retrieves an I/O request's output buffer.


## -syntax


````
NTSTATUS WdfRequestRetrieveOutputBuffer(
  _In_      WDFREQUEST Request,
  _In_      size_t     MinimumRequiredSize,
  _Out_     PVOID      *Buffer,
  _Out_opt_ size_t     *Length
);
````


## -parameters




### -param Request [in]

A handle to a framework request object. 


### -param MinimumRequiredSize [in]

The minimum buffer size, in bytes, that the driver needs to process the I/O request.


### -param Buffer [out]

A pointer to a location that receives the buffer's address.


### -param Length [out, optional]

A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>WdfRequestRetrieveOutputBuffer</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The output buffer's length is zero, or the <i>MinimumRequiredSize</i> parameter specifies a buffer size that is larger than the buffer's actual size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The request type is not valid or the request is using <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>. For more information about supported methods for accessing data buffers, see the following Remarks section.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The request has already been completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory.

</td>
</tr>
</table>
 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.




## -remarks



A request's output buffer receives information, such as data from a disk, that the driver provides to the originator of the request. Your driver can call <b>WdfRequestRetrieveOutputBuffer</b> to obtain the output buffer for a read request or a device I/O control request, but not for a write request (because write requests do not provide output data).

The <b>WdfRequestRetrieveOutputBuffer</b> method retrieves the output buffer for I/O requests that use the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">buffered I/O</a> method or the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">direct I/O</a> method for accessing data buffers. If the request's I/O control code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>, or if the request came from another kernel-mode driver, <b>WdfRequestRetrieveOutputBuffer</b> also supports I/O requests that use <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>. 

If <b>WdfRequestRetrieveOutputBuffer</b> returns STATUS_SUCCESS, the driver receives the address and, optionally, the size of the output buffer. 

The driver can access the retrieved buffer until it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes the I/O request</a> that the <i>Request</i> parameter represents.

Instead of calling <b>WdfRequestRetrieveOutputBuffer</b>, the driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a>, which creates a framework memory object that represents the buffer.

For more information about <b>WdfRequestRetrieveOutputBuffer</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.


#### Examples

The following code example is part of an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_device_control.md">EvtIoDeviceControl</a> callback function. This example obtains a USB device's configuration descriptor and places the descriptor in the I/O request's output buffer.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyEvtIoDeviceControl(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  OutputBufferLength,
    IN size_t  InputBufferLength,
    IN ULONG  IoControlCode    
    )
{
    WDFDEVICE  device;
    PDEVICE_CONTEXT  pDevContext;
    size_t  bytesReturned = 0;
    NTSTATUS  status;

    device = WdfIoQueueGetDevice(Queue);
    //
    // GetDeviceContext is a driver-defined function 
    // to retrieve device object context space.
    //
    pDevContext = GetDeviceContext(device);

    switch(IoControlCode) {

      case IOCTL_OSRUSBFX2_GET_CONFIG_DESCRIPTOR: {
 
        PUSB_CONFIGURATION_DESCRIPTOR  configurationDescriptor = NULL;
        USHORT  requiredSize;

        //
        // First, get the size of the USB configuration descriptor.
        //
        status = WdfUsbTargetDeviceRetrieveConfigDescriptor(
                                                pDevContext-&gt;UsbDevice,
                                                NULL,
                                                &amp;requiredSize
                                                );
        if (status != STATUS_BUFFER_TOO_SMALL) {
            break;
        }

        //
        // Get the buffer. Make sure the buffer is big
        // enough to hold the configuration descriptor.
        //
        status = WdfRequestRetrieveOutputBuffer(
                                                Request, 
                                                (size_t)requiredSize,
                                                &amp;configurationDescriptor,
                                                NULL
                                                );
        if(!NT_SUCCESS(status)){
            break;
        }
        //
        // Now get the config descriptor.
        //
        status = WdfUsbTargetDeviceRetrieveConfigDescriptor(
                                                pDevContext-&gt;UsbDevice,
                                                configurationDescriptor,
                                                &amp;requiredSize
                                                );
        if (!NT_SUCCESS(status)) {
            break;
        }

        bytesReturned = requiredSize;
      }
        break;
...
    (Other case statements removed.)
...
    default:
        status = STATUS_INVALID_DEVICE_REQUEST;
        break;
    }
    //
    // Complete the request.
    //
    WdfRequestCompleteWithInformation(
                                      Request,
                                      status,
                                      bytesReturned
                                      );
    return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputbuffer.md">WdfRequestRetrieveInputBuffer</a>



 

 


