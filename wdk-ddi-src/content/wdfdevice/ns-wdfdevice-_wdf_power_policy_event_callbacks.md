---
UID: NS:wdfdevice._WDF_POWER_POLICY_EVENT_CALLBACKS
title: _WDF_POWER_POLICY_EVENT_CALLBACKS (wdfdevice.h)
description: The WDF_POWER_POLICY_EVENT_CALLBACKS structure contains pointers to a driver's power policy event callback functions.
old-location: wdf\wdf_power_policy_event_callbacks.htm
tech.root: wdf
ms.assetid: 6932c938-e477-4a18-9ada-bb3864c6a6f1
ms.date: 02/26/2018
ms.keywords: "*PWDF_POWER_POLICY_EVENT_CALLBACKS, DFDeviceObjectGeneralRef_d4970639-86cb-4b83-8ac8-a7662ebca017.xml, PWDF_POWER_POLICY_EVENT_CALLBACKS, PWDF_POWER_POLICY_EVENT_CALLBACKS structure pointer, WDF_POWER_POLICY_EVENT_CALLBACKS, WDF_POWER_POLICY_EVENT_CALLBACKS structure, _WDF_POWER_POLICY_EVENT_CALLBACKS, kmdf.wdf_power_policy_event_callbacks, wdf.wdf_power_policy_event_callbacks, wdfdevice/PWDF_POWER_POLICY_EVENT_CALLBACKS, wdfdevice/WDF_POWER_POLICY_EVENT_CALLBACKS"
ms.topic: struct
f1_keywords:
 - "wdfdevice/WDF_POWER_POLICY_EVENT_CALLBACKS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfdevice.h
api_name:
- WDF_POWER_POLICY_EVENT_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: WDF_POWER_POLICY_EVENT_CALLBACKS, *PWDF_POWER_POLICY_EVENT_CALLBACKS
---

# _WDF_POWER_POLICY_EVENT_CALLBACKS structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_POWER_POLICY_EVENT_CALLBACKS</b> structure contains pointers to a driver's power policy event callback functions. 


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtDeviceArmWakeFromS0

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0">EvtDeviceArmWakeFromS0</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceDisarmWakeFromS0

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0">EvtDeviceDisarmWakeFromS0</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceWakeFromS0Triggered

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_wake_from_s0_triggered">EvtDeviceWakeFromS0Triggered</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceArmWakeFromSx

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx">EvtDeviceArmWakeFromSx</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceDisarmWakeFromSx

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx">EvtDeviceDisarmWakeFromSx</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceWakeFromSxTriggered

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered">EvtDeviceWakeFromSxTriggered</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceArmWakeFromSxWithReason

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason">EvtDeviceArmWakeFromSxWithReason</a> event callback function, or <b>NULL</b>.


## -remarks



The <b>WDF_POWER_POLICY_EVENT_CALLBACKS</b> structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks">WdfDeviceInitSetPowerPolicyEventCallbacks</a> method.

Your driver should initialize its <b>WDF_POWER_POLICY_EVENT_CALLBACKS</b> structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdf_power_policy_event_callbacks_init">WDF_POWER_POLICY_EVENT_CALLBACKS_INIT</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_pnppower_event_callbacks">WDF_PNPPOWER_EVENT_CALLBACKS</a>
 

 

