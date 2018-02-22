---
UID: NS:pep_x._PEP_PPM_IDLE_SELECT
title: "_PEP_PPM_IDLE_SELECT"
author: windows-driver-content
description: The PEP_PPM_IDLE_SELECT structure describes the most energy-efficient idle state that the processor can enter and still satisfy the constraints specified by the operating system.
old-location: kernel\pep_ppm_idle_select.htm
old-project: kernel
ms.assetid: 4783CB44-3A55-4C7C-8EA2-1A72317CC955
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PPEP_PPM_IDLE_SELECT, *PPEP_PPM_IDLE_SELECT, kernel.pep_ppm_idle_select, pep_x/PPEP_PPM_IDLE_SELECT, PEP_PPM_IDLE_SELECT, pep_x/PEP_PPM_IDLE_SELECT, PEP_PPM_IDLE_SELECT structure [Kernel-Mode Driver Architecture], PPEP_PPM_IDLE_SELECT structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_IDLE_SELECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pepfx.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pep_x.h
apiname:
-	PEP_PPM_IDLE_SELECT
product: Windows
targetos: Windows
req.typenames: "*PPEP_PPM_IDLE_SELECT, PEP_PPM_IDLE_SELECT"
---

# _PEP_PPM_IDLE_SELECT structure


## -description


The <b>PEP_PPM_IDLE_SELECT</b> structure describes the most energy-efficient idle state that the processor can enter and still satisfy the constraints specified by the operating system.


## -syntax


````
typedef struct _PEP_PPM_IDLE_SELECT {
  PPEP_PROCESSOR_IDLE_CONSTRAINTS Constraints;
  BOOLEAN                         AbortTransition;
  ULONG                           IdleStateIndex;
  ULONG                           DependencyArrayUsed;
  ULONG                           DependencyArrayCount;
  PPEP_PROCESSOR_IDLE_DEPENDENCY  DependencyArray;
  ULONG                           PlatformIdleStateIndex;
} PEP_PPM_IDLE_SELECT, *PPEP_PPM_IDLE_SELECT;
````


## -struct-fields




### -field Constraints

[in] A pointer to a <a href="..\pep_x\ns-pep_x-_pep_processor_idle_constraints.md">PEP_PROCESSOR_IDLE_CONSTRAINTS</a> structure that specifies the constraints that the selected processor idle state must satisfy. The operating system sets the values in this structure. The platform extension plug-in (PEP) must select a processor idle state that satisfies these constraints.


### -field AbortTransition

[out] Whether to cancel the pending transition to a processor idle state. Set this member to TRUE if the PEP requires the operating system to cancel the pending transition, and to FALSE otherwise. The PEP selects this option if it wants to queue work and have the Windows kernel process this work before the processor enters idle.


### -field IdleStateIndex

[out] The index that identifies the idle state that the processor is to enter. This member is ignored if <b>AbortTransition</b> = TRUE. If the processor supports N idle states, idle state indexes range from 0 to N–1. The PEP supplied the number of supported idle states for this processor in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629121">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a> notification.


### -field DependencyArrayUsed

[out] The number of array elements that the PEP has actually written to the output buffer pointed to the <b>DependencyArray</b> member.


### -field DependencyArrayCount

[in] The maximum number of elements in the array pointed to by the <b>DependencyArray</b> member. The <b>DependencyArrayCount</b> member value is equal to the <b>MaximumCoordinatedProcessors</b> value that the PEP previously supplied in response to the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629121">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a> notification.


### -field DependencyArray

[in] A pointer to an output buffer to which the PEP writes an array of <a href="..\pepfx\ns-pepfx-_pep_processor_idle_dependency.md">PEP_PROCESSOR_IDLE_DEPENDENCY</a> structures. The elements of this array specify processor idle dependencies or wake dependencies that must be met for this idle transition to succeed. The PEP sets the <b>DependencyArrayUsed</b> member to the actual number of array elements that the PEP writes to the buffer. The output buffer is allocated by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) and is guaranteed to be large enough to contain the number of array elements specified by the <b>DependencyArrayCount</b> member.


### -field PlatformIdleStateIndex

[out] The index of the platform idle state that the platform is to enter when the processor enters the selected processor idle state. The PEP should set this member only if the platform enters an idle state at the same time as the processor. This member is ignored if <b>AbortTransition</b> is TRUE.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629120">PEP_NOTIFY_PPM_IDLE_SELECT</a> notification. The <b>Constraints</b>, <b>DependencyArrayCount</b>, and <b>DependencyArray</b> members of the structure contain input values supplied by PoFx when this notification is sent. The remaining members contain output values that the PEP writes to the structure in response to the notification.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629120">PEP_NOTIFY_PPM_IDLE_SELECT</a>



<a href="..\pepfx\ns-pepfx-_pep_processor_idle_dependency.md">PEP_PROCESSOR_IDLE_DEPENDENCY</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629121">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a>



<a href="..\pep_x\ns-pep_x-_pep_processor_idle_constraints.md">PEP_PROCESSOR_IDLE_CONSTRAINTS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_IDLE_SELECT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

