---
UID: NC:wdfdevice.EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX
title: EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX
author: windows-driver-content
description: A driver's EvtDeviceDisarmWakeFromSx event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.
old-location: wdf\evtdevicedisarmwakefromsx.htm
old-project: wdf
ms.assetid: 79bf7a42-5053-428a-a78b-dd8bdff93a69
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicedisarmwakefromsx, EvtDeviceDisarmWakeFromSx callback function, EvtDeviceDisarmWakeFromSx, EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX, EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX, wdfdevice/EvtDeviceDisarmWakeFromSx, DFDeviceObjectGeneralRef_ea30bcf7-25ce-493a-a8e0-310657a98c60.xml, kmdf.evtdevicedisarmwakefromsx
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfdevice.h
apiname:
-	EvtDeviceDisarmWakeFromSx
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceDisarmWakeFromSx</i> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.


## -prototype


````
EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX EvtDeviceDisarmWakeFromSx;

VOID EvtDeviceDisarmWakeFromSx(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




#### - Device [in]

A handle to a framework device object.


## -returns


None



## -remarks


To register an <i>EvtDeviceDisarmWakeFromSx</i> callback function, a driver must call  <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.

If the driver has registered this callback function, the framework calls it after the framework has determined that system power is being restored, and after the bus driver completes the <a href="https://msdn.microsoft.com/ed582644-af51-4841-be59-6a3deb6d9de5">wait/wake IRP</a>. Before calling the driver's <i>EvtDeviceDisarmWakeFromSx</i> callback function, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a>, <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a>, and <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered.md">EvtDeviceWakeFromSxTriggered</a> callback functions.

The <i>EvtDeviceDisarmWakeFromSx</i> callback function must perform any hardware operations that are needed to disable the device's ability to trigger a wake signal after the power has been lowered.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about this callback function, see <a href="https://msdn.microsoft.com/519dcd1a-9975-48b1-a032-04348b903ac5">Supporting System Wake-Up</a>.

The <i>EvtDeviceDisarmWakeFromSx</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered.md">EvtDeviceWakeFromSxTriggered</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md">EvtDeviceArmWakeFromSx</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0.md">EvtDeviceDisarmWakeFromS0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

