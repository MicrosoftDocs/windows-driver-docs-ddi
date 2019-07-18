---
UID: NS:pepfx._PEP_PPM_RESUME_FROM_SYSTEM_STATE
title: _PEP_PPM_RESUME_FROM_SYSTEM_STATE (pepfx.h)
description: Used by the PEP_NOTIFY_PPM_RESUME_FROM_SYSTEM_STATE notification that notifies the PEP that the system has just resumed from a system power state.
old-location: kernel\pep_ppm_resume_from_system_state.htm
tech.root: kernel
ms.assetid: 281f223a-1189-4045-9a3a-17433432a6a3
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_RESUME_FROM_SYSTEM_STATE, PEP_PPM_RESUME_FROM_SYSTEM_STATE, PEP_PPM_RESUME_FROM_SYSTEM_STATE structure [Kernel-Mode Driver Architecture], _PEP_PPM_RESUME_FROM_SYSTEM_STATE, kernel.pep_ppm_resume_from_system_state, pepfx/PEP_PPM_RESUME_FROM_SYSTEM_STATE"
ms.topic: struct
f1_keywords:
 - "pepfx/PEP_PPM_RESUME_FROM_SYSTEM_STATE"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
- Pepfx.h
api_name:
- PEP_PPM_RESUME_FROM_SYSTEM_STATE
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_RESUME_FROM_SYSTEM_STATE, *PPEP_PPM_RESUME_FROM_SYSTEM_STATE
---

# _PEP_PPM_RESUME_FROM_SYSTEM_STATE structure


## -description


Used by the <b>PEP_NOTIFY_PPM_RESUME_FROM_SYSTEM_STATE</b> notification that notifies the PEP that the system has just resumed from a system power state. 


## -struct-fields




### -field TargetState

On input, a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_system_power_state">SYSTEM_POWER_STATE</a>-type value that indicates the power state that the system is entering. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Processor power management (PPM) notifications</a>
 

 

