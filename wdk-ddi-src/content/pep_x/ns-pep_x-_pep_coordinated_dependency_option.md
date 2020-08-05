---
UID: NS:pep_x._PEP_COORDINATED_DEPENDENCY_OPTION
title: _PEP_COORDINATED_DEPENDENCY_OPTION (pep_x.h)
description: The PEP_COORIDNATED_DEPENDENCY_OPTION structure describes a coordinated idle state's dependency to the OS.
old-location: kernel\pep_coordinated_dependency_option.htm
tech.root: kernel
ms.assetid: DE95A3E9-3542-49EE-AA62-3430A6B2D7C7
ms.date: 04/30/2018
keywords: ["PEP_COORDINATED_DEPENDENCY_OPTION structure"]
ms.keywords: "*PPEP_COORDINATED_DEPENDENCY_OPTION, PEP_COORDINATED_DEPENDENCY_OPTION, PEP_COORDINATED_DEPENDENCY_OPTION structure [Kernel-Mode Driver Architecture], PPEP_COORDINATED_DEPENDENCY_OPTION, PPEP_COORDINATED_DEPENDENCY_OPTION structure pointer [Kernel-Mode Driver Architecture], _PEP_COORDINATED_DEPENDENCY_OPTION, kernel.pep_coordinated_dependency_option, pepfx/PEP_COORDINATED_DEPENDENCY_OPTION, pepfx/PPEP_COORDINATED_DEPENDENCY_OPTION"
f1_keywords:
 - "pep_x/PEP_COORDINATED_DEPENDENCY_OPTION"
 - "PEP_COORDINATED_DEPENDENCY_OPTION"
req.header: pep_x.h
req.include-header: Pep_x.h
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
- pepfx.h
api_name:
- PEP_COORDINATED_DEPENDENCY_OPTION
targetos: Windows
req.typenames: PEP_COORDINATED_DEPENDENCY_OPTION, *PPEP_COORDINATED_DEPENDENCY_OPTION
---

# _PEP_COORDINATED_DEPENDENCY_OPTION structure


## -description


The <b>PEP_COORIDNATED_DEPENDENCY_OPTION</b> structure describes a coordinated idle state's dependency to the OS.


## -struct-fields




### -field ExpectedStateIndex

Supplies the index of the idle state (coordinated idle state or processor idle state) that must have already been entered/be entered by this idle transition.


### -field LooseDependency

When <b> FALSE</b>, the OS must use synchronization to guarantee that the state referred to by this dependency has already been entered.
When <b>TRUE</b>,  the OS may perform best-effort coordination that the target state is entered.
The PEP must set <b>LooseDependency</b> to <b>TRUE</b> if the <b>ExpectedState</b> is a processor state and has the <b>WakesSpuriously</b> flag set.



### -field InitiatingState

Indicates if the OS may simultaneously enter the state referred to by this dependency.
If <b>FALSE</b>, this state is only valid when another processor has previously entered it.



### -field DependentState

Indicates if this state is a valid state for a dependent processor to be in.



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">PEP_NOTIFY_PPM_QUERY_COORDINATED_DEPENDENCY notification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_coordinated_dependency">PEP_PPM_QUERY_COORDINATED_DEPENDENCY</a>
 

 

