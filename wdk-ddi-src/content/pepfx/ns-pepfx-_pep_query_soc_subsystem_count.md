---
UID: NS:pepfx._PEP_QUERY_SOC_SUBSYSTEM_COUNT
title: "_PEP_QUERY_SOC_SUBSYSTEM_COUNT"
author: windows-driver-content
description: The PEP_QUERY_SOC_SUBSYSTEM_COUNT structure is used to tell the OS whether the PEP supports system on a chip (SoC) subsystem accounting for a given platform idle state.
old-location: kernel\pep_query_soc_subsystem_count.htm
old-project: kernel
ms.assetid: 1DB17B90-41B7-4DA2-AFB6-3A4B218068F6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "_PEP_QUERY_SOC_SUBSYSTEM_COUNT, PPEP_QUERY_SOC_SUBSYSTEM_COUNT structure pointer [Kernel-Mode Driver Architecture], *PPEP_QUERY_SOC_SUBSYSTEM_COUNT, PEP_QUERY_SOC_SUBSYSTEM_COUNT structure [Kernel-Mode Driver Architecture], kernel.pep_query_soc_subsystem_count, PPEP_QUERY_SOC_SUBSYSTEM_COUNT, PEP_QUERY_SOC_SUBSYSTEM_COUNT, pepfx/PPEP_QUERY_SOC_SUBSYSTEM_COUNT, pepfx/PEP_QUERY_SOC_SUBSYSTEM_COUNT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
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
-	PEP_QUERY_SOC_SUBSYSTEM_COUNT
product: Windows
targetos: Windows
req.typenames: PEP_QUERY_SOC_SUBSYSTEM_COUNT, *PPEP_QUERY_SOC_SUBSYSTEM_COUNT
---

# _PEP_QUERY_SOC_SUBSYSTEM_COUNT structure


## -description


The <b>PEP_QUERY_SOC_SUBSYSTEM_COUNT</b> structure is used to tell the OS whether the PEP supports system on a chip (SoC) subsystem accounting for a given platform idle state. 


## -syntax


````
typedef struct _PEP_QUERY_SOC_SUBSYSTEM_COUNT {
  ULONG PlatformIdleStateIndex;
  ULONG SubsystemCount;
  ULONG Flags;
} PEP_QUERY_SOC_SUBSYSTEM_COUNT, *PPEP_QUERY_SOC_SUBSYSTEM_COUNT;
````


## -struct-fields




### -field PlatformIdleStateIndex

[in] The platform idle state index for which the kernel is querying about. 


### -field SubsystemCount

[out] The number of SoC subsystems tallied by the PEP for the specified platform idle state.  The PEP cannot return 0 in this parameter; instead the PEP should return <b>FALSE</b> to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186733">PEP_DPM_QUERY_SOC_SUBSYSTEM_COUNT notification</a> that provided this structure.  


### -field Flags

This member is reserved and should be set to zero.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186733">PEP_DPM_QUERY_SOC_SUBSYSTEM_COUNT notification</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_QUERY_SOC_SUBSYSTEM_COUNT structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

