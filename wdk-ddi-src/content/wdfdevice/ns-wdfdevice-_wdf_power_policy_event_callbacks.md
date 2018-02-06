---
UID: NS:wdfdevice._WDF_POWER_POLICY_EVENT_CALLBACKS
title: "_WDF_POWER_POLICY_EVENT_CALLBACKS"
author: windows-driver-content
description: The WDF_POWER_POLICY_EVENT_CALLBACKS structure contains pointers to a driver's power policy event callback functions.
old-location: wdf\wdf_power_policy_event_callbacks.htm
old-project: wdf
ms.assetid: 6932c938-e477-4a18-9ada-bb3864c6a6f1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdevice/WDF_POWER_POLICY_EVENT_CALLBACKS, WDF_POWER_POLICY_EVENT_CALLBACKS, DFDeviceObjectGeneralRef_d4970639-86cb-4b83-8ac8-a7662ebca017.xml, PWDF_POWER_POLICY_EVENT_CALLBACKS structure pointer, _WDF_POWER_POLICY_EVENT_CALLBACKS, PWDF_POWER_POLICY_EVENT_CALLBACKS, wdfdevice/PWDF_POWER_POLICY_EVENT_CALLBACKS, kmdf.wdf_power_policy_event_callbacks, WDF_POWER_POLICY_EVENT_CALLBACKS structure, *PWDF_POWER_POLICY_EVENT_CALLBACKS, wdf.wdf_power_policy_event_callbacks
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_POWER_POLICY_EVENT_CALLBACKS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

