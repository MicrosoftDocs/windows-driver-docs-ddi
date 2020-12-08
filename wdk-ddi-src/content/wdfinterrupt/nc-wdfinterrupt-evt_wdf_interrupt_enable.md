---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_ENABLE
title: EVT_WDF_INTERRUPT_ENABLE (wdfinterrupt.h)
description: A driver's EvtInterruptEnable event callback function enables a specified hardware interrupt.
old-location: wdf\evtinterruptenable.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_INTERRUPT_ENABLE callback function"]
ms.keywords: DFInterruptObjectRef_eb3a90f0-712a-43fe-8d5c-5a29d1df0a62.xml, EVT_WDF_INTERRUPT_ENABLE, EVT_WDF_INTERRUPT_ENABLE callback, EvtInterruptEnable, EvtInterruptEnable callback function, kmdf.evtinterruptenable, wdf.evtinterruptenable, wdfinterrupt/EvtInterruptEnable
req.header: wdfinterrupt.h
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
req.irql: (See Remarks section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_INTERRUPT_ENABLE
 - wdfinterrupt/EVT_WDF_INTERRUPT_ENABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfinterrupt.h
api_name:
 - EvtInterruptEnable
---

# EVT_WDF_INTERRUPT_ENABLE callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtInterruptEnable</i> event callback function enables a specified hardware interrupt.

## -parameters

### -param Interrupt 

[in]
A handle to a framework interrupt object.

### -param AssociatedDevice 

[in]
A handle to the framework device object that the driver passed to <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>.

## -returns

The <i>EvtInterruptEnable</i> callback function must return STATUS_SUCCESS or another status value for which <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b> if the function encounters no errors. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

## -remarks

To register an <i>EvtInterruptEnable</i> callback function, your driver must place the callback function's address in a <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>.

The framework calls the driver's <i>EvtInterruptEnable</i> callback function each time the device enters its working (D0) state. Additionally, a driver can cause the framework to call the <i>EvtInterruptEnable</i> callback function by calling <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptenable">WdfInterruptEnable</a>.  Note that most framework-based drivers should not call <b>WdfInterruptEnable</b>, because the framework calls the driver's <i>EvtInterruptEnable</i> callback function each time the device enters its working (D0) state.

Before calling the <i>EvtInterruptEnable</i> callback function, the framework raises the processor's IRQL to the device's DIRQL and acquires the spin lock that the driver specified in the interrupt object's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure. 

Beginning with version 1.11 of KMDF, your driver can provide <a href="/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a>. If the driver has requested passive-level interrupt handling, then before calling the <i>EvtInterruptEnable</i> function at IRQL = PASSIVE_LEVEL, the framework acquires the passive-level interrupt lock that the driver configured in the interrupt object's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure.

After the <i>EvtInterruptEnable</i> callback function returns, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry_post_interrupts_enabled">EvtDeviceD0EntryPostInterruptsEnabled</a> event callback function at IRQL = PASSIVE_LEVEL.

You must not assume that a device will use the same interrupt resources each time the framework calls your driver's <i>EvtInterruptEnable</i> callback function. Sometimes the PnP manager <a href="/windows-hardware/drivers/wdf/the-pnp-manager-redistributes-system-resources">redistributes system resources</a>, and it might assign new interrupt resources to your device. The driver can call <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptgetinfo">WdfInterruptGetInfo</a> to determine a device's interrupt resources.

For more information about handling interrupts in framework-based drivers, see <a href="/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry_post_interrupts_enabled">EvtDeviceD0EntryPostInterruptsEnabled</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable">EvtInterruptDisable</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptenable">WdfInterruptEnable</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptgetinfo">WdfInterruptGetInfo</a>
