---
UID: NS:wdfinterrupt._WDF_INTERRUPT_CONFIG
title: "_WDF_INTERRUPT_CONFIG"
author: windows-driver-content
description: The WDF_INTERRUPT_CONFIG structure contains configuration information for a device interrupt.
old-location: wdf\wdf_interrupt_config.htm
old-project: wdf
ms.assetid: 10eb623d-6778-4ccb-8ed4-9926c13dec5a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfinterrupt/PWDF_INTERRUPT_CONFIG, kmdf.wdf_interrupt_config, wdfinterrupt/WDF_INTERRUPT_CONFIG, _WDF_INTERRUPT_CONFIG, PWDF_INTERRUPT_CONFIG, PWDF_INTERRUPT_CONFIG structure pointer, WDF_INTERRUPT_CONFIG, WDF_INTERRUPT_CONFIG structure, DFInterruptObjectRef_545890e4-5222-42e8-8fba-c159a0faa140.xml, *PWDF_INTERRUPT_CONFIG, wdf.wdf_interrupt_config
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfinterrupt.h
apiname:
-	WDF_INTERRUPT_CONFIG
product: Windows
targetos: Windows
req.typenames: "*PWDF_INTERRUPT_CONFIG, WDF_INTERRUPT_CONFIG"
req.product: Windows 10 or later.
---

# _WDF_INTERRUPT_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_INTERRUPT_CONFIG</b> structure contains configuration information for a device interrupt.


## -syntax


````
typedef struct _WDF_INTERRUPT_CONFIG {
  ULONG                           Size;
  WDFSPINLOCK                     SpinLock;
  WDF_TRI_STATE                   ShareVector;
  BOOLEAN                         FloatingSave;
  BOOLEAN                         AutomaticSerialization;
  PFN_WDF_INTERRUPT_ISR           EvtInterruptIsr;
  PFN_WDF_INTERRUPT_DPC           EvtInterruptDpc;
  PFN_WDF_INTERRUPT_ENABLE        EvtInterruptEnable;
  PFN_WDF_INTERRUPT_DISABLE       EvtInterruptDisable;
  PFN_WDF_INTERRUPT_WORKITEM      EvtInterruptWorkItem;
  PCM_PARTIAL_RESOURCE_DESCRIPTOR InterruptRaw;
  PCM_PARTIAL_RESOURCE_DESCRIPTOR InterruptTranslated;
  WDFWAITLOCK                     WaitLock;
  BOOLEAN                         PassiveHandling;
  WDF_TRI_STATE                   ReportInactiveOnPowerDown;
  BOOLEAN                         CanWakeDevice;
} WDF_INTERRUPT_CONFIG, *PWDF_INTERRUPT_CONFIG;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field SpinLock

The handle to a framework spin-lock object, obtained by a previous call to <a href="..\wdfsync\nf-wdfsync-wdfspinlockcreate.md">WdfSpinLockCreate</a>, or <b>NULL</b>. If this parameter is <b>NULL</b>, the framework uses an internal spin-lock object. The framework acquires the spin lock before it calls the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a> event callback function and when the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>. For passive-level interrupt handling, set to NULL.

Starting with UMDF version 2.0, UMDF always uses passive-level interrupt handling. In this case, set this member to NULL.


### -field ShareVector

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value. If this value is <b>WdfTrue</b>, the interrupt vector can be shared. If the value is <b>WdfFalse</b>, the interrupt vector cannot be shared. If the value is <b>WdfDefault</b>, the PnP manager uses the bus driver's value.


### -field FloatingSave

A Boolean value that, if <b>TRUE</b>, indicates that the system will save the processor's floating point and MMX state when the device interrupts. If <b>FALSE</b>, the system does not save the floating point and MMX state. A driver should set this value to <b>TRUE</b> only if its <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function must use floating point or MMX registers. For more information about saving floating point and MMX state, see <a href="https://msdn.microsoft.com/73414084-4054-466a-b64c-5c81b224be92">Using Floating Point or MMX in a WDM Driver</a>.

This member is ignored starting in UMDF version 2.0.


### -field AutomaticSerialization

A Boolean value that, if <b>TRUE</b>, indicates that the framework will synchronize execution of the interrupt object's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>    or <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a> callback function with callback functions from other objects that are underneath the interrupt's parent  object.  For more information, see the following Remarks section.


### -field EvtInterruptIsr

A pointer to the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function. This pointer cannot be <b>NULL</b>.


### -field EvtInterruptDpc

A pointer to the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> callback function, or <b>NULL</b>. The driver can provide <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a> or <i>EvtInterruptDpc</i>, but not both.


### -field EvtInterruptEnable

A pointer to the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a> callback function, or <b>NULL</b>.


### -field EvtInterruptDisable

A pointer to the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a> callback function, or <b>NULL</b>.


### -field EvtInterruptWorkItem

A pointer to the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a> callback function, or <b>NULL</b>. The driver can provide <i>EvtInterruptWorkItem</i> or <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>, but not both. The <b>EvtInterruptWorkItem</b> member is available in version 1.11 and later versions of KMDF.


### -field InterruptRaw

A pointer to the <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/raw-and-translated-resources">raw resources</a> that the system assigned to the interrupt. This member is only used if the interrupt is created in the <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback. The <b>InterruptRaw</b> member is available in version 1.11 and later versions of KMDF.


### -field InterruptTranslated

A pointer to the <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/raw-and-translated-resources">translated resources</a> that the system assigned to the interrupt. This member is only used if the interrupt is created in the <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback. The <b>InterruptTranslated</b> member is available in version 1.11 and later versions of KMDF.


### -field WaitLock

A handle to a framework wait-lock object, obtained by a previous call to <a href="..\wdfsync\nf-wdfsync-wdfwaitlockcreate.md">WdfWaitLockCreate</a>, or <b>NULL</b>. If <b>WaitLock</b> is non-<b>NULL</b>, <b>PassiveHandling</b> must be set to <b>TRUE</b>.  The <b>WaitLock</b> member is available in version 1.11 and later versions of KMDF.  For more information about <b>WaitLock</b>, see  <b>Remarks</b>.


### -field PassiveHandling

Set to <b>FALSE</b> for interrupt handling at the device's IRQL (DIRQL).
Set to <b>TRUE</b> for passive-level interrupt handling.
The <b>PassiveHandling</b> member is available in version 1.11 and later versions of KMDF. Starting in UMDF version 2.0, <a href="..\wdfinterrupt\nf-wdfinterrupt-wdf_interrupt_config_init.md">WDF_INTERRUPT_CONFIG_INIT</a> always sets this member to TRUE.


### -field ReportInactiveOnPowerDown

This member applies to KMDF only.

 A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that applies only if the driver has not called <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowernotpageable.md">WdfDeviceInitSetPowerNotPageable</a>.  This member can have one of the following values:

<b>WdfTrue</b> - KMDF reports the interrupt inactive when the device transitions to a low-power (Dx) state.        In operating systems prior to Windows 8, the framework's behavior matches that described for  <b>WdfFalse</b>.


<div class="alert"><b>Note</b>  If <b>CanWakeDevice</b> is set to <b>TRUE</b> and <b>ReportInactiveOnPowerDown</b> is set to <b>WdfTrue</b>, the framework does not report  the interrupt inactive when the device transitions to a low-power state.</div>
<div> </div>


<b>WdfFalse</b> - KMDF disconnects the interrupt when the device transitions to a low-power (Dx) state.

<b>WdfDefault</b> - On ARM-based platforms, the framework's behavior matches that described for  <b>WdfTrue</b>. On other platforms, the framework's behavior matches that described for  <b>WdfFalse</b>.

The <b>ReportInactiveOnPowerDown</b> member is available in version 1.11 and later versions of KMDF. It is not available in UMDF version 2.0.

For more information about reporting an interrupt inactive, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj158878">Making an ISR Active or Inactive</a>.


### -field CanWakeDevice

A Boolean value that indicates whether the interrupt is used to wake the device from a low-power state.
If <b>FALSE</b>, the interrupt is not used to wake the device. If <b>TRUE</b>, the interrupt is used to wake the device.
The <b>CanWakeDevice</b> member is available starting in KMDF version 1.13 and UMDF version 2.0.


## -remarks



The <b>WDF_INTERRUPT_CONFIG</b> structure is used as input to <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>. 

To initialize a <b>WDF_INTERRUPT_CONFIG</b> structure, your driver must first call <a href="..\wdfinterrupt\nf-wdfinterrupt-wdf_interrupt_config_init.md">WDF_INTERRUPT_CONFIG_INIT</a> and then fill in structure members that <b>WDF_INTERRUPT_CONFIG_INIT</b> does not initialize.

If <b>AutomaticSerialization</b> is TRUE, the following rules apply:

<ul>
<li>If the execution level of the interrupt's parent object is <b>WdfExecutionLevelPassive</b>, the driver can supply <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a>, but should not supply <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> in this configuration structure.</li>
<li>If  the execution level of the interrupt's parent object is <b>WdfExecutionLevelDispatch</b>, the driver can supply <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>, but should not supply <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a> in this configuration structure. In this second case, the interrupt object itself can still be passive.</li>
</ul>
The driver can use this structure's <b>WaitLock</b> member to provide its own interrupt lock for <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a>. If the driver sets <b>PassiveHandling</b> to TRUE but not does provide a <b>WaitLock</b>, the framework creates an interrupt lock internally. The framework acquires the passive-level interrupt lock before calling the following callback functions:<dl>
<dd>
<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a>
</dd>
<dd>
<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a>
</dd>
<dd>
<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a>
</dd>
<dd>
<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a>
</dd>
</dl>


For more information about <b>AutomaticSerialization</b> and synchronizing driver callback functions, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.

By default, KMDF function drivers are power pageable. A driver calls <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowernotpageable.md">WdfDeviceInitSetPowerNotPageable</a> 
to specify that it is non-power pageable.

In KMDF versions earlier than 1.11, the framework always disconnects interrupts of power pageable drivers when the device transitions into a low-power (Dx) state. Starting in KMDF version 1.11, you can change this behavior by setting the <b>ReportInactiveOnPowerDown</b> member of this structure.  For non-power pageable drivers, interrupts remain connected when Dx state transitions occur, regardless of the value set in <b>ReportInactiveOnPowerDown</b>.

If a UMDF driver sets <b>ReportInactiveOnPowerDown</b>, the value is ignored.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.

The driver can use this structure's <b>CanWakeDevice</b> member to create an interrupt that can be used to bring the device from a low-power Dx state back to D0. The driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback routine  is scheduled to run at IRQL = PASSIVE_LEVEL after the device enters D0.

For more information, see <a href="https://msdn.microsoft.com/6A4E62BD-B10F-4F01-B4B4-1FF5086710D4">Using an Interrupt to Wake a Device</a>.




## -see-also

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptqueuedpcforisr.md">WdfInterruptQueueDpcForIsr</a>



<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>



<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a>



<a href="..\wdfsync\nf-wdfsync-wdfspinlockcreate.md">WdfSpinLockCreate</a>



<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a>



<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>



<a href="..\wdfinterrupt\nf-wdfinterrupt-wdf_interrupt_config_init.md">WDF_INTERRUPT_CONFIG_INIT</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowernotpageable.md">WdfDeviceInitSetPowerNotPageable</a>



<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>



<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpageable.md">WdfDeviceInitSetPowerPageable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_CONFIG structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

