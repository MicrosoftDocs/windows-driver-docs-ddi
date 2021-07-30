---
UID: NS:pep_x._PEP_KERNEL_INFORMATION_STRUCT_V3
title: _PEP_KERNEL_INFORMATION_STRUCT_V3 (pep_x.h)
description: Learn how the PEP_KERNEL_INFORMATION_STRUCT_V3 structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows power management framework (PoFx).
old-location: kernel\pep_kernel_information.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["PEP_KERNEL_INFORMATION_STRUCT_V3 structure"]
ms.keywords: "*PPEP_KERNEL_INFORMATION, *PPEP_KERNEL_INFORMATION_STRUCT_V3, PEP_KERNEL_INFORMATION, PEP_KERNEL_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PEP_KERNEL_INFORMATION_STRUCT_V1, PEP_KERNEL_INFORMATION_STRUCT_V1 structure [Kernel-Mode Driver Architecture], PEP_KERNEL_INFORMATION_STRUCT_V3, PPEP_KERNEL_INFORMATION_STRUCT_V1, PPEP_KERNEL_INFORMATION_STRUCT_V1 structure pointer [Kernel-Mode Driver Architecture], _PEP_KERNEL_INFORMATION_STRUCT_V3, kernel.pep_kernel_information, pep_x/PEP_KERNEL_INFORMATION, pep_x/PEP_KERNEL_INFORMATION_STRUCT_V1, pep_x/PPEP_KERNEL_INFORMATION_STRUCT_V1"
req.header: pep_x.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: 
targetos: Windows
req.typenames: PEP_KERNEL_INFORMATION_STRUCT_V3, *PPEP_KERNEL_INFORMATION_STRUCT_V3
f1_keywords:
 - _PEP_KERNEL_INFORMATION_STRUCT_V3
 - pep_x/_PEP_KERNEL_INFORMATION_STRUCT_V3
 - PPEP_KERNEL_INFORMATION_STRUCT_V3
 - pep_x/PPEP_KERNEL_INFORMATION_STRUCT_V3
 - PEP_KERNEL_INFORMATION_STRUCT_V3
 - pep_x/PEP_KERNEL_INFORMATION_STRUCT_V3
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pep_x.h
api_name:
 - _PEP_KERNEL_INFORMATION_STRUCT_V3
 - PPEP_KERNEL_INFORMATION_STRUCT_V3
 - PEP_KERNEL_INFORMATION_STRUCT_V3
---

# _PEP_KERNEL_INFORMATION_STRUCT_V3 structure (pep_x.h)

## -description

The **PEP_KERNEL_INFORMATION** structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows [power management framework](/windows-hardware/drivers/ddi/_kernel/#device-power-management) (PoFx).

## -struct-fields

### -field Version

The current version number for this structure. Set this member to PEP_KERNEL_INFORMATION_VERSION.

### -field Size

The size, in bytes, of this structure. Set this member to **sizeof**(**PEP_KERNEL_INFORMATION**).

### -field Plugin

The handle assigned to the PEP's registration with PoFx. PoFx sets the value of this member. The PEP uses this handle in calls to the [RequestWorker](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestworker) routine.

### -field RequestWorker

A pointer to a [RequestWorker](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestworker) routine. PoFx sets the value of this member. The **RequestWorker** routine is implemented by PoFx. The PEP calls this routine to request the use of a worker thread from the operating system.

### -field EnumerateUnmaskedInterrupts

A pointer to an [EnumerateUnmaskedInterrupts](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackenumerateunmaskedinterrupts) routine. PoFx sets the value of this member. The **EnumerateUnmaskedInterrupts** routine is implemented by PoFx. The PEP calls this routine to request information about the unmasked interrupts.

### -field ProcessorHalt

A pointer to a [ProcessorHalt](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackprocessorhalt) routine. PoFx sets the value of this member. The **ProcessorHalt** routine is implemented by PoFx. The PEP calls this routine to prepare the current processor to enter the halted state.

### -field RequestInterrupt

A pointer to a [RequestInterrupt](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestinterrupt) routine. PoFx sets the value of this member. The **RequestInterrupt** routine is implemented by PoFx. The PEP calls this routine to replay an edge-triggered interrupt that might have been lost after the hardware platform entered a low-power system state.

### -field TransitionCriticalResource

A pointer to a [TransitionCriticalResource](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackcriticalresource) routine. PoFx sets the value of this member. The **TransitionCriticalResource** routine is implemented by PoFx. The PEP calls this routine to transition critical system resources to the idle condition.

#### - ProcessorIdleVeto

A pointer to a [ProcessorIdleVeto](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackprocessoridleveto) routine. PoFx sets the value of this member. The **ProcessorIdleVeto** routine is implemented by PoFx. The PEP calls this routine to increment or decrement the veto count for a pending transition to a processor idle state.

#### - PlatformIdleVeto

A pointer to a [PlatformIdleVeto](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackplatformidleveto) routine. PoFx sets the value of this member. The **PlatformIdleVeto** routine is implemented by PoFx. The PEP calls this routine to increment or decrement the veto count for a pending transition to a platform idle state.

#### - UpdateProcessorIdleState

A pointer to an [UpdateProcessorIdleState](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackupdateprocessoridlestate) routine. PoFx sets the value of this member. The **UpdateProcessorIdleState** routine is implemented by PoFx. The PEP calls this routine to update the properties of the specified processor idle state.

#### - UpdatePlatformIdleState

A pointer to an [UpdatePlatformIdleState](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackupdateplatformidlestate) routine. PoFx sets the value of this member. The **UpdatePlatformIdleState** routine is implemented by PoFx. The PEP calls this routine to update the properties of the specified platform idle state.

#### - RequestCommon

A pointer to an [RequestCommon](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestcommon) routine. PoFx sets the value of this member. The **RequestCommon** routine is implemented by PoFx. The PEP calls this routine to perform a processing operation that is specified by a request ID.

#### - CompleteWork

A pointer to a **CompleteWork** routine. PoFx sets the value of this member. The **CompleteWork** routine is implemented by PoFx. The PEP calls this routine to notify PoFx that the PEP has completed a work item.

## -remarks

The **KernelInformation** parameter to the [PoFxRegisterPlugin](/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterplugin) or [PoFxRegisterPluginEx](/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex) routine is a pointer to a **PEP_KERNEL_INFORMATION** structure. The PEP allocates this structure and sets the values of the **Version** and **Size** members of this structure before calling **PoFxRegisterPlugin** or **PoFxRegisterPluginEx**. During the call to this routine, PoFx fills in the remaining members of the structure.

## -see-also

[EnumerateUnmaskedInterrupts](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackenumerateunmaskedinterrupts)

[PlatformIdleVeto](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackplatformidleveto)

[PoFxRegisterPlugin](/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterplugin)

[PoFxRegisterPluginEx](/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex)

[ProcessorHalt](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackprocessorhalt)

[ProcessorIdleVeto](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackprocessoridleveto)

[RequestCommon](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestcommon)

[RequestInterrupt](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestinterrupt)

[RequestWorker](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestworker)

[TransitionCriticalResource](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackcriticalresource)

[UpdatePlatformIdleState](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackupdateplatformidlestate)

[UpdateProcessorIdleState](/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackupdateprocessoridlestate)
