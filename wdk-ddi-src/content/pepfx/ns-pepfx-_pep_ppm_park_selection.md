---
UID: NS:pepfx._PEP_PPM_PARK_SELECTION
title: "_PEP_PPM_PARK_SELECTION"
author: windows-driver-content
description: The PEP_PPM_PARK_SELECTION structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption.
old-location: kernel\pep_ppm_park_selection.htm
tech.root: kernel
ms.assetid: 1957D03D-7C85-4A58-A5CC-94D3C9913F5A
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_PARK_SELECTION, PEP_PPM_PARK_SELECTION, PEP_PPM_PARK_SELECTION structure [Kernel-Mode Driver Architecture], PPEP_PPM_PARK_SELECTION, PPEP_PPM_PARK_SELECTION structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PARK_SELECTION, kernel.pep_ppm_park_selection, pepfx/PEP_PPM_PARK_SELECTION, pepfx/PPEP_PPM_PARK_SELECTION"
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
-	PEP_PPM_PARK_SELECTION
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_PARK_SELECTION, *PPEP_PPM_PARK_SELECTION
---

# _PEP_PPM_PARK_SELECTION structure


## -description


The <b>PEP_PPM_PARK_SELECTION</b> structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption.


## -struct-fields




### -field AdditionalUnparkedProcessors

[in] The number of additional processors that need to be parked.

This number includes all processors in the <b>Processors</b> array for which the PEP sets <b>PepPreference</b> to PROCESSOR_PARK_PREFERENCE_PARKED but the operating system sets <b>PoPreference</b> to either PROCESSOR_PARK_PREFERENCE_UNPARKED or PROCESSOR_PARK_PREFERENCE_NONE. For more information about these values, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt186837">PEP_PROCESSOR_PARK_PREFERENCE</a>.

This number does <u>not</u> include processors in the <b>Processors</b> array for which the operating system sets the <b>PoPreference</b> value to PROCESSOR_PARK_PREFERENCE_PARKED.


### -field Count

[in] The number of elements in the array pointed to by the <b>Processors</b> member.


### -field Processors

[in/out] A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/mt186837">PEP_PROCESSOR_PARK_PREFERENCE</a> structures. The <b>Count</b> member specifies the number of elements in the array.





#### On input

Each array element indicates the parking preferences for a particular processor.



#### On output

Returns the PEP parking preference for each processor.

The Processors array is guaranteed to contain the processors in increasing order by processor index.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186812">PEP_NOTIFY_PPM_PARK_SELECTION</a> notification. All three members of the structure contain input values that are set by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) before this notification is sent to the PEP.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186812">PEP_NOTIFY_PPM_PARK_SELECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186837">PEP_PROCESSOR_PARK_PREFERENCE</a>
 

 

