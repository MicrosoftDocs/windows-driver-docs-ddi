---
UID: NC:wdfdevice.EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED
title: EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED
author: windows-driver-content
description: A driver's EvtDeviceWakeFromSxTriggered event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal.
old-location: wdf\evtdevicewakefromsxtriggered.htm
old-project: wdf
ms.assetid: a1899d90-4906-458d-b7e3-122655f4d926
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicewakefromsxtriggered, EvtDeviceWakeFromSxTriggered callback function, EvtDeviceWakeFromSxTriggered, EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED, EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED, wdfdevice/EvtDeviceWakeFromSxTriggered, DFDeviceObjectGeneralRef_38946496-1155-44d9-8636-8343c4623000.xml, kmdf.evtdevicewakefromsxtriggered
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfdevice.h
apiname:
-	EvtDeviceWakeFromSxTriggered
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceWakeFromSxTriggered</i> event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal.


## -prototype


````
EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED EvtDeviceWakeFromSxTriggered;

VOID EvtDeviceWakeFromSxTriggered(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns


None



## -remarks


To register an <i>EvtDeviceWakeFromSxTriggered</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.

If the driver has registered this callback, the framework calls it after calling the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> callback function and before calling the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx.md">EvtDeviceDisarmWakeFromSx</a> callback function.

System hardware (BIOSes, motherboards, bus adapters) can sometimes drop a wake signal before the bus driver detects it, even though the signal wakes up the system. In such cases, the driver's <i>EvtDeviceWakeFromSxTriggered</i> callback function will not be called even though the driver's device triggered a wake signal.

Some buses combine wake signals from several children. If your device is connected to one of these buses, the callback function might have to determine if the current device triggered the wake-up signal. If your device provides a hardware latch that saves the device's triggered state, it is best to check that state in the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx.md">EvtDeviceDisarmWakeFromSx</a> callback function, because that callback is always called after the device wakes up, even if the wake signal was dropped.

For more information about this callback function, see <a href="https://msdn.microsoft.com/519dcd1a-9975-48b1-a032-04348b903ac5">Supporting System Wake-Up</a>.



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx.md">EvtDeviceDisarmWakeFromSx</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_wake_from_s0_triggered.md">EvtDeviceWakeFromS0Triggered</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md">EvtDeviceArmWakeFromSx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

