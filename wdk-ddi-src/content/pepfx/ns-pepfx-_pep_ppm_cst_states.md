---
UID: NS:pepfx._PEP_PPM_CST_STATES
title: "_PEP_PPM_CST_STATES"
description: The PEP_PPM_CST_STATES structure specifies the properties of the C states (ACPI processor power states) that are supported for a processor.
old-location: kernel\pep_ppm_cst_states.htm
tech.root: kernel
ms.assetid: 4E620796-3065-469E-8E91-8F698F672CAE
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_CST_STATES, PEP_PPM_CST_STATES, PEP_PPM_CST_STATES structure [Kernel-Mode Driver Architecture], PPEP_PPM_CST_STATES, PPEP_PPM_CST_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_CST_STATES, kernel.pep_ppm_cst_states, pepfx/PEP_PPM_CST_STATES, pepfx/PPEP_PPM_CST_STATES"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PPM_CST_STATES
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_CST_STATES, *PPEP_PPM_CST_STATES
---

# _PEP_PPM_CST_STATES structure


## -description


The <b>PEP_PPM_CST_STATES</b> structure specifies the properties of the C states (ACPI processor power states) that are supported for a processor.


## -struct-fields




### -field Count

The number of elements in the <b>IdleStates</b> array.


### -field IdleStates

A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/mt186799">PEP_PPM_CST_STATE</a> structures.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186800">PEP_NOTIFY_PPM_CST_STATES</a> notification. The contents of this structure are obtained from the _CST object that is located in the ACPI namespace for the processor. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186800">PEP_NOTIFY_PPM_CST_STATES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186799">PEP_PPM_CST_STATE</a>
 

 

