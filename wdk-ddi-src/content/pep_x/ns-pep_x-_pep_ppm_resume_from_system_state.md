---
UID: NS:pep_x._PEP_PPM_RESUME_FROM_SYSTEM_STATE
title: "_PEP_PPM_RESUME_FROM_SYSTEM_STATE"
author: windows-driver-content
description: Used by the PEP_NOTIFY_PPM_RESUME_FROM_SYSTEM_STATE notification that notifies the PEP that the system has just resumed from a system power state.
old-location: kernel\pep_ppm_resume_from_system_state.htm
old-project: kernel
ms.assetid: 281f223a-1189-4045-9a3a-17433432a6a3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPEP_PPM_RESUME_FROM_SYSTEM_STATE, PEP_PPM_RESUME_FROM_SYSTEM_STATE, PEP_PPM_RESUME_FROM_SYSTEM_STATE structure [Kernel-Mode Driver Architecture], _PEP_PPM_RESUME_FROM_SYSTEM_STATE, kernel.pep_ppm_resume_from_system_state, pepfx/PEP_PPM_RESUME_FROM_SYSTEM_STATE"
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
-	PEP_PPM_RESUME_FROM_SYSTEM_STATE
product: Windows
targetos: Windows
req.typenames: PEP_PPM_RESUME_FROM_SYSTEM_STATE, *PPEP_PPM_RESUME_FROM_SYSTEM_STATE, PEP_PPM_RESUME_FROM_SYSTEM_STATE, *PPEP_PPM_RESUME_FROM_SYSTEM_STATE
---

# _PEP_PPM_RESUME_FROM_SYSTEM_STATE structure


## -description


Used by the <b>PEP_NOTIFY_PPM_RESUME_FROM_SYSTEM_STATE</b> notification that notifies the PEP that the system has just resumed from a system power state. 


## -syntax


````
typedef struct _PEP_PPM_RESUME_FROM_SYSTEM_STATE {
  SYSTEM_POWER_STATE  TargetState;
} PEP_PPM_RESUME_FROM_SYSTEM_STATE, PEP_PPM_RESUME_FROM_SYSTEM_STATE;
````


## -struct-fields




### -field TargetState

On input, a <a href="..\ntpoapi\ne-ntpoapi-_system_power_state.md">SYSTEM_POWER_STATE</a>-type value that indicates the power state that the system is entering. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186881">Processor power management (PPM) notifications</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_RESUME_FROM_SYSTEM_STATE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

