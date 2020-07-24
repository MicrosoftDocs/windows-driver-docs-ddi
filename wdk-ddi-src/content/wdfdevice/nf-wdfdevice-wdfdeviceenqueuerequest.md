---
UID: NF:wdfdevice.WdfDeviceEnqueueRequest
title: WdfDeviceEnqueueRequest function (wdfdevice.h)
description: The WdfDeviceEnqueueRequest method delivers a specified I/O request to the framework, so that the framework can subsequently add the request to one of the I/O queues that the driver has created for the specified device.
old-location: wdf\wdfdeviceenqueuerequest.htm
tech.root: wdf
ms.assetid: f669790f-0370-46a0-ba38-05e35cdf23b3
ms.date: 02/26/2018
keywords: ["WdfDeviceEnqueueRequest function"]
ms.keywords: DFDeviceObjectGeneralRef_f97fc280-163f-4931-a222-6a8ccf3251d2.xml, WdfDeviceEnqueueRequest, WdfDeviceEnqueueRequest method, kmdf.wdfdeviceenqueuerequest, wdf.wdfdeviceenqueuerequest, wdfdevice/WdfDeviceEnqueueRequest
f1_keywords:
 - "wdfdevice/WdfDeviceEnqueueRequest"
 - "WdfDeviceEnqueueRequest"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, KmdfIrql, KmdfIrql2, RequestCompleted, RequestCompletedLocal
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL (See remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceEnqueueRequest
targetos: Windows
req.typenames: 
---

# WdfDeviceEnqueueRequest function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceEnqueueRequest</b> method delivers a specified I/O request to the framework, so that the framework can subsequently add the request to one of the I/O queues that the driver has created for the specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Request [in]

A handle to a framework request object.


## -returns



If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The amount of available memory is low.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The driver has not created any I/O queues for the device, and the driver is not a filter driver.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The device's I/O queue is not accepting requests.

</td>
</tr>
</table>
 

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Your driver can call <b>WdfDeviceEnqueueRequest</b> only from an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_io_in_caller_context">EvtIoInCallerContext</a> callback function.

The <b>WdfDeviceEnqueueRequest</b> method adds the request to the driver's request-type-specific I/O queue for the device, if the driver has created one. Otherwise the method adds the request to the device's default queue, if the driver has created one.

If the driver has not created any I/O queues for the device, <b>WdfDeviceEnqueueRequest</b> does the following:

<ul>
<li>
If the driver is a filter driver, <b>WdfDeviceEnqueueRequest</b> sends the request to the driver's I/O target.

</li>
<li>
If the driver is not a filter driver, <b>WdfDeviceEnqueueRequest</b> returns STATUS_INVALID_DEVICE_REQUEST.

</li>
</ul>
While <b>WdfDeviceEnqueueRequest</b> is executing, it is possible for the driver to receive and complete or cancel the request.

As a result, if the driver needs to use the request or its context after calling <b>WdfDeviceEnqueueRequest</b>, then it should take a reference on the request before calling <b>WdfDeviceEnqueueRequest</b>.

To do so, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a> before and then <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectdereference">WdfObjectDereference</a> after the call to <b>WdfDeviceEnqueueRequest</b>. The driver must dereference the request before exiting <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_io_in_caller_context">EvtIoInCallerContext</a>.

For more information about the <b>WdfDeviceEnqueueRequest</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.

For versions 1.0 and 1.5 of KMDF, <b>WdfDeviceEnqueueRequest</b> must be called at PASSIVE_LEVEL. For versions 1.7 and later, <b>WdfDeviceEnqueueRequest</b> can be called at IRQL <= DISPATCH_LEVEL.


#### Examples

The following code example is an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_io_in_caller_context">EvtIoInCallerContext</a> callback function that looks for requests that contain the custom I/O control code, IOCTL_NONPNP_METHOD_NEITHER. If the I/O control code is not found, the callback function just returns the request to the framework. If the callback function finds the I/O control code, it preprocesses the request and then returns it to the framework. If an error is encountered, the callback function completes the request.

```cpp
VOID
MyEvtDeviceIoInCallerContext(
    IN WDFDEVICE  Device,
    IN WDFREQUEST Request
    )
{
    NTSTATUS  status = STATUS_SUCCESS;
    WDF_REQUEST_PARAMETERS  params;

    WDF_REQUEST_PARAMETERS_INIT(&params);
    WdfRequestGetParameters(
                            Request,
                            &params
                            );
    if(!(params.Type == WdfRequestTypeDeviceControl &&
         params.Parameters.DeviceIoControl.IoControlCode == IOCTL_NONPNP_METHOD_NEITHER)) {
        status = WdfDeviceEnqueueRequest(
                                         Device,
                                         Request
                                         );
        if(!NT_SUCCESS(status)) {
            goto End;
        }
        return;
    }
    //
    // Found a match for the control code. Preprocess the request, and then
    // return the request to the framework.
    //

    //...(Preprocess the request here.)

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
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_parameters_init">WDF_REQUEST_PARAMETERS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a>
 

 

