---
UID: NC:wdfdevice.EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION
title: EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION (wdfdevice.h)
description: A driver's EvtDevicePowerStateChange event callback function informs the driver that a device's power state machine is moving from one state to another.
old-location: wdf\evtdevicepowerstatechange.htm
tech.root: wdf
ms.assetid: 9f54c7e2-0c8a-46ee-9318-6db934c1aab6
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION callback function"]
ms.keywords: DFDeviceObjectGeneralRef_fc945165-b31d-4d35-b3be-5586c280d8ca.xml, EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION, EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION callback, EvtDevicePowerStateChange, EvtDevicePowerStateChange callback function, kmdf.evtdevicepowerstatechange, wdf.evtdevicepowerstatechange, wdfdevice/EvtDevicePowerStateChange
f1_keywords:
 - "wdfdevice/EvtDevicePowerStateChange"
 - "EvtDevicePowerStateChange"
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
- EvtDevicePowerStateChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

>[!NOTE]
>This callback function is for Microsoft-internal use only.

A driver's <i>EvtDevicePowerStateChange</i> event callback function informs the driver that a device's power state machine is moving from one state to another.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param NotificationData [in]

A pointer to a framework-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_notification_data">WDF_DEVICE_POWER_NOTIFICATION_DATA</a> structure that identifies the state machine's old and new states.


## -remarks



To register an <i>EvtDevicePowerStateChange</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitregisterpowerstatechangecallback">WdfDeviceInitRegisterPowerStateChangeCallback</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/state-machines-in-the-framework">State Machines in the Framework</a>.

If the <i>EvtDevicePowerStateChange</i> callback function calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicestopidle">WdfDeviceStopIdle</a> with the <i>WaitForD0</i> parameter set to <b>TRUE</b>, the framework's power state machine will become deadlocked.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_pnp_state_change_notification">EvtDevicePnpStateChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_power_policy_state_change_notification">EvtDevicePowerPolicyStateChange</a>
 

 

