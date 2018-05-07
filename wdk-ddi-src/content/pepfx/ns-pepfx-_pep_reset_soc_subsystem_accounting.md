---
UID: NS:pepfx._PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING
title: "_PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING"
author: windows-driver-content
description: The PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure is provided to the platform extension plug-in (PEP) as part of a PEP_DPM_RESET_SOC_SUBSYSTEM_ACCOUNTING notification.
old-location: kernel\pep_reset_soc_subsystem_accounting.htm
old-project: kernel
ms.assetid: DCB0E541-51AB-4624-A007-46D109F31E5B
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure [Kernel-Mode Driver Architecture], PPEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, PPEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure pointer [Kernel-Mode Driver Architecture], _PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, kernel.pep_reset_soc_subsystem_accounting, pepfx/PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, pepfx/PPEP_RESET_SOC_SUBSYSTEM_ACCOUNTING"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING
product:
- Windows
targetos: Windows
req.typenames: PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING, *PPEP_RESET_SOC_SUBSYSTEM_ACCOUNTING
---

# _PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING structure


## -description


The <b>PEP_RESET_SOC_SUBSYSTEM_ACCOUNTING</b> structure is provided to the platform extension plug-in (PEP) as part of a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186740">PEP_DPM_RESET_SOC_SUBSYSTEM_ACCOUNTING notification</a>. 


## -struct-fields




### -field PlatformIdleStateIndex

[in] The platform idle state index for the subsystem accounting to be reset.


### -field Flags

This member is reserved and should be set to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186740">PEP_DPM_RESET_SOC_SUBSYSTEM_ACCOUNTING notification</a>
 

 

