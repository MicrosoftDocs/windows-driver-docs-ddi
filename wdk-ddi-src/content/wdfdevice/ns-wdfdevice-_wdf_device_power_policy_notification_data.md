---
UID: NS:wdfdevice._WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA
title: "_WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA"
author: windows-driver-content
description: The WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA structure describes a state change within a device's power policy state machine.
old-location: wdf\wdf_device_power_policy_notification_data.htm
tech.root: wdf
ms.assetid: aa91ea9b-3d92-4f33-8bbd-dd64a76a0a86
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_b2b78d41-642d-4e2d-89cc-8ea27a033c77.xml, WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA, WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA structure, _WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA, kmdf.wdf_device_power_policy_notification_data, wdf.wdf_device_power_policy_notification_data, wdfdevice/WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA
product:
- Windows
targetos: Windows
req.typenames: WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA
---

# _WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA structure


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA</b> structure describes a state change within a device's power policy state machine.


## -struct-fields




### -field Type

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552513">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerator that identifies the type of state change that is being reported.


### -field Data


### -field Data.EnterState


### -field Data.EnterState.CurrentState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551275">WDF_DEVICE_POWER_POLICY_STATE</a>-typed enumerator identifies the state machine's current state.


### -field Data.EnterState.NewState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551275">WDF_DEVICE_POWER_POLICY_STATE</a>-typed enumerator identifies the state machine's next state.


### -field Data.PostProcessState


### -field Data.PostProcessState.CurrentState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551275">WDF_DEVICE_POWER_POLICY_STATE</a>-typed enumerator identifies the state machine's current state.


### -field Data.LeaveState


### -field Data.LeaveState.CurrentState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551275">WDF_DEVICE_POWER_POLICY_STATE</a>-typed enumerator identifies the state machine's current state.


### -field Data.LeaveState.NewState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="https://msdn.microsoft.com/library/windows/hardware/ff551275">WDF_DEVICE_POWER_POLICY_STATE</a>-typed enumerator identifies the state machine's next state.


## -remarks



The <b>WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA</b> structure is an input argument to a driver's <a href="https://msdn.microsoft.com/91432773-3255-4feb-a6f4-c24da4486703">EvtDevicePowerPolicyStateChange</a> callback function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546066">WdfDeviceInitRegisterPowerPolicyStateChangeCallback</a>
 

 

