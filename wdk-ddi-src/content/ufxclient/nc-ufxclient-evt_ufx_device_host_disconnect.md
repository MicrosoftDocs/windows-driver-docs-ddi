---
UID: NC:ufxclient.EVT_UFX_DEVICE_HOST_DISCONNECT
title: EVT_UFX_DEVICE_HOST_DISCONNECT (ufxclient.h)
description: The client driver's implementation to disable the function controller's communication with the host.
old-location: buses\evt_ufx_device_host_disconnect.htm
tech.root: usbref
ms.assetid: 01E66957-BB9B-4C35-920F-2DC0F01123E5
ms.date: 05/07/2018
ms.keywords: EVT_UFX_DEVICE_HOST_DISCONNECT, EVT_UFX_DEVICE_HOST_DISCONNECT callback, EvtUfxDeviceHostDisconnect, EvtUfxDeviceHostDisconnect callback function [Buses], PFN_UFX_DEVICE_HOST_DISCONNECT, PFN_UFX_DEVICE_HOST_DISCONNECT callback function pointer [Buses], buses.evt_ufx_device_host_disconnect, ufxclient/EvtUfxDeviceHostDisconnect
ms.topic: callback
req.header: ufxclient.h
req.include-header: 
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ufxclient.h
api_name:
- PFN_UFX_DEVICE_HOST_DISCONNECT
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UFX_DEVICE_HOST_DISCONNECT callback function


## -description


The client driver's implementation to disable the function controller's communication with the host.


## -parameters




### -param Arg1








#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_HOST_DISCONNECT</i> implementation with the USB function class extension (UFX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a> method.

UFX invokes this  event callback to perform a soft-disconnect on the USB cable. After this call, the client driver must not initiate a connection with the host until UFX invokes <a href="https://msdn.microsoft.com/library/windows/hardware/mt187852">EVT_UFX_DEVICE_HOST_CONNECT</a>. 

The client driver indicates completion of this event by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UFX_DEVICE_HOST_DISCONNECT UfxDevice_EvtDeviceHostDisconnect;

VOID
UfxDevice_EvtDeviceHostDisconnect (
    _In_ UFXDEVICE UfxDevice
    )
/*++

Routine Description:

    EvtDeviceHostDisconnect callback handler for UFXDEVICE object.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

--*/
{

    PCONTROLLER_CONTEXT ControllerContext;
    PUFXDEVICE_CONTEXT DeviceContext;
    BOOLEAN EventComplete;

    TraceEntry();

    DeviceContext = UfxDeviceGetContext(UfxDevice);
    ControllerContext = DeviceGetControllerContext(DeviceContext->FdoWdfDevice);

    EventComplete = TRUE;

    //
    // #### TODO: Cancel all transfers. ####
    //

    WdfSpinLockAcquire(ControllerContext->DpcLock);

    //
    // #### TODO: Insert code to clear the run state on the controller ####
    //
    
    WdfSpinLockRelease(ControllerContext->DpcLock);

    if (EventComplete) {
        UfxDeviceEventComplete(UfxDevice, STATUS_SUCCESS);
    }

    TraceExit();
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a>
 

 

