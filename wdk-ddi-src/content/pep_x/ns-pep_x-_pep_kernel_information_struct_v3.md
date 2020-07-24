---
UID: NS:pep_x._PEP_KERNEL_INFORMATION_STRUCT_V3
title: _PEP_KERNEL_INFORMATION_STRUCT_V3 (pep_x.h)
description: The PEP_KERNEL_INFORMATION structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows power management framework (PoFx).
old-location: kernel\pep_kernel_information.htm
tech.root: kernel
ms.assetid: 4FBBEF08-3BDA-43B2-A05B-B6BFC2787FC6
ms.date: 04/30/2018
keywords: ["_PEP_KERNEL_INFORMATION_STRUCT_V3 structure"]
ms.keywords: "*PPEP_KERNEL_INFORMATION, *PPEP_KERNEL_INFORMATION_STRUCT_V3, PEP_KERNEL_INFORMATION, PEP_KERNEL_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PEP_KERNEL_INFORMATION_STRUCT_V1, PEP_KERNEL_INFORMATION_STRUCT_V1 structure [Kernel-Mode Driver Architecture], PEP_KERNEL_INFORMATION_STRUCT_V3, PPEP_KERNEL_INFORMATION_STRUCT_V1, PPEP_KERNEL_INFORMATION_STRUCT_V1 structure pointer [Kernel-Mode Driver Architecture], _PEP_KERNEL_INFORMATION_STRUCT_V3, kernel.pep_kernel_information, pep_x/PEP_KERNEL_INFORMATION, pep_x/PEP_KERNEL_INFORMATION_STRUCT_V1, pep_x/PPEP_KERNEL_INFORMATION_STRUCT_V1"
f1_keywords:
 - "pep_x/PEP_KERNEL_INFORMATION_STRUCT_V1"
 - "PEP_KERNEL_INFORMATION_STRUCT_V1"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pep_x.h
api_name:
- PEP_KERNEL_INFORMATION_STRUCT_V1
targetos: Windows
req.typenames: PEP_KERNEL_INFORMATION_STRUCT_V3, *PPEP_KERNEL_INFORMATION_STRUCT_V3
---

# _PEP_KERNEL_INFORMATION_STRUCT_V3 structure


## -description


The <b>PEP_KERNEL_INFORMATION</b> structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx).


## -struct-fields




### -field Version

The current version number for this structure. Set this member to PEP_KERNEL_INFORMATION_VERSION.


### -field Size

The size, in bytes, of this structure. Set this member to <b>sizeof</b>(<b>PEP_KERNEL_INFORMATION</b>).


### -field Plugin

The handle assigned to the PEP's registration with PoFx. PoFx sets the value of this member. The PEP uses this handle in calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestworker">RequestWorker</a> routine.


### -field RequestWorker

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestworker">RequestWorker</a> routine. PoFx sets the value of this member. The <b>RequestWorker</b> routine is implemented by PoFx. The PEP calls this routine to request the use of a worker thread from the operating system.


### -field EnumerateUnmaskedInterrupts

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackenumerateunmaskedinterrupts">EnumerateUnmaskedInterrupts</a> routine. PoFx sets the value of this member. The <b>EnumerateUnmaskedInterrupts</b> routine is implemented by PoFx. The PEP calls this routine to request information about the unmasked interrupts.


### -field ProcessorHalt

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackprocessorhalt">ProcessorHalt</a> routine. PoFx sets the value of this member. The <b>ProcessorHalt</b> routine is implemented by PoFx. The PEP calls this routine to prepare the current processor to enter the halted state.


### -field RequestInterrupt

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestinterrupt">RequestInterrupt</a> routine. PoFx sets the value of this member. The <b>RequestInterrupt</b> routine is implemented by PoFx. The PEP calls this routine to replay an edge-triggered interrupt that might have been lost after the hardware platform entered a low-power system state.


### -field TransitionCriticalResource

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackcriticalresource">TransitionCriticalResource</a> routine. PoFx sets the value of this member. The <b>TransitionCriticalResource</b> routine is implemented by PoFx. The PEP calls this routine to transition critical system resources to the idle condition.


#### - ProcessorIdleVeto

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackprocessoridleveto">ProcessorIdleVeto</a> routine. PoFx sets the value of this member. The <b>ProcessorIdleVeto</b> routine is implemented by PoFx. The PEP calls this routine to increment or decrement the veto count for a pending transition to a processor idle state.


#### - PlatformIdleVeto

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackplatformidleveto">PlatformIdleVeto</a> routine. PoFx sets the value of this member. The <b>PlatformIdleVeto</b> routine is implemented by PoFx. The PEP calls this routine to increment or decrement the veto count for a pending transition to a platform idle state.


#### - UpdateProcessorIdleState

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackupdateprocessoridlestate">UpdateProcessorIdleState</a> routine. PoFx sets the value of this member. The <b>UpdateProcessorIdleState</b> routine is implemented by PoFx. The PEP calls this routine to update the properties of the specified processor idle state.


#### - UpdatePlatformIdleState

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackupdateplatformidlestate">UpdatePlatformIdleState</a> routine. PoFx sets the value of this member. The <b>UpdatePlatformIdleState</b> routine is implemented by PoFx. The PEP calls this routine to update the properties of the specified platform idle state.


#### - RequestCommon

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestcommon">RequestCommon</a> routine. PoFx sets the value of this member. The <b>RequestCommon</b> routine is implemented by PoFx. The PEP calls this routine to perform a processing operation that is specified by a request ID.


#### - CompleteWork

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt186629">CompleteWork</a> routine. PoFx sets the value of this member. The <b>CompleteWork</b> routine is implemented by PoFx. The PEP calls this routine to notify PoFx that the PEP has completed a work item.


## -remarks



The <b>KernelInformation</b> parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterplugin">PoFxRegisterPlugin</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex">PoFxRegisterPluginEx</a> routine is a pointer to a <b>PEP_KERNEL_INFORMATION</b> structure. The PEP allocates this structure and sets the values of the <b>Version</b> and <b>Size</b> members of this structure before calling <b>PoFxRegisterPlugin</b> or <b>PoFxRegisterPluginEx</b>. During the call to this routine, PoFx fills in the remaining members of the structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186629">CompleteWork</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackenumerateunmaskedinterrupts">EnumerateUnmaskedInterrupts</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackplatformidleveto">PlatformIdleVeto</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterplugin">PoFxRegisterPlugin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex">PoFxRegisterPluginEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackprocessorhalt">ProcessorHalt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackprocessoridleveto">ProcessorIdleVeto</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestcommon">RequestCommon</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestinterrupt">RequestInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackrequestworker">RequestWorker</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackcriticalresource">TransitionCriticalResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackupdateplatformidlestate">UpdatePlatformIdleState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackupdateprocessoridlestate">UpdateProcessorIdleState</a>
 

 

