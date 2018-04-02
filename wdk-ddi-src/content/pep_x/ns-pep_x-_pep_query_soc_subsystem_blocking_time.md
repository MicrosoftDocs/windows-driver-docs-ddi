---
UID: NS:pep_x._PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME
title: "_PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME"
author: windows-driver-content
description: The PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME structure is used by the PEP_DPM_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME notification to collect details about the blocking duration for a particular system on a chip (SoC) subsystem.
old-location: kernel\pep_query_soc_subsystem_blocking_time.htm
old-project: kernel
ms.assetid: 54A2D89F-FCD0-4F91-8D0E-181F63790C89
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME, PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME, PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME structure [Kernel-Mode Driver Architecture], PPEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME, PPEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME structure pointer [Kernel-Mode Driver Architecture], _PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME, kernel.pep_query_soc_subsystem_blocking_time, pepfx/PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME, pepfx/PPEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME
product: Windows
targetos: Windows
req.typenames: PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME, *PPEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME, PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME, *PPEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME
---

# _PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME structure


## -description


The <b>PEP_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME</b> structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186732">PEP_DPM_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME notification</a> to collect details about the blocking duration for a particular system on a chip (SoC) subsystem.


## -struct-fields




### -field PlatformIdleStateIndex

[in] The platform idle state index for the SoC subsystem that the OS is querying.


### -field SubsystemHandle

[in] A context pointer that the PEP previously provided on subsystem initialization. The context pointer is optional, so if none was provided then the value will be zero. The PEP is free to ignore this field.


### -field SubsystemName

[in] The name of the subsystem whose blocking time is being queried.  This name was provided by the PEP on subsystem initialization.


### -field BlockingTime

[out] The blocking time tallied for this subsystem in 100 nanosecond units since the previous <a href="https://msdn.microsoft.com/library/windows/hardware/mt186740">PEP_DPM_RESET_SOC_SUBSYSTEM_ACCOUNTING notification</a>.


### -field Flags

This member is reserved and should be set to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186732">PEP_DPM_QUERY_SOC_SUBSYSTEM_BLOCKING_TIME notification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186740">PEP_DPM_RESET_SOC_SUBSYSTEM_ACCOUNTING notification</a>
 

 

