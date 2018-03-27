---
UID: NS:pepfx._PEP_COORDINATED_DEPENDENCY_OPTION
title: "_PEP_COORDINATED_DEPENDENCY_OPTION"
author: windows-driver-content
description: The PEP_COORIDNATED_DEPENDENCY_OPTION structure describes a coordinated idle stateâ€™s dependency to the OS.
old-location: kernel\pep_coordinated_dependency_option.htm
old-project: kernel
ms.assetid: DE95A3E9-3542-49EE-AA62-3430A6B2D7C7
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_COORDINATED_DEPENDENCY_OPTION, PEP_COORDINATED_DEPENDENCY_OPTION, PEP_COORDINATED_DEPENDENCY_OPTION structure [Kernel-Mode Driver Architecture], PPEP_COORDINATED_DEPENDENCY_OPTION, PPEP_COORDINATED_DEPENDENCY_OPTION structure pointer [Kernel-Mode Driver Architecture], _PEP_COORDINATED_DEPENDENCY_OPTION, kernel.pep_coordinated_dependency_option, pepfx/PEP_COORDINATED_DEPENDENCY_OPTION, pepfx/PPEP_COORDINATED_DEPENDENCY_OPTION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_COORDINATED_DEPENDENCY_OPTION
product: Windows
targetos: Windows
req.typenames: PEP_COORDINATED_DEPENDENCY_OPTION, *PPEP_COORDINATED_DEPENDENCY_OPTION
---

# _PEP_COORDINATED_DEPENDENCY_OPTION structure


## -description


The <b>PEP_COORIDNATED_DEPENDENCY_OPTION</b> structure describes a coordinated idle stateâ€™s dependency to the OS.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186775">PEP_NOTIFY_PPM_QUERY_COORDINATED_DEPENDENCY notification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186821">PEP_PPM_QUERY_COORDINATED_DEPENDENCY</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_COORDINATED_DEPENDENCY_OPTION structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

