---
UID: NS:pep_x._PEP_PPM_ENTER_SYSTEM_STATE
title: _PEP_PPM_ENTER_SYSTEM_STATE (pep_x.h)
description: Used in the PEP_NOTIFY_PPM_ENTER_SYSTEM_STATE notification to notify PEP that the system is about to enter a system power state.  .
old-location: kernel\pep_ppm_enter_system_state.htm
tech.root: kernel
ms.assetid: 1a398899-b05d-4853-b68d-ae8be958dd91
ms.date: 04/30/2018
keywords: ["_PEP_PPM_ENTER_SYSTEM_STATE structure"]
ms.keywords: "*PPEP_PPM_ENTER_SYSTEM_STATE, PEP_PPM_ENTER_SYSTEM_STATE, PEP_PPM_ENTER_SYSTEM_STATE structure [Kernel-Mode Driver Architecture], PPEP_PPM_ENTER_SYSTEM_STATE, PPEP_PPM_ENTER_SYSTEM_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_ENTER_SYSTEM_STATE, kernel.pep_ppm_enter_system_state, pepfx/PEP_PPM_ENTER_SYSTEM_STATE, pepfx/PPEP_PPM_ENTER_SYSTEM_STATE"
f1_keywords:
 - "pep_x/PEP_PPM_ENTER_SYSTEM_STATE"
req.header: pep_x.h
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
- PEP_PPM_ENTER_SYSTEM_STATE
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_ENTER_SYSTEM_STATE, *PPEP_PPM_ENTER_SYSTEM_STATE
---

# _PEP_PPM_ENTER_SYSTEM_STATE structure


## -description


Used in the <b>PEP_NOTIFY_PPM_ENTER_SYSTEM_STATE</b> notification to notify PEP that the system is about to enter a system power state.  


## -struct-fields




### -field TargetState

On input, a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_system_power_state">SYSTEM_POWER_STATE</a>-type value that indicates the power state that the system is entering. 


## -remarks



This notification is sent to all processors simultaneously after the system has completed all passive level work transitioning the processor to the system power state. 
This notification is sent at DISPATCH_LEVEL, with all processors at dispatch. This notification is always executed on the target processor. 
PEP must not queue any work from this notification. The processors will not process work items, DPCs, etc. after this notification has been sent.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Processor power management (PPM) notifications</a>
 

 

