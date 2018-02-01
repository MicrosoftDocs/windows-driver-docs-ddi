---
UID: NC:wdfpdo.EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS
title: EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS
author: windows-driver-content
description: A bus driver's EvtDeviceDisableWakeAtBus event callback function performs bus-level operations that disable the ability of one of the bus's devices to trigger a wake-up signal on the bus.
old-location: wdf\evtdevicedisablewakeatbus.htm
old-project: wdf
ms.assetid: 91ae9694-5020-42ee-b882-a753e9bbe919
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicedisablewakeatbus, EvtDeviceDisableWakeAtBus callback function, EvtDeviceDisableWakeAtBus, EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS, EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS, wdfpdo/EvtDeviceDisableWakeAtBus, DFDeviceObjectFdoPdoRef_3f6a4a69-a6aa-48a5-9a6a-fd64c569edca.xml, kmdf.evtdevicedisablewakeatbus
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
-	EvtDeviceDisableWakeAtBus
product: Windows
targetos: Windows
req.typenames: "*PWDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO"
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A bus driver's <i>EvtDeviceDisableWakeAtBus</i> event callback function performs bus-level operations that disable the ability of one of the bus's devices to trigger a wake-up signal on the bus.


## -prototype


````
EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS EvtDeviceDisableWakeAtBus;

VOID EvtDeviceDisableWakeAtBus(
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


For more information about this callback function, see <a href="https://msdn.microsoft.com/519dcd1a-9975-48b1-a032-04348b903ac5">Supporting System Wake-Up</a>.



## -see-also

<a href="..\wdfpdo\nc-wdfpdo-evt_wdf_device_enable_wake_at_bus.md">EvtDeviceEnableWakeAtBus</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

