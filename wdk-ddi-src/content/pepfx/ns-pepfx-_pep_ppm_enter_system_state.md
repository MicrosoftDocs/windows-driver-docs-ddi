---
UID: NS:pepfx._PEP_PPM_ENTER_SYSTEM_STATE
title: "_PEP_PPM_ENTER_SYSTEM_STATE"
author: windows-driver-content
description: Used in the PEP_NOTIFY_PPM_ENTER_SYSTEM_STATE notification to notify PEP that the system is about to enter a system power state.  .
old-location: kernel\pep_ppm_enter_system_state.htm
old-project: kernel
ms.assetid: 1a398899-b05d-4853-b68d-ae8be958dd91
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PPEP_PPM_ENTER_SYSTEM_STATE, *PPEP_PPM_ENTER_SYSTEM_STATE, _PEP_PPM_ENTER_SYSTEM_STATE, pepfx/PPEP_PPM_ENTER_SYSTEM_STATE, PEP_PPM_ENTER_SYSTEM_STATE structure [Kernel-Mode Driver Architecture], PPEP_PPM_ENTER_SYSTEM_STATE structure pointer [Kernel-Mode Driver Architecture], pepfx/PEP_PPM_ENTER_SYSTEM_STATE, kernel.pep_ppm_enter_system_state, PEP_PPM_ENTER_SYSTEM_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Pepfx.h
apiname:
-	PEP_PPM_ENTER_SYSTEM_STATE
product: Windows
targetos: Windows
req.typenames: PEP_PPM_ENTER_SYSTEM_STATE, *PPEP_PPM_ENTER_SYSTEM_STATE
---

# _PEP_PPM_ENTER_SYSTEM_STATE structure


## -description


Used in the <b>PEP_NOTIFY_PPM_ENTER_SYSTEM_STATE</b> notification to notify PEP that the system is about to enter a system power state.  


## -syntax


````
typedef struct _PEP_PPM_ENTER_SYSTEM_STATE {
  SYSTEM_POWER_STATE  TargetState;
} PEP_PPM_ENTER_SYSTEM_STATE, *PPEP_PPM_ENTER_SYSTEM_STATE;
````


## -struct-fields




### -field TargetState

On input, a <a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a>-type value that indicates the power state that the system is entering. 


## -remarks



This notification is sent to all processors simultaneously after the system has completed all passive level work transitioning the processor to the system power state. 
This notification is sent at DISPATCH_LEVEL, with all processors at dispatch. This notification is always executed on the target processor. 
PEP must not queue any work from this notification. The processors will not process work items, DPCs, etc. after this notification has been sent.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186881">Processor power management (PPM) notifications</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_ENTER_SYSTEM_STATE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

