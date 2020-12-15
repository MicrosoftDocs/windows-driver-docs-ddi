---
UID: NC:wdfdevice.EVT_WDF_DEVICE_D0_ENTRY
title: EVT_WDF_DEVICE_D0_ENTRY (wdfdevice.h)
description: A driver's EvtDeviceD0Entry event callback function performs operations that are needed when the driver's device enters the D0 power state.
old-location: wdf\evtdeviced0entry.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_D0_ENTRY callback function"]
ms.keywords: DFDeviceObjectGeneralRef_2be6c269-2579-4358-ba3a-855672e6d2bc.xml, EVT_WDF_DEVICE_D0_ENTRY, EVT_WDF_DEVICE_D0_ENTRY callback, EvtDeviceD0Entry, EvtDeviceD0Entry callback function, kmdf.evtdeviced0entry, wdf.evtdeviced0entry, wdfdevice/EvtDeviceD0Entry
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DEVICE_D0_ENTRY
 - wdfdevice/EVT_WDF_DEVICE_D0_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtDeviceD0Entry
---

# EVT_WDF_DEVICE_D0_ENTRY callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceD0Entry</i> event callback function performs operations that are needed when the driver's device enters the D0 power state.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param PreviousState 

[in]
A <a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a>-typed enumerator that identifies the previous device power state.

## -returns

If the <i>EvtDeviceD0Entry</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 

For more information about this callback function's return values, see <a href="/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.



The framework does not call the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> callback function after the <i>EvtDeviceD0Entry</i> callback function returns a status value for which NT_SUCCESS(status) equals <b>FALSE</b>.

## -remarks

To register an <i>EvtDeviceD0Entry</i> callback function for a device, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceD0Entry</i> callback function for a device, the framework calls the function each time the device enters its working (D0) state. A device will enter the D0 state when one of the following occurs:

<ul>
<li>
A device is enumerated (because the device was plugged in or the system was rebooted).

</li>
<li>
The system and all of its devices return to their working states from a low-power state.

</li>
<li>
The device returns to its working state after it entered a low-power state because it was idle (if the device supports low-power idle).

</li>
<li>
The Plug and Play manager has redistributed the system's hardware resources among the system's devices.

</li>
</ul>
The framework calls the <i>EvtDeviceD0Entry</i> callback function immediately after the device enters its working (D0) state and is available to the driver, but before the device's interrupts have been enabled. The <i>PreviousState</i> parameter identifies the device power state that the device was in before it entered the D0 state.   When the framework first calls <i>EvtDeviceD0Entry</i>, it provides a <i>PreviousState</i> value of <b>WdfPowerDeviceD3Final</b>.

The callback function must perform any operations that are needed to make the device fully operational, such as loading firmware or enabling device capabilities that are disabled when the device is in a low-power state. 

If the <i>EvtDeviceD0Entry</i> callback function returns a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, the framework does the following:

<ul>
<li>
If the device is starting for the first time, the framework begins an <a href="/windows-hardware/drivers/wdf/a-user-unplugs-a-device">orderly removal</a> sequence for the device.

</li>
<li>
If the device is returning from a low-power state to its working state, the framework begins a <a href="/windows-hardware/drivers/wdf/a-user-unplugs-a-device">surprise removal</a> sequence for the device.

</li>
</ul>
The framework does not call the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> callback function in either of these situations.

For more information about when the framework calls the <i>EvtDeviceD0Entry</i> callback function, see <a href="/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="/windows-hardware/drivers/wdf/supporting-pnp-and-power-management-in-function-drivers">Supporting PnP and Power Management in Function Drivers</a>.

The <i>EvtDeviceD0Entry</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a>
