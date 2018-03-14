---
UID: NS:wdfdevice._WDF_POWER_POLICY_EVENT_CALLBACKS
title: "_WDF_POWER_POLICY_EVENT_CALLBACKS"
author: windows-driver-content
description: The WDF_POWER_POLICY_EVENT_CALLBACKS structure contains pointers to a driver's power policy event callback functions.
old-location: wdf\wdf_power_policy_event_callbacks.htm
old-project: wdf
ms.assetid: 6932c938-e477-4a18-9ada-bb3864c6a6f1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_POWER_POLICY_EVENT_CALLBACKS, DFDeviceObjectGeneralRef_d4970639-86cb-4b83-8ac8-a7662ebca017.xml, PWDF_POWER_POLICY_EVENT_CALLBACKS, PWDF_POWER_POLICY_EVENT_CALLBACKS structure pointer, WDF_POWER_POLICY_EVENT_CALLBACKS, WDF_POWER_POLICY_EVENT_CALLBACKS structure, _WDF_POWER_POLICY_EVENT_CALLBACKS, kmdf.wdf_power_policy_event_callbacks, wdf.wdf_power_policy_event_callbacks, wdfdevice/PWDF_POWER_POLICY_EVENT_CALLBACKS, wdfdevice/WDF_POWER_POLICY_EVENT_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_POWER_POLICY_EVENT_CALLBACKS
product: Windows
targetos: Windows
req.typenames: WDF_POWER_POLICY_EVENT_CALLBACKS, *PWDF_POWER_POLICY_EVENT_CALLBACKS
req.product: Windows 10 or later.
---

# _WDF_POWER_POLICY_EVENT_CALLBACKS structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_POWER_POLICY_EVENT_CALLBACKS</b> structure contains pointers to a driver's power policy event callback functions. 


## -syntax


````
typedef struct _WDF_POWER_POLICY_EVENT_CALLBACKS {
  ULONG                                       Size;
  PFN_WDF_DEVICE_ARM_WAKE_FROM_S0             EvtDeviceArmWakeFromS0;
  PFN_WDF_DEVICE_DISARM_WAKE_FROM_S0          EvtDeviceDisarmWakeFromS0;
  PFN_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED       EvtDeviceWakeFromS0Triggered;
  PFN_WDF_DEVICE_ARM_WAKE_FROM_SX             EvtDeviceArmWakeFromSx;
  PFN_WDF_DEVICE_DISARM_WAKE_FROM_SX          EvtDeviceDisarmWakeFromSx;
  PFN_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED       EvtDeviceWakeFromSxTriggered;
  PFN_WDF_DEVICE_ARM_WAKE_FROM_SX_WITH_REASON EvtDeviceArmWakeFromSxWithReason;
} WDF_POWER_POLICY_EVENT_CALLBACKS, *PWDF_POWER_POLICY_EVENT_CALLBACKS;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtDeviceArmWakeFromS0

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md">EvtDeviceArmWakeFromS0</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceDisarmWakeFromS0

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0.md">EvtDeviceDisarmWakeFromS0</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceWakeFromS0Triggered

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_wake_from_s0_triggered.md">EvtDeviceWakeFromS0Triggered</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceArmWakeFromSx

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md">EvtDeviceArmWakeFromSx</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceDisarmWakeFromSx

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx.md">EvtDeviceDisarmWakeFromSx</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceWakeFromSxTriggered

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered.md">EvtDeviceWakeFromSxTriggered</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceArmWakeFromSxWithReason

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason.md">EvtDeviceArmWakeFromSxWithReason</a> event callback function, or <b>NULL</b>.


## -remarks



The <b>WDF_POWER_POLICY_EVENT_CALLBACKS</b> structure is used as input to the <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md">WdfDeviceInitSetPowerPolicyEventCallbacks</a> method.

Your driver should initialize its <b>WDF_POWER_POLICY_EVENT_CALLBACKS</b> structure by calling <a href="..\wdfdevice\nf-wdfdevice-wdf_power_policy_event_callbacks_init.md">WDF_POWER_POLICY_EVENT_CALLBACKS_INIT</a>.




## -see-also

<a href="..\wdfdevice\ns-wdfdevice-_wdf_pnppower_event_callbacks.md">WDF_PNPPOWER_EVENT_CALLBACKS</a>



 

 


