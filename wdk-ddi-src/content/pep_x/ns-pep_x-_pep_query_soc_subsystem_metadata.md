---
UID: NS:pep_x._PEP_QUERY_SOC_SUBSYSTEM_METADATA
title: _PEP_QUERY_SOC_SUBSYSTEM_METADATA (pep_x.h)
description: The PEP_QUERY_SOC_SUBSYSTEM_METADATA structure is used with the PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA notification to collect optional metadata about the system on a chip (SoC) subsystem whose blocking time has just been queried.
old-location: kernel\pep_query_soc_subsystem_metadata.htm
tech.root: kernel
ms.assetid: D823EF66-1440-45B7-A0D8-A98522AA69E1
ms.date: 04/30/2018
ms.keywords: "*PPEP_QUERY_SOC_SUBSYSTEM_METADATA, PEP_QUERY_SOC_SUBSYSTEM_METADATA, PEP_QUERY_SOC_SUBSYSTEM_METADATA structure [Kernel-Mode Driver Architecture], PPEP_QUERY_SOC_SUBSYSTEM_METADATA, PPEP_QUERY_SOC_SUBSYSTEM_METADATA structure pointer [Kernel-Mode Driver Architecture], _PEP_QUERY_SOC_SUBSYSTEM_METADATA, kernel.pep_query_soc_subsystem_metadata, pepfx/PEP_QUERY_SOC_SUBSYSTEM_METADATA, pepfx/PPEP_QUERY_SOC_SUBSYSTEM_METADATA"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_QUERY_SOC_SUBSYSTEM_METADATA
product:
- Windows
targetos: Windows
req.typenames: PEP_QUERY_SOC_SUBSYSTEM_METADATA, *PPEP_QUERY_SOC_SUBSYSTEM_METADATA
---

# _PEP_QUERY_SOC_SUBSYSTEM_METADATA structure


## -description


The <b>PEP_QUERY_SOC_SUBSYSTEM_METADATA</b> structure is used with the <b>PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA</b> notification to collect optional metadata about the system on a chip (SoC) subsystem whose blocking time has just been queried.


## -struct-fields




### -field PlatformIdleStateIndex

[in] The platform idle state index for the SoC subsystem that the OS is querying.


### -field SubsystemHandle

[in] A context pointer that the PEP previously provided on subsystem initialization. The context pointer is optional, so if none was provided then the value will be zero. The PEP is free to ignore this field.


### -field SubsystemName

[in] The name of the subsystem whose metadata is being queried.


### -field Flags

This member is reserved and should be set to zero.


### -field MetadataCount

[in] The number of entries in the <b>Metadata</b> array.  The PEP previously provided this value as <b>PEP_QUERY_SOC_SUBSYSTEM.MetadataCount</b>.


### -field Metadata

[in/out] An array of pointers to <a href="https://msdn.microsoft.com/library/windows/hardware/mt186854">PEP_SOC_SUBSYSTEM_METADATA</a> structures.  Each entry holds one key/value metadata string-pair.


## -see-also




<b>PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA</b>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186854">PEP_SOC_SUBSYSTEM_METADATA</a>
 

 

