---
UID: NS:pepfx._PEP_PPM_CST_STATES
title: "_PEP_PPM_CST_STATES"
author: windows-driver-content
description: The PEP_PPM_CST_STATES structure specifies the properties of the C states (ACPI processor power states) that are supported for a processor.
old-location: kernel\pep_ppm_cst_states.htm
old-project: kernel
ms.assetid: 4E620796-3065-469E-8E91-8F698F672CAE
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PPEP_PPM_CST_STATES, ,, A, C, E, M, P, PEP_PPM_CST_STATES, PEP_PPM_CST_STATES structure [Kernel-Mode Driver Architecture], PPEP_PPM_CST_STATES, PPEP_PPM_CST_STATES structure pointer [Kernel-Mode Driver Architecture], S, T, _, _PEP_PPM_CST_STATES, kernel.pep_ppm_cst_states, pepfx/PEP_PPM_CST_STATES, pepfx/PPEP_PPM_CST_STATES"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PPM_CST_STATES
product: Windows
targetos: Windows
req.typenames: PEP_PPM_CST_STATES, *PPEP_PPM_CST_STATES
---

# _PEP_PPM_CST_STATES structure


## -description


The <b>PEP_PPM_CST_STATES</b> structure specifies the properties of the C states (ACPI processor power states) that are supported for a processor.


## -syntax


````
typedef struct _PEP_PPM_CST_STATES {
  ULONG              Count;
  PPEP_PPM_CST_STATE IdleStates;
} PEP_PPM_CST_STATES, *PPEP_PPM_CST_STATES;
````


## -struct-fields




### -field Count

The number of elements in the <b>IdleStates</b> array.


### -field IdleStates

A pointer to an array of <a href="..\pep_x\ns-pep_x-_pep_ppm_cst_state.md">PEP_PPM_CST_STATE</a> structures.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186800">PEP_NOTIFY_PPM_CST_STATES</a> notification. The contents of this structure are obtained from the _CST object that is located in the ACPI namespace for the processor. 




## -see-also

<a href="..\pep_x\ns-pep_x-_pep_ppm_cst_state.md">PEP_PPM_CST_STATE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186800">PEP_NOTIFY_PPM_CST_STATES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_CST_STATES structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

