---
UID: NC:wdfdevice.EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED
title: EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED (wdfdevice.h)
description: A driver's EvtDeviceD0ExitPreInterruptsDisabled event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.
old-location: wdf\evtdeviced0exitpreinterruptsdisabled.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED callback function"]
ms.keywords: DFDeviceObjectGeneralRef_f10df6b2-b5ef-49ad-8333-9289c164ea40.xml, EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED, EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED callback, EvtDeviceD0ExitPreInterruptsDisabled, EvtDeviceD0ExitPreInterruptsDisabled callback function, kmdf.evtdeviced0exitpreinterruptsdisabled, wdf.evtdeviced0exitpreinterruptsdisabled, wdfdevice/EvtDeviceD0ExitPreInterruptsDisabled
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
 - EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED
 - wdfdevice/EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED
---

# EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceD0ExitPreInterruptsDisabled</i> event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param TargetState 

[in]
A <a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a>-typed enumerator that identifies the device power state that the device is about to enter.

## -returns

If the <i>EvtDeviceD0ExitPreInterruptsDisabled</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 

For more information about this callback function's return values, see <a href="/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.

## -remarks

To register an <i>EvtDeviceD0ExitPreInterruptsDisabled</i> callback function, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

The <i>EvtDeviceD0ExitPreInterruptsDisabled</i> callback function is called at IRQL = PASSIVE_LEVEL, before the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable">EvtInterruptDisable</a> callback function. A driver can provide this function if it must perform device-specific operations before disables an interrupt, if those operations should not be performed at IRQL = DIRQL in the <i>EvtInterruptDisable</i> callback function.

For more information about when the framework calls this callback function, see <a href="/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about handling interrupts, see <a href="/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry_post_interrupts_enabled">EvtDeviceD0EntryPostInterruptsEnabled</a>

