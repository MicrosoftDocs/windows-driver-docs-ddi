---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY
title: EVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY
author: windows-driver-content
description: The client driver's implementation to determine if the controller supports a specific capability.
old-location: buses\evt_ucx_controller_query_usb_capability.htm
tech.root: usbref
ms.assetid: c01150b6-e6cf-484c-be3e-c63984e97bb3
ms.date: 5/7/2018
ms.keywords: EVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY, EVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY callback, EvtUcxControllerQueryUsbCapability, EvtUcxControllerQueryUsbCapability callback function [Buses], PEVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY, PEVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY callback function pointer [Buses], buses.evt_ucx_controller_query_usb_capability, ucxcontroller/EvtUcxControllerQueryUsbCapability
ms.topic: callback
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ucxcontroller.h
api_name:
-	PEVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY callback function


## -description


The client driver's implementation to determine if the controller supports a specific capability.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param CapabilityType [in]

Pointer to a GUID specifying the requested capability. The possible  <i>PGUID</i>  values are  as follows:

<ul>
<li>GUID_USB_CAPABILITY_CHAINED_MDLS</li>
<li>GUID_USB_CAPABILITY_STATIC_STREAMS</li>
<li>GUID_USB_CAPABILITY_SELECTIVE_SUSPEND</li>
<li>GUID_USB_CAPABILITY_FUNCTION_SUSPEND

</li>
<li>GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE</li>
<li>GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE</li>
<li>GUID_USB_CAPABILITY_CLEAR_TT_BUFFER_ON_ASYNC_TRANSFER_CANCEL<ul>
<li>For typical host controllers, the query must fail (STATUS_NOT_SUPPORTED). If the controller succeeds this capability, it is requesting a Clear TT Buffer when canceling Low Speed/Full Speed asynchronous (Bulk or Control) transfers that have been sent to a TT hub.</li>
</ul>
</li>
</ul>
   See the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/hh406230">USBD_QueryUsbCapability</a> for more information.


### -param OutputBufferLength [in]

The length, in bytes, of the request's output buffer, if an output buffer is available.


### -param OutputBuffer [out, optional]

A pointer to a location that receives the buffer's address. Certain capabilities may need to provide additional information
        to UCX in this buffer.


### -param ResultLength [out]

A location that, on return, contains the size, in bytes, of the information that the callback function stored in <i>OutputBuffer.</i>


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The requested USB capability is supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
The requested USB capability is unknown and not supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Controller does not support the requested USB capability.

For GUID_USB_CAPABILITY_CLEAR_TT_BUFFER_ON_ASYNC_TRANSFER_CANCEL, the controller did not request a Clear TT Buffer when canceling Low Speed/Full Speed
        asynchronous (Bulk or Control) transfers that were sent to a TT hub.

</td>
</tr>
</table>
 




## -remarks



The UCX client driver registers its <i>EVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY</i> implementation with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
Controller_EvtControllerQueryUsbCapability(
    UCXCONTROLLER   UcxController,
    PGUID           CapabilityType,
    ULONG           OutputBufferLength,
    PVOID           OutputBuffer,
    PULONG          ResultLength
)

{
    NTSTATUS status;

    UNREFERENCED_PARAMETER(UcxController);
    UNREFERENCED_PARAMETER(OutputBufferLength);
    UNREFERENCED_PARAMETER(OutputBuffer);

    *ResultLength = 0;

    if (RtlCompareMemory(CapabilityType,
                         &amp;GUID_USB_CAPABILITY_CHAINED_MDLS,
                         sizeof(GUID)) == sizeof(GUID)) {

        //
        // TODO: Is GUID_USB_CAPABILITY_CHAINED_MDLS supported?
        //
        DbgTrace(TL_INFO, Controller, "GUID_USB_CAPABILITY_CHAINED_MDLS not supported");
        status = STATUS_NOT_SUPPORTED;
    }
    else if (RtlCompareMemory(CapabilityType,
                              &amp;GUID_USB_CAPABILITY_STATIC_STREAMS,
                              sizeof(GUID)) == sizeof(GUID)) {

        //
        // TODO: Is GUID_USB_CAPABILITY_STATIC_STREAMS supported?
        //
        DbgTrace(TL_INFO, Controller, "GUID_USB_CAPABILITY_STATIC_STREAMS supported");
        status = STATUS_NOT_SUPPORTED;
    }
    else if (RtlCompareMemory(CapabilityType,
                              &amp;GUID_USB_CAPABILITY_FUNCTION_SUSPEND,
                              sizeof(GUID)) == sizeof(GUID)) {

        //
        // TODO: Is GUID_USB_CAPABILITY_FUNCTION_SUSPEND supported?
        //
        DbgTrace(TL_INFO, Controller, "GUID_USB_CAPABILITY_FUNCTION_SUSPEND not supported");
        status = STATUS_NOT_SUPPORTED;
    }
    else if (RtlCompareMemory(CapabilityType,
                              &amp;GUID_USB_CAPABILITY_SELECTIVE_SUSPEND,
                              sizeof(GUID)) == sizeof(GUID)) {

        DbgTrace(TL_INFO, Controller, "GUID_USB_CAPABILITY_SELECTIVE_SUSPEND supported");
        status = STATUS_SUCCESS;
    }
    else if (RtlCompareMemory(CapabilityType,
                              &amp;GUID_USB_CAPABILITY_CLEAR_TT_BUFFER_ON_ASYNC_TRANSFER_CANCEL,
                              sizeof(GUID)) == sizeof(GUID)) {

        //
        // TODO: Is GUID_USB_CAPABILITY_CLEAR_TT_BUFFER_ON_ASYNC_TRANSFER_CANCEL supported?
        //
        DbgTrace(TL_INFO, Controller, "GUID_USB_CAPABILITY_CLEAR_TT_BUFFER_ON_ASYNC_TRANSFER_CANCEL not supported");
        status = STATUS_NOT_SUPPORTED;
    }
    else {
        DbgTrace(TL_INFO, Controller, "Unhandled USB capability");
        status = STATUS_NOT_IMPLEMENTED;
    }

    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>
 

 

