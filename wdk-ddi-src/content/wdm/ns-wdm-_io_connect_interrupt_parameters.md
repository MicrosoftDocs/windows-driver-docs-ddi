---
UID: NS:wdm._IO_CONNECT_INTERRUPT_PARAMETERS
title: "_IO_CONNECT_INTERRUPT_PARAMETERS"
author: windows-driver-content
description: The IO_CONNECT_INTERRUPT_PARAMETERS structure contains the parameters that a driver supplies to the IoConnectInterruptEx routine to register an interrupt service routine (ISR).
old-location: kernel\io_connect_interrupt_parameters.htm
old-project: kernel
ms.assetid: 450c2e2b-56fa-4896-ba81-0f84f7e3051d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PIO_CONNECT_INTERRUPT_PARAMETERS, wdm/IO_CONNECT_INTERRUPT_PARAMETERS, IO_CONNECT_INTERRUPT_PARAMETERS, IO_CONNECT_INTERRUPT_PARAMETERS structure [Kernel-Mode Driver Architecture], kernel.io_connect_interrupt_parameters, _IO_CONNECT_INTERRUPT_PARAMETERS, kstruct_b_c3854cf4-b084-42f4-9f3b-92a96fc741c1.xml, wdm/PIO_CONNECT_INTERRUPT_PARAMETERS, PIO_CONNECT_INTERRUPT_PARAMETERS structure pointer [Kernel-Mode Driver Architecture], *PIO_CONNECT_INTERRUPT_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	IO_CONNECT_INTERRUPT_PARAMETERS
product: Windows
targetos: Windows
req.typenames: IO_CONNECT_INTERRUPT_PARAMETERS, *PIO_CONNECT_INTERRUPT_PARAMETERS
req.product: Windows 10 or later.
---

# _IO_CONNECT_INTERRUPT_PARAMETERS structure


## -description


The <b>IO_CONNECT_INTERRUPT_PARAMETERS</b> structure contains the parameters that a driver supplies to the <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> routine to register an interrupt service routine (ISR).


## -syntax


````
typedef struct _IO_CONNECT_INTERRUPT_PARAMETERS {
  ULONG Version;
  union {
    struct {
      PDEVICE_OBJECT    PhysicalDeviceObject;
      PKINTERRUPT       *InterruptObject;
      PKSERVICE_ROUTINE ServiceRoutine;
      PVOID             ServiceContext;
      PKSPIN_LOCK       SpinLock;
      KIRQL             SynchronizeIrql;
      BOOLEAN           FloatingSave;
      BOOLEAN           ShareVector;
      ULONG             Vector;
      KIRQL             Irql;
      KINTERRUPT_MODE   InterruptMode;
      KAFFINITY         ProcessorEnableMask;
      USHORT            Group;
    } FullySpecified;
    struct {
      PDEVICE_OBJECT    PhysicalDeviceObject;
      PKINTERRUPT       *InterruptObject;
      PKSERVICE_ROUTINE ServiceRoutine;
      PVOID             ServiceContext;
      PKSPIN_LOCK       SpinLock;
      KIRQL             SynchronizeIrql;
      BOOLEAN           FloatingSave;
    } LineBased;
    struct {
      PDEVICE_OBJECT            PhysicalDeviceObject;
      union {
        PVOID                      *Generic;
        PIO_INTERRUPT_MESSAGE_INFO *InterruptMessageTable;
        PKINTERRUPT                *InterruptObject;
      } ConnectionContext;
      PKMESSAGE_SERVICE_ROUTINE MessageServiceRoutine;
      PVOID                     ServiceContext;
      PKSPIN_LOCK               SpinLock;
      KIRQL                     SynchronizeIrql;
      BOOLEAN                   FloatingSave;
      PKSERVICE_ROUTINE         FallBackServiceRoutine;
    } MessageBased;
  };
} IO_CONNECT_INTERRUPT_PARAMETERS, *PIO_CONNECT_INTERRUPT_PARAMETERS;
````


## -struct-fields




### -field Version

On input, specifies the particular operation to be performed by <b>IoConnectInterruptEx</b>, as follows.

<table>
<tr>
<th>Version value</th>
<th>IoConnectInterruptEx operation</th>
</tr>
<tr>
<td>
CONNECT_FULLY_SPECIFIED

</td>
<td>
Connects to a specific interrupt using information provided by the Plug and Play (PnP) manager. Use the <b>FullySpecified</b> member to provide the additional parameters of the operation.

</td>
</tr>
<tr>
<td>
CONNECT_LINE_BASED

</td>
<td>
Registers an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine for the device's line-based interrupts. Use the <b>LineBased</b> member to provide the additional parameters of the operation.

</td>
</tr>
<tr>
<td>
CONNECT_MESSAGE_BASED

</td>
<td>
Registers an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547940">InterruptMessageService</a> routine for the device's message-signaled interrupts. The caller can also specify a fallback <i>InterruptService</i> routine if the device only has line-based interrupts. Use the <b>MessageBased</b> member to provide the additional parameters of the operation.

</td>
</tr>
</table>
 

On return, the routine provides information about the operation, as follows.

<table>
<tr>
<th>Version value</th>
<th>Description</th>
</tr>
<tr>
<td>
CONNECT_FULLY_SPECIFIED

</td>
<td>
The caller specified CONNECT_LINE_BASED or CONNECT_MESSAGE_BASED for <b>Version</b> on a platform that does not support it. Retry the operation using CONNECT_FULLY_SPECIFIED.

</td>
</tr>
<tr>
<td>
CONNECT_LINE_BASED

</td>
<td>
The caller specified CONNECT_MESSAGE_BASED and the caller's fallback <i>InterruptService</i> routine was registered.

</td>
</tr>
<tr>
<td>
CONNECT_MESSAGE_BASED

</td>
<td>
The caller specified CONNECT_MESSAGE_BASED and the caller's <i>InterruptMessageService</i> routine was registered.

</td>
</tr>
</table>
 


#### - FullySpecified

Specifies the additional parameters of the operation to be performed by <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> when <b>Version</b> has a value of CONNECT_FULLY_SPECIFIED (or CONNECT_FULLY_SPECIFIED_GROUP if the <b>Group</b> member is used). For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565520">Using the CONNECT_FULLY_SPECIFIED Version of IoConnectInterruptEx</a>.



#### PhysicalDeviceObject

A pointer to the PDO for the device.



#### InterruptObject

A pointer to a location that receives a pointer to the set of interrupt objects for the device.



#### ServiceRoutine

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine to register as the ISR for the device's interrupts.



#### ServiceContext

Specifies the value to be passed as the <i>ServiceContext</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine.



#### SpinLock

Either a pointer to a spin lock to serve as the interrupt spin lock for the set of interrupts, or <b>NULL</b>. If <b>NULL</b>, the system allocates a spin lock to serve as the interrupt spin lock. If non-<b>NULL</b>, you should have initialized the spin lock with <a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>.



#### SynchronizeIrql

Specifies the DIRQL at which the ISR will run. If the ISR handles more than one interrupt vector or the driver has more than one ISR, this value must be the maximum IRQL of the set of interrupts. The IRQL for an interrupt is passed in the <b>CmResourceTypeInterrupt</b> resource at the <b>u.Interrupt.Level</b> member of <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>. Otherwise, the <b>Irql</b> and <b>SynchronizeIrql</b> values are identical.



#### FloatingSave

Specifies if the system saves the processor's floating-point state when the interrupt occurs. If <b>TRUE</b>, the system saves the floating-point state.



#### ShareVector

Specifies whether the interrupt vector is sharable. Line-based PCI interrupts must be sharable. For message-signaled PCI interrupts, driver writers can choose whether their interrupts are sharable, but should choose to make them sharable by default.



#### Vector

Specifies the interrupt vector passed in the <b>CmResourceTypeInterrupt</b> resource at the <b>u.Interrupt.Vector</b> member of <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b>.



#### Irql

Specifies the DIRQL passed in the <b>CmResourceTypeInterrupt</b> resource at the <b>u.Interrupt.Level</b> member of <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>. Starting with Windows 8, a driver can register an ISR that runs at passive level by setting <b>Irql</b> and <b>SynchronizeIrql</b> to PASSIVE_LEVEL, and setting <b>SpinLock</b> to <b>NULL</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh698277">Using Passive-Level Interrupt Service Routines</a>.



#### InterruptMode

Specifies a <a href="..\wudfwdm\ne-wudfwdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a> that determines whether the interrupt is level-triggered (<b>InterruptMode</b> = <b>LevelSensitive</b>) or edge-triggered (<b>InterruptMode</b> = <b>Latched</b>). For shared interrupt lines from a PCI bus, specify <b>LevelSensitive</b>. For PCI message-signaled interrupts, specify <b>Latched</b>.



#### ProcessorEnableMask

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a> mask that represents the set of processors on which the device's interrupts can occur. This value is passed in the <b>CmResourceTypeInterrupt</b> resource at the <b>u.Interrupt.Affinity</b> member of <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b>.



#### Group

Specifies a group number that identifies the processor group to which the interrupt is to be delivered. Typically, a driver receives its group number as part of the translated resources that are included in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request. Starting with Windows 7, the <b>Group</b> member is used if the <b>Version</b> member of the <b>IO_CONNECT_INTERRUPT_PARAMETERS</b> structure is set to CONNECT_FULLY_SPECIFIED_GROUP. The <b>Group</b> member is ignored if <b>Version</b> is set to CONNECT_FULLY_SPECIFIED, in which case the group number for delivery of the interrupt is always 0.


#### - LineBased

Specifies the additional parameters of the operation to be performed by <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> when <b>Version</b> has a value of CONNECT_LINE_BASED. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565525">Using the CONNECT_LINE_BASED Version of IoConnectInterruptEx</a>.



#### PhysicalDeviceObject

A pointer to the physical device object (PDO) of the device.



#### InterruptObject

A pointer to a location that receives a pointer to the set of interrupt objects for the device.



#### ServiceRoutine

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine to register as the ISR for the device's interrupts.



#### ServiceContext

Specifies the value to be passed as the <i>ServiceContext</i> parameter of the <i>InterruptService</i> routine.



#### SpinLock

Either a pointer to a spin lock to serve as the interrupt spin lock for the set of interrupts, or <b>NULL</b>. If <b>NULL</b>, the system allocates a spin lock to serve as the interrupt spin lock. If non-<b>NULL</b>, you should have initialized the spin lock with <a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>.



#### SynchronizeIrql

Specifies the minimum device IRQL (DIRQL) at which the ISR runs. The system uses this value only if it is greater than the maximum IRQL of the set of interrupts; otherwise, the system uses the maximum IRQL. Drivers almost always specify PASSIVE_LEVEL for <b>SynchronizeIrql</b>. (A driver should specify a value other than PASSIVE_LEVEL only if the ISR must run above a certain IRQL.) Starting with Windows 8, a set of line-based interrupt resources that are assigned to a device can share an ISR that runs at IRQL = PASSIVE_LEVEL. If <b>SynchronizeIrql</b> = PASSIVE_LEVEL, and the maximum IRQL of this set of interrupts is PASSIVE_LEVEL, the <i>InterruptService</i> routine is called at PASSIVE_LEVEL. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh698277">Using Passive-Level Interrupt Service Routines</a>.



#### FloatingSave

Specifies if the system saves the processor's floating-point state when the interrupt occurs. If <b>TRUE</b>, the system saves floating-point state. For x86-based and Itanium-based platforms, this value must be set to <b>FALSE</b>. For more information about saving floating-point and MMX state, see <a href="https://msdn.microsoft.com/73414084-4054-466a-b64c-5c81b224be92">Using Floating Point or MMX in a WDM Driver</a>.


#### - MessageBased

Specifies the additional parameters of the operation to be performed by <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> when <b>Version</b> has a value of CONNECT_MESSAGE_BASED. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565530">Using the CONNECT_MESSAGE_BASED Version of IoConnectInterruptEx</a>.



#### PhysicalDeviceObject

A pointer to the PDO of the device.



#### ConnectionContext

A pointer to a location that receives a pointer to the connection context. If on return <b>Version</b> has a value of CONNECT_LINE_BASED, the routine provides a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> structure. If on return <b>Version</b> has a value of CONNECT_MESSAGE_BASED, the routine provides a pointer to an <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a> structure. 

To minimize casting, <b>ConnectionContext</b> is defined as a union. Use <b>ConnectionContext.Generic</b> to treat the location as a PVOID. Use <b>ConnectionContext.InterruptObject</b> and <b>ConnectionContext.InterruptMessageTable</b> to treat the location as a PKINTERRUPT or PIO_INTERRUPT_MESSAGE_INFO variable respectively.



##### Generic

A pointer to a PVOID variable into which the <b>IoConnectInterruptEx</b> routine writes a pointer to the connection context.



##### InterruptMessageTable

A pointer to a PIO_INTERRUPT_MESSAGE_INFO variable into which the <b>IoConnectInterruptEx</b> routine writes a pointer to the connection context.



##### InterruptObject

A pointer to a PKINTERRUPT variable into which the <b>IoConnectInterruptEx</b> routine writes a pointer to the connection context.



#### MessageServiceRoutine

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547940">InterruptMessageService</a> routine to register as the ISR for the device's interrupts.



#### ServiceContext

Specifies the value to be passed as the <i>ServiceContext</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547940">InterruptMessageService</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine for the interrupt. 



#### SpinLock

Either a pointer to a spin lock to serve as the interrupt spin lock for the set of interrupts, or <b>NULL</b>. If <b>NULL</b>, the system allocates a spin lock to serve as the interrupt spin lock. If non-<b>NULL</b>, you should have initialized the spin lock with <a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>.



#### SynchronizeIrql

Specifies the minimum device IRQL (DIRQL) at which the ISR runs. The system only uses this value if it is greater than the maximum IRQL of the set of interrupts; otherwise, the system uses the maximum IRQL. Drivers almost always specify PASSIVE_LEVEL for <b>SynchronizeIrql</b>.



#### FloatingSave

Specifies if the system saves the processor's floating-point state when the interrupt occurs. If <b>TRUE</b>, the system saves floating-point state.



#### FallBackServiceRoutine

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine to use as the ISR for line-based interrupts. If the device has no message-signaled interrupts, but has line-based interrupts, the system registers this routine to handle the line-based interrupts.


## -remarks



The <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> routine takes a single <i>Parameters</i> parameter, which points to an <b>IO_CONNECT_INTERRUPT_PARAMETERS</b> structure that contains all of the parameters of the operation.




## -see-also

<a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_CONNECT_INTERRUPT_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

