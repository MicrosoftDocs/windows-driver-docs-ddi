---
UID: NC:wdfpdo.EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS
title: EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS
author: windows-driver-content
description: A bus driver's EvtDeviceEnableWakeAtBus event callback function performs bus-level operations that enable one of the bus's devices to trigger a wake-up signal on the bus.
old-location: wdf\evtdeviceenablewakeatbus.htm
old-project: wdf
ms.assetid: 902c9bdc-d83a-4bc2-802c-1aaba43c9e2e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdeviceenablewakeatbus, EvtDeviceEnableWakeAtBus callback function, EvtDeviceEnableWakeAtBus, EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS, EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS, wdfpdo/EvtDeviceEnableWakeAtBus, DFDeviceObjectFdoPdoRef_c418526b-2cf2-4193-b75c-f6af5d669433.xml, kmdf.evtdeviceenablewakeatbus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
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
-	Wdfpdo.h
apiname:
-	EvtDeviceEnableWakeAtBus
product: Windows
targetos: Windows
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A bus driver's <i>EvtDeviceEnableWakeAtBus</i> event callback function performs bus-level operations that enable one of the bus's devices to trigger a wake-up signal on the bus.


## -prototype


````
EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS EvtDeviceEnableWakeAtBus;

NTSTATUS EvtDeviceEnableWakeAtBus(
  _In_ WDFDEVICE          Device,
  _In_ SYSTEM_POWER_STATE PowerState
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PowerState [in]

A SYSTEM_POWER_STATE-typed enumerator that identifies the system power state that the system or device will wake from.


## -returns


If the <i>EvtDeviceEnableWakeAtBus</i> callback function encountered no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="..\wdfpdo\nc-wdfpdo-evt_wdf_device_disable_wake_at_bus.md">EvtDeviceDisableWakeAtBus</a> callback function.

 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.





## -remarks


For more information about this callback function, see <a href="https://msdn.microsoft.com/519dcd1a-9975-48b1-a032-04348b903ac5">Supporting System Wake-Up</a>.



## -see-also

<a href="..\wdfpdo\nc-wdfpdo-evt_wdf_device_disable_wake_at_bus.md">EvtDeviceDisableWakeAtBus</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

