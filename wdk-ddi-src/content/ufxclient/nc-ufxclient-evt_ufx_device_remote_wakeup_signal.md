---
UID: NC:ufxclient.EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL
title: EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL (ufxclient.h)
description: The client driver's implementation to initiate remote wake-up on the function controller.
old-location: buses\evt_ufx_device_remote_wakeup_signal.htm
tech.root: usbref
ms.assetid: A1250501-DC33-4AA8-8AD7-9938ECAC8AFB
ms.date: 05/07/2018
ms.keywords: EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL, EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL callback, EvtUfxDeviceRemoteWakeupSignal, EvtUfxDeviceRemoteWakeupSignal callback function [Buses], PFN_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL, PFN_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL callback function pointer [Buses], buses.evt_ufx_device_remote_wakeup_signal, ufxclient/EvtUfxDeviceRemoteWakeupSignal
ms.topic: callback
f1_keywords:
 - "ufxclient/PFN_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ufxclient.h
api_name:
- PFN_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL callback function


## -description


The client driver's implementation to initiate remote wake-up on the function controller.


## -parameters




### -param Arg1








#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL</i> implementation with the USB function class extension (UFX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a> method.

The client driver indicates completion of this event by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL UfxDevice_EvtDeviceRemoteWakeupSignal;

VOID
UfxDevice_EvtDeviceRemoteWakeupSignal (
    _In_ UFXDEVICE UfxDevice
    )
/*++
Routine Description:

    Signals Remote Wakeup to the Host by issuing a link state change command.
    It acquires and releases the power reference to ensure a valid power state
    before accessing the device.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

--*/
{
    NTSTATUS Status;
    PUFXDEVICE_CONTEXT DeviceContext;

    PAGED_CODE();

    TraceEntry();

    DeviceContext = UfxDeviceGetContext(UfxDevice);

    //
    // Stop Idle to ensure the device is in working state
    //

    Status = WdfDeviceStopIdle(DeviceContext->FdoWdfDevice, TRUE);
    if (!NT_SUCCESS(Status)) {
        TraceError("Failed to stop idle %!STATUS!", Status);
        goto End;
    }

    //
    // Issue a Link State Change Request.
    //

    //
    // #### TODO: Insert code to issue a link state change on the controller ####
    //

    WdfDeviceResumeIdle(DeviceContext->FdoWdfDevice);

End:
    UfxDeviceEventComplete(UfxDevice, Status);
    TraceExit();
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a>
 

 

