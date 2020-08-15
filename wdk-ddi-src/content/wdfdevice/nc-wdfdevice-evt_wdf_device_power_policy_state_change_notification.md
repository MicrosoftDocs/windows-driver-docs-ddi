---
UID: NC:wdfdevice.EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION
title: EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION (wdfdevice.h)
description: A driver's EvtDevicePowerPolicyStateChange event callback function informs the driver that a device's power policy state machine is moving from one state to another.
old-location: wdf\evtdevicepowerpolicystatechange.htm
tech.root: wdf
ms.assetid: 91432773-3255-4feb-a6f4-c24da4486703
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION callback function"]
ms.keywords: DFDeviceObjectGeneralRef_e672bc5b-0c7a-4df4-8c21-d3f6aafa6fb8.xml, EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION, EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION callback, EvtDevicePowerPolicyStateChange, EvtDevicePowerPolicyStateChange callback function, kmdf.evtdevicepowerpolicystatechange, wdf.evtdevicepowerpolicystatechange, wdfdevice/EvtDevicePowerPolicyStateChange
f1_keywords:
 - "wdfdevice/EvtDevicePowerPolicyStateChange"
 - "EvtDevicePowerPolicyStateChange"
req.header: wdfdevice.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDevicePowerPolicyStateChange
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

>[!NOTE]
>This callback function is for Microsoft-internal use only.

A driver's <i>EvtDevicePowerPolicyStateChange</i> event callback function informs the driver that a device's power policy state machine is moving from one state to another.


## -parameters




### -param Device 
[in]
A handle to a framework device object.


### -param NotificationData 
[in]
A pointer to a framework-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_notification_data">WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA</a> structure that identifies the state machine's old and new states.


## -remarks



To register an <i>EvtDevicePowerPolicyStateChange</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitregisterpowerpolicystatechangecallback">WdfDeviceInitRegisterPowerPolicyStateChangeCallback</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/state-machines-in-the-framework">State Machines in the Framework</a>.

If the <i>EvtDevicePowerPolicyStateChange</i> callback function calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicestopidle">WdfDeviceStopIdle</a> with the <i>WaitForD0</i> parameter set to <b>TRUE</b>, the framework's power policy state machine will become deadlocked.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_pnp_state_change_notification">EvtDevicePnpStateChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_power_state_change_notification">EvtDevicePowerStateChange</a>
 

 

