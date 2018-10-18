---
UID: NF:ufxclient.UfxDeviceNotifyHardwareReady
title: UfxDeviceNotifyHardwareReady function
author: windows-driver-content
description: Notifies UFX that the hardware is ready.
old-location: buses\ufxdevicenotifyhardwareready.htm
tech.root: usbref
ms.assetid: B4BE0BDC-C1A3-4230-8F4B-78DE34F5554D
ms.date: 5/7/2018
ms.keywords: UfxDeviceNotifyHardwareReady, UfxDeviceNotifyHardwareReady method [Buses], buses.ufxdevicenotifyhardwareready, ufxclient/UfxDeviceNotifyHardwareReady
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: ufxstub.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxDeviceNotifyHardwareReady
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxDeviceNotifyHardwareReady function


## -description


Notifies UFX that the hardware is ready.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


## -returns



This method does not return a value.




## -remarks



The client driver typically calls <b>UfxDeviceNotifyHardwareReady</b> from its <a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a> callback function, as shown in the following example.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
OnEvtDeviceD0Entry (
  _In_ WDFDEVICE Device,
  _In_ WDF_POWER_DEVICE_STATE PreviousState
)
/*++

Routine Description:

    Called by the framework after entering D0 state.

Arguments:

    Device - WDFDEVICE framework handle to the bus FDO.

    PreviousState - The WDF_POWER_DEVICE_STATE from which the stack is
        making this transition.

Return Value:

    Returns STATUS_SUCCESS or an appropriate NTSTATUS code otherwise.

--*/
{
    PCONTROLLER_CONTEXT ControllerContext;

    TraceEntry();

    ControllerContext = DeviceGetControllerContext(Device);

    if (PreviousState &gt; WdfPowerDeviceD1) { 
        DevicePerformSoftReset(Device);

        WdfWaitLockAcquire(ControllerContext-&gt;InitializeDefaultEndpointLock, NULL);
        ControllerContext-&gt;InitializeDefaultEndpoint = TRUE;
        WdfWaitLockRelease(ControllerContext-&gt;InitializeDefaultEndpointLock);
    }

    if (PreviousState == WdfPowerDeviceD3Final) {
        //
        // Notify UFX that HW is now ready
        //
        UfxDeviceNotifyHardwareReady(ControllerContext-&gt;UfxDevice);
    }

    TraceExit();
    return STATUS_SUCCESS;
}</pre>
</td>
</tr>
</table></span></div>


