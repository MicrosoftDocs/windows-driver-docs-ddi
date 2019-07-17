---
UID: NF:wdm.IoConnectInterrupt
title: IoConnectInterrupt function (wdm.h)
description: The IoConnectInterrupt routine registers a device driver's InterruptService routine (ISR), so that it will be called when a device interrupts on any of a specified set of processors.
old-location: kernel\ioconnectinterrupt.htm
tech.root: kernel
ms.assetid: a0f9a339-f548-47a2-92ab-ccd341592384
ms.date: 04/30/2018
ms.keywords: IoConnectInterrupt, IoConnectInterrupt routine [Kernel-Mode Driver Architecture], k104_efa094e0-ac29-491b-803a-8470ed39c915.xml, kernel.ioconnectinterrupt, wdm/IoConnectInterrupt
ms.topic: function
f1_keywords:
 - "wdm/IoConnectInterrupt"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive2, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoConnectInterrupt
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoConnectInterrupt function


## -description


The <b>IoConnectInterrupt</b> routine registers a device driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kservice_routine">InterruptService</a> routine (ISR), so that it will be called when a device interrupts on any of a specified set of processors.


## -parameters




### -param InterruptObject [out]

Pointer to the address of driver-supplied storage for a pointer to a set of interrupt objects. This pointer must be passed in subsequent calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesynchronizeexecution">KeSynchronizeExecution</a>.


### -param ServiceRoutine [in]

Pointer to the entry point for the driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kservice_routine">InterruptService</a> routine.


### -param ServiceContext [in, optional]

Pointer to the driver-determined context that will be supplied to the <i>InterruptService</i> routine when it is called. The <i>ServiceContext</i> area must be in resident memory: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the device driver. See <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/providing-isr-context-information">Providing ISR Context Information</a> for details.


### -param SpinLock [in, optional]

Pointer to an initialized spin lock, for which the driver supplies the storage, that will be used to synchronize access to driver-determined data shared by other driver routines. This parameter is required if the ISR handles more than one vector or if the driver has more than one ISR. Otherwise, the driver need not allocate storage for an interrupt spin lock and the input pointer is <b>NULL</b>.


### -param Vector [in]

Specifies the interrupt vector passed in the interrupt resource at the <b>u.Interrupt.Vector</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.


### -param Irql [in]

Specifies the DIRQL passed in the interrupt resource at the <b>u.Interrupt.Level</b> member of <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b>.


### -param SynchronizeIrql [in]

Specifies the DIRQL at which the ISR will run. If the ISR handles more than one interrupt vector or the driver has more than one ISR, this value must be the highest of the <i>Irql</i> values passed at <b>u.Interrupt.Level</b> in each interrupt resource. Otherwise, the <i>Irql</i> and <i>SynchronizeIrql</i> values are identical.


### -param InterruptMode [in]

Specifies whether the device interrupt is <b>LevelSensitive</b> or <b>Latched</b>.


### -param ShareVector [in]

Specifies whether the interrupt vector is sharable. 


### -param ProcessorEnableMask [in]

Specifies a [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity) value representing the set of processors on which device interrupts can occur in this platform. This value is passed in the interrupt resource at <b>u.Interrupt.Affinity</b>. 


### -param FloatingSave [in]

Specifies whether to save the floating-point stack when the driver's device interrupts. For x86-based and Itanium-based platforms, this value must be set to <b>FALSE</b>. For more information about saving floating-point and MMX state, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-floating-point-or-mmx-in-a-wdm-driver">Using Floating Point or MMX in a WDM Driver</a>. 


## -returns



<b>IoConnectInterrupt</b> can return one of the following NTSTATUS values:




## -remarks



New drivers should use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a> routine, which is easier to use. Drivers for devices that support message-signaled interrupts (MSI) must use <b>IoConnectInterruptEx</b>.

A PnP driver should call <b>IoConnectInterrupt</b> as part of device start-up, before it completes the PnP <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> request.

When a driver receives an <b>IRP_MN_START_DEVICE</b> request, the driver receives raw and translated hardware resources in the <b>Parameters.StartDevice.AllocatedResources</b> and  <b>Parameters.StartDevice.AllocatedResourcesTranslated</b> members of the IRP's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structure, respectively. To connect its interrupt, the driver uses the resources at <b>AllocatedResourcesTranslated.List.PartialResourceList.PartialDescriptors[]</b>. The driver must scan the array of partial descriptors for resources of type <b>CmResourceTypeInterrupt</b>.

If the driver supplies the storage for the <i>SpinLock</i>, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a> before passing its interrupt spin lock to <b>IoConnectInterrupt</b>.

On return from a successful call to <b>IoConnectInterrupt</b>, the caller's ISR can be called if interrupts are enabled on the driver's device or if <i>ShareVector</i> was set to <b>TRUE</b>. Drivers must not enable interrupts until after <b>IoConnectInterrupt</b> returns.



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iodisconnectinterrupt">IoDisconnectInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesynchronizeexecution">KeSynchronizeExecution</a>
 

 

