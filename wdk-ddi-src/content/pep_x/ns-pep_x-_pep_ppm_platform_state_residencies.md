---
UID: NS:pep_x._PEP_PPM_PLATFORM_STATE_RESIDENCIES
title: _PEP_PPM_PLATFORM_STATE_RESIDENCIES (pep_x.h)
description: The PEP_PPM_PLATFORM_STATE_RESIDENCIES structure contains the accumulated residency times and transition counts for the idle states that are supported by the hardware platform.
old-location: kernel\pep_ppm_platform_state_residencies.htm
tech.root: kernel
ms.assetid: 5B6186EB-EC08-4C11-9CCF-E07D78FBD535
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_PLATFORM_STATE_RESIDENCIES, PEP_PPM_PLATFORM_STATE_RESIDENCIES, PEP_PPM_PLATFORM_STATE_RESIDENCIES structure [Kernel-Mode Driver Architecture], PPEP_PPM_PLATFORM_STATE_RESIDENCIES, PPEP_PPM_PLATFORM_STATE_RESIDENCIES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PLATFORM_STATE_RESIDENCIES, kernel.pep_ppm_platform_state_residencies, pepfx/PEP_PPM_PLATFORM_STATE_RESIDENCIES, pepfx/PPEP_PPM_PLATFORM_STATE_RESIDENCIES"
ms.topic: struct
f1_keywords:
 - "pep_x/PEP_PPM_PLATFORM_STATE_RESIDENCIES"
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
- PEP_PPM_PLATFORM_STATE_RESIDENCIES
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_PLATFORM_STATE_RESIDENCIES, *PPEP_PPM_PLATFORM_STATE_RESIDENCIES
---

# _PEP_PPM_PLATFORM_STATE_RESIDENCIES structure


## -description


The <b>PEP_PPM_PLATFORM_STATE_RESIDENCIES</b> structure contains the accumulated residency times and transition counts for the idle states that are supported by the hardware platform.


## -struct-fields




### -field Count

[in] The number of elements in the array pointed to by the <b>States</b> member. The number of array elements equals the number of platform idle states that the PEP previously provided in response to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification.


### -field States

[in] A pointer to an output buffer to which the PEP writes an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_platform_state_residency">PEP_PPM_PLATFORM_STATE_RESIDENCY</a> structures. Each structure contains the accumulated residency and transition count information for a particular platform idle state. This buffer is guaranteed to be large enough to contain the number of array elements specified by the <b>Count</b> member. Each idle state is identified by its array index. If the array contains N elements, idle state indexes range from 0 to N-1.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_platform_state_residencies">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE_RESIDENCIES</a> notification. Both members of the structure contain input values that the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) supplies when this notification is sent to the PEP. PoFx allocates the output buffer pointed to by the <b>States</b> member, and the PEP writes to this buffer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_platform_state_residencies">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE_RESIDENCIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_platform_state_residency">PEP_PPM_PLATFORM_STATE_RESIDENCY</a>
 

 

