---
UID: NS:pep_x._PEP_QUERY_SOC_SUBSYSTEM_COUNT
title: "_PEP_QUERY_SOC_SUBSYSTEM_COUNT"
description: The PEP_QUERY_SOC_SUBSYSTEM_COUNT structure is used to tell the OS whether the PEP supports system on a chip (SoC) subsystem accounting for a given platform idle state.
old-location: kernel\pep_query_soc_subsystem_count.htm
tech.root: kernel
ms.assetid: 1DB17B90-41B7-4DA2-AFB6-3A4B218068F6
ms.date: 04/30/2018
ms.keywords: "*PPEP_QUERY_SOC_SUBSYSTEM_COUNT, PEP_QUERY_SOC_SUBSYSTEM_COUNT, PEP_QUERY_SOC_SUBSYSTEM_COUNT structure [Kernel-Mode Driver Architecture], PPEP_QUERY_SOC_SUBSYSTEM_COUNT, PPEP_QUERY_SOC_SUBSYSTEM_COUNT structure pointer [Kernel-Mode Driver Architecture], _PEP_QUERY_SOC_SUBSYSTEM_COUNT, kernel.pep_query_soc_subsystem_count, pepfx/PEP_QUERY_SOC_SUBSYSTEM_COUNT, pepfx/PPEP_QUERY_SOC_SUBSYSTEM_COUNT"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_QUERY_SOC_SUBSYSTEM_COUNT
product:
- Windows
targetos: Windows
req.typenames: PEP_QUERY_SOC_SUBSYSTEM_COUNT, *PPEP_QUERY_SOC_SUBSYSTEM_COUNT
---

# _PEP_QUERY_SOC_SUBSYSTEM_COUNT structure


## -description


The <b>PEP_QUERY_SOC_SUBSYSTEM_COUNT</b> structure is used to tell the OS whether the PEP supports system on a chip (SoC) subsystem accounting for a given platform idle state. 


## -struct-fields




### -field PlatformIdleStateIndex

[in] The platform idle state index for which the kernel is querying about. 


### -field SubsystemCount

[out] The number of SoC subsystems tallied by the PEP for the specified platform idle state.  The PEP cannot return 0 in this parameter; instead the PEP should return <b>FALSE</b> to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186733">PEP_DPM_QUERY_SOC_SUBSYSTEM_COUNT notification</a> that provided this structure.  


### -field Flags

This member is reserved and should be set to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186733">PEP_DPM_QUERY_SOC_SUBSYSTEM_COUNT notification</a>
 

 

