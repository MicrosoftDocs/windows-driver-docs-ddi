---
UID: NS:pep_x._PEP_PPM_ENTER_SYSTEM_STATE
title: "_PEP_PPM_ENTER_SYSTEM_STATE"
author: windows-driver-content
description: Used in the PEP_NOTIFY_PPM_ENTER_SYSTEM_STATE notification to notify PEP that the system is about to enter a system power state.  .
old-location: kernel\pep_ppm_enter_system_state.htm
old-project: kernel
ms.assetid: 1a398899-b05d-4853-b68d-ae8be958dd91
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_PPM_ENTER_SYSTEM_STATE, PEP_PPM_ENTER_SYSTEM_STATE, PEP_PPM_ENTER_SYSTEM_STATE structure [Kernel-Mode Driver Architecture], PPEP_PPM_ENTER_SYSTEM_STATE, PPEP_PPM_ENTER_SYSTEM_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_ENTER_SYSTEM_STATE, kernel.pep_ppm_enter_system_state, pepfx/PEP_PPM_ENTER_SYSTEM_STATE, pepfx/PPEP_PPM_ENTER_SYSTEM_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Pepfx.h
api_name:
-	PEP_PPM_ENTER_SYSTEM_STATE
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_ENTER_SYSTEM_STATE, *PPEP_PPM_ENTER_SYSTEM_STATE, PEP_PPM_ENTER_SYSTEM_STATE, *PPEP_PPM_ENTER_SYSTEM_STATE
---

# _PEP_PPM_ENTER_SYSTEM_STATE structure


## -description


Used in the <b>PEP_NOTIFY_PPM_ENTER_SYSTEM_STATE</b> notification to notify PEP that the system is about to enter a system power state.  


## -struct-fields




### -field TargetState

On input, a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564565">SYSTEM_POWER_STATE</a>-type value that indicates the power state that the system is entering. 


## -remarks



This notification is sent to all processors simultaneously after the system has completed all passive level work transitioning the processor to the system power state. 
This notification is sent at DISPATCH_LEVEL, with all processors at dispatch. This notification is always executed on the target processor. 
PEP must not queue any work from this notification. The processors will not process work items, DPCs, etc. after this notification has been sent.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186881">Processor power management (PPM) notifications</a>
 

 

