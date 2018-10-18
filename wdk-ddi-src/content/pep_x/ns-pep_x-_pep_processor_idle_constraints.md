---
UID: NS:pep_x._PEP_PROCESSOR_IDLE_CONSTRAINTS
title: "_PEP_PROCESSOR_IDLE_CONSTRAINTS"
author: windows-driver-content
description: The PEP_PROCESSOR_IDLE_CONSTRAINTS structure specifies a set of constraints that the PEP uses to select a processor idle state.
old-location: kernel\pep_processor_idle_constraints.htm
tech.root: kernel
ms.assetid: E2939DFA-52EC-4AA7-ACC6-63D60603A24D
ms.date: 4/30/2018
ms.keywords: "*PPEP_PROCESSOR_IDLE_CONSTRAINTS, PEP_PROCESSOR_IDLE_CONSTRAINTS, PEP_PROCESSOR_IDLE_CONSTRAINTS structure [Kernel-Mode Driver Architecture], PPEP_PROCESSOR_IDLE_CONSTRAINTS, PPEP_PROCESSOR_IDLE_CONSTRAINTS structure pointer [Kernel-Mode Driver Architecture], _PEP_PROCESSOR_IDLE_CONSTRAINTS, kernel.pep_processor_idle_constraints, pep_x/PEP_PROCESSOR_IDLE_CONSTRAINTS, pep_x/PPEP_PROCESSOR_IDLE_CONSTRAINTS"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pep_x.h
api_name:
-	PEP_PROCESSOR_IDLE_CONSTRAINTS
product:
- Windows
targetos: Windows
req.typenames: PEP_PROCESSOR_IDLE_CONSTRAINTS, *PPEP_PROCESSOR_IDLE_CONSTRAINTS
---

# _PEP_PROCESSOR_IDLE_CONSTRAINTS structure


## -description


The <b>PEP_PROCESSOR_IDLE_CONSTRAINTS</b> structure specifies a set of constraints that the PEP uses to select a processor idle state.


## -struct-fields




### -field IdleDuration

The length of time, in 100-nanosecond units, for which the processor is expected to stay in the selected idle state. This is the operating system's current best estimate and might vary over time without further notification.


### -field Interruptible

Whether the processor must be able to respond to interrupts in the selected idle state. A value of TRUE indicates that the processor must be interruptible in this idle state. A value of FALSE indicates that the processor is not required to be interruptible in this idle state.


### -field Type

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt629126">PEP_PROCESSOR_IDLE_TYPE</a> enumeration value that indicates whether these idle constraints apply to just the current processor (<b>Type</b> = <b>PepIdleTypeProcessor</b>) or to all processors in the hardware platform (<b>Type</b> = <b>PepIdleTypePlatform</b>).


## -remarks



The <b>Constraints</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt629120">PEP_PPM_IDLE_SELECT</a> structure is a pointer to a <b>PEP_PROCESSOR_IDLE_CONSTRAINTS</b> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt629120">PEP_PPM_IDLE_SELECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629126">PEP_PROCESSOR_IDLE_TYPE</a>
 

 

