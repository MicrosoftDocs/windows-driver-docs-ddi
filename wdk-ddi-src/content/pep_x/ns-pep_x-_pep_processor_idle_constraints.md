---
UID: NS:pep_x._PEP_PROCESSOR_IDLE_CONSTRAINTS
title: "_PEP_PROCESSOR_IDLE_CONSTRAINTS"
author: windows-driver-content
description: The PEP_PROCESSOR_IDLE_CONSTRAINTS structure specifies a set of constraints that the PEP uses to select a processor idle state.
old-location: kernel\pep_processor_idle_constraints.htm
old-project: kernel
ms.assetid: E2939DFA-52EC-4AA7-ACC6-63D60603A24D
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PEP_PROCESSOR_IDLE_CONSTRAINTS, kernel.pep_processor_idle_constraints, *PPEP_PROCESSOR_IDLE_CONSTRAINTS, PPEP_PROCESSOR_IDLE_CONSTRAINTS, PEP_PROCESSOR_IDLE_CONSTRAINTS structure [Kernel-Mode Driver Architecture], _PEP_PROCESSOR_IDLE_CONSTRAINTS, PPEP_PROCESSOR_IDLE_CONSTRAINTS structure pointer [Kernel-Mode Driver Architecture], pep_x/PEP_PROCESSOR_IDLE_CONSTRAINTS, pep_x/PPEP_PROCESSOR_IDLE_CONSTRAINTS
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
-	PEP_PROCESSOR_IDLE_CONSTRAINTS
product: Windows
targetos: Windows
req.typenames: "*PPEP_PROCESSOR_IDLE_CONSTRAINTS, PEP_PROCESSOR_IDLE_CONSTRAINTS"
---

# _PEP_PROCESSOR_IDLE_CONSTRAINTS structure


## -description


The <b>PEP_PROCESSOR_IDLE_CONSTRAINTS</b> structure specifies a set of constraints that the PEP uses to select a processor idle state.


## -syntax


````
typedef struct _PEP_PROCESSOR_IDLE_CONSTRAINTS {
  ULONGLONG               IdleDuration;
  BOOLEAN                 Interruptible;
  PEP_PROCESSOR_IDLE_TYPE Type;
} PEP_PROCESSOR_IDLE_CONSTRAINTS, *PPEP_PROCESSOR_IDLE_CONSTRAINTS;
````


## -struct-fields




### -field IdleDuration

The length of time, in 100-nanosecond units, for which the processor is expected to stay in the selected idle state. This is the operating system's current best estimate and might vary over time without further notification.


### -field Interruptible

Whether the processor must be able to respond to interrupts in the selected idle state. A value of TRUE indicates that the processor must be interruptible in this idle state. A value of FALSE indicates that the processor is not required to be interruptible in this idle state.


### -field Type

A <a href="..\pep_x\ne-pep_x-ppep_processor_idle_type.md">PEP_PROCESSOR_IDLE_TYPE</a> enumeration value that indicates whether these idle constraints apply to just the current processor (<b>Type</b> = <b>PepIdleTypeProcessor</b>) or to all processors in the hardware platform (<b>Type</b> = <b>PepIdleTypePlatform</b>).


## -remarks



The <b>Constraints</b> member of the <a href="..\pep_x\ns-pep_x-_pep_ppm_idle_select.md">PEP_PPM_IDLE_SELECT</a> structure is a pointer to a <b>PEP_PROCESSOR_IDLE_CONSTRAINTS</b> structure.




## -see-also

<a href="..\pep_x\ne-pep_x-ppep_processor_idle_type.md">PEP_PROCESSOR_IDLE_TYPE</a>



<a href="..\pep_x\ns-pep_x-_pep_ppm_idle_select.md">PEP_PPM_IDLE_SELECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PROCESSOR_IDLE_CONSTRAINTS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

