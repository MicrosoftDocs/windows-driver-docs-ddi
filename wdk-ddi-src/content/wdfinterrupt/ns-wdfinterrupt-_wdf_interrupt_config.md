---
UID: NS:wdfinterrupt._WDF_INTERRUPT_CONFIG
title: _WDF_INTERRUPT_CONFIG (wdfinterrupt.h)
description: The WDF_INTERRUPT_CONFIG structure contains configuration information for a device interrupt.
old-location: wdf\wdf_interrupt_config.htm
tech.root: wdf
ms.assetid: 10eb623d-6778-4ccb-8ed4-9926c13dec5a
ms.date: 02/26/2018
keywords: ["_WDF_INTERRUPT_CONFIG structure"]
ms.keywords: "*PWDF_INTERRUPT_CONFIG, DFInterruptObjectRef_545890e4-5222-42e8-8fba-c159a0faa140.xml, PWDF_INTERRUPT_CONFIG, PWDF_INTERRUPT_CONFIG structure pointer, WDF_INTERRUPT_CONFIG, WDF_INTERRUPT_CONFIG structure, _WDF_INTERRUPT_CONFIG, kmdf.wdf_interrupt_config, wdf.wdf_interrupt_config, wdfinterrupt/PWDF_INTERRUPT_CONFIG, wdfinterrupt/WDF_INTERRUPT_CONFIG"
f1_keywords:
 - "wdfinterrupt/WDF_INTERRUPT_CONFIG"
 - "WDF_INTERRUPT_CONFIG"
req.header: wdfinterrupt.h
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
- wdfinterrupt.h
api_name:
- WDF_INTERRUPT_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_CONFIG, *PWDF_INTERRUPT_CONFIG
---

# _WDF_INTERRUPT_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_INTERRUPT_CONFIG</b> structure contains configuration information for a device interrupt.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field SpinLock

The handle to a framework spin-lock object, obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfspinlockcreate">WdfSpinLockCreate</a>, or <b>NULL</b>. If this parameter is <b>NULL</b>, the framework uses an internal spin-lock object. The framework acquires the spin lock before it calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize">EvtInterruptSynchronize</a> event callback function and when the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>. For passive-level interrupt handling, set to NULL.

Starting with UMDF version 2.0, UMDF always uses passive-level interrupt handling. In this case, set this member to NULL.


### -field ShareVector

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed value. If this value is <b>WdfTrue</b>, the interrupt vector can be shared. If the value is <b>WdfFalse</b>, the interrupt vector cannot be shared. If the value is <b>WdfDefault</b>, the PnP manager uses the bus driver's value.


### -field FloatingSave

A Boolean value that, if <b>TRUE</b>, indicates that the system will save the processor's floating point and MMX state when the device interrupts. If <b>FALSE</b>, the system does not save the floating point and MMX state. A driver should set this value to <b>TRUE</b> only if its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function must use floating point or MMX registers. For more information about saving floating point and MMX state, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-floating-point-or-mmx-in-a-wdm-driver">Using Floating Point or MMX in a WDM Driver</a>.

This member is ignored starting in UMDF version 2.0.


### -field AutomaticSerialization

A Boolean value that, if <b>TRUE</b>, indicates that the framework will synchronize execution of the interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>    or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a> callback function with callback functions from other objects that are underneath the interrupt's parent  object.  For more information, see the following Remarks section.


### -field EvtInterruptIsr

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function. This pointer cannot be <b>NULL</b>.


### -field EvtInterruptDpc

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function, or <b>NULL</b>. The driver can provide <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a> or <i>EvtInterruptDpc</i>, but not both.


### -field EvtInterruptEnable

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable">EvtInterruptEnable</a> callback function, or <b>NULL</b>.


### -field EvtInterruptDisable

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable">EvtInterruptDisable</a> callback function, or <b>NULL</b>.


### -field EvtInterruptWorkItem

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a> callback function, or <b>NULL</b>. The driver can provide <i>EvtInterruptWorkItem</i> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>, but not both. The <b>EvtInterruptWorkItem</b> member is available in version 1.11 and later versions of KMDF.


### -field InterruptRaw

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/raw-and-translated-resources">raw resources</a> that the system assigned to the interrupt. This member is only used if the interrupt is created in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback. The <b>InterruptRaw</b> member is available in version 1.11 and later versions of KMDF.


### -field InterruptTranslated

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/raw-and-translated-resources">translated resources</a> that the system assigned to the interrupt. This member is only used if the interrupt is created in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback. The <b>InterruptTranslated</b> member is available in version 1.11 and later versions of KMDF.


### -field WaitLock

A handle to a framework wait-lock object, obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfwaitlockcreate">WdfWaitLockCreate</a>, or <b>NULL</b>. If <b>WaitLock</b> is non-<b>NULL</b>, <b>PassiveHandling</b> must be set to <b>TRUE</b>.  The <b>WaitLock</b> member is available in version 1.11 and later versions of KMDF.  For more information about <b>WaitLock</b>, see  <b>Remarks</b>.


### -field PassiveHandling

Set to <b>FALSE</b> for interrupt handling at the device's IRQL (DIRQL).
Set to <b>TRUE</b> for passive-level interrupt handling.
The <b>PassiveHandling</b> member is available in version 1.11 and later versions of KMDF. Starting in UMDF version 2.0, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdf_interrupt_config_init">WDF_INTERRUPT_CONFIG_INIT</a> always sets this member to TRUE.


### -field ReportInactiveOnPowerDown

This member applies to KMDF only.

 A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed value that applies only if the driver has not called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowernotpageable">WdfDeviceInitSetPowerNotPageable</a>.  This member can have one of the following values:

<b>WdfTrue</b> - KMDF reports the interrupt inactive when the device transitions to a low-power (Dx) state.        In operating systems prior to Windows 8, the framework's behavior matches that described for  <b>WdfFalse</b>.


<div class="alert"><b>Note</b>  If <b>CanWakeDevice</b> is set to <b>TRUE</b> and <b>ReportInactiveOnPowerDown</b> is set to <b>WdfTrue</b>, the framework does not report  the interrupt inactive when the device transitions to a low-power state.</div>
<div> </div>


<b>WdfFalse</b> - KMDF disconnects the interrupt when the device transitions to a low-power (Dx) state.

<b>WdfDefault</b> - On ARM-based platforms, the framework's behavior matches that described for  <b>WdfTrue</b>. On other platforms, the framework's behavior matches that described for  <b>WdfFalse</b>.

The <b>ReportInactiveOnPowerDown</b> member is available in version 1.11 and later versions of KMDF. It is not available in UMDF version 2.0.

For more information about reporting an interrupt inactive, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/making-an-isr-active-or-inactive">Making an ISR Active or Inactive</a>.


### -field CanWakeDevice

A Boolean value that indicates whether the interrupt is used to wake the device from a low-power state.
If <b>FALSE</b>, the interrupt is not used to wake the device. If <b>TRUE</b>, the interrupt is used to wake the device.
The <b>CanWakeDevice</b> member is available starting in KMDF version 1.13 and UMDF version 2.0.


## -remarks



The <b>WDF_INTERRUPT_CONFIG</b> structure is used as input to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>. 

To initialize a <b>WDF_INTERRUPT_CONFIG</b> structure, your driver must first call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdf_interrupt_config_init">WDF_INTERRUPT_CONFIG_INIT</a> and then fill in structure members that <b>WDF_INTERRUPT_CONFIG_INIT</b> does not initialize.

If <b>AutomaticSerialization</b> is TRUE, the following rules apply:

<ul>
<li>If the execution level of the interrupt's parent object is <b>WdfExecutionLevelPassive</b>, the driver can supply <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a>, but should not supply <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> in this configuration structure.</li>
<li>If  the execution level of the interrupt's parent object is <b>WdfExecutionLevelDispatch</b>, the driver can supply <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>, but should not supply <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a> in this configuration structure. In this second case, the interrupt object itself can still be passive.</li>
</ul>
The driver can use this structure's <b>WaitLock</b> member to provide its own interrupt lock for <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a>. If the driver sets <b>PassiveHandling</b> to TRUE but not does provide a <b>WaitLock</b>, the framework creates an interrupt lock internally. The framework acquires the passive-level interrupt lock before calling the following callback functions:<dl>
<dd>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable">EvtInterruptEnable</a>
</dd>
<dd>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable">EvtInterruptDisable</a>
</dd>
<dd>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize">EvtInterruptSynchronize</a>
</dd>
<dd>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a>
</dd>
</dl>


For more information about <b>AutomaticSerialization</b> and synchronizing driver callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.

By default, KMDF function drivers are power pageable. A driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowernotpageable">WdfDeviceInitSetPowerNotPageable</a> 
to specify that it is non-power pageable.

In KMDF versions earlier than 1.11, the framework always disconnects interrupts of power pageable drivers when the device transitions into a low-power (Dx) state. Starting in KMDF version 1.11, you can change this behavior by setting the <b>ReportInactiveOnPowerDown</b> member of this structure.  For non-power pageable drivers, interrupts remain connected when Dx state transitions occur, regardless of the value set in <b>ReportInactiveOnPowerDown</b>.

If a UMDF driver sets <b>ReportInactiveOnPowerDown</b>, the value is ignored.

For more information about handling interrupts in framework-based drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.

The driver can use this structure's <b>CanWakeDevice</b> member to create an interrupt that can be used to bring the device from a low-power Dx state back to D0. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback routine  is scheduled to run at IRQL = PASSIVE_LEVEL after the device enters D0.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-an-interrupt-to-wake-a-device">Using an Interrupt to Wake a Device</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_disable">EvtInterruptDisable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_enable">EvtInterruptEnable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdf_interrupt_config_init">WDF_INTERRUPT_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowernotpageable">WdfDeviceInitSetPowerNotPageable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptqueuedpcforisr">WdfInterruptQueueDpcForIsr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfspinlockcreate">WdfSpinLockCreate</a>
 

 

