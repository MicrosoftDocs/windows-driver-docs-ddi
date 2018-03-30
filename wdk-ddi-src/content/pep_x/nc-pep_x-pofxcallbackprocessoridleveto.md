---
UID: NC:pep_x.POFXCALLBACKPROCESSORIDLEVETO
title: POFXCALLBACKPROCESSORIDLEVETO
author: windows-driver-content
description: The ProcessorIdleVeto routine increments or decrements the veto count for a veto code for a processor idle state.
old-location: kernel\processoridleveto.htm
old-project: kernel
ms.assetid: 505276EE-5D41-4AB2-82FB-FBDEF994F372
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: POFXCALLBACKPROCESSORIDLEVETO, ProcessorIdleVeto, ProcessorIdleVeto routine [Kernel-Mode Driver Architecture], ProcessorIdleVetoreadv, kernel.processoridleveto, pepfx/ProcessorIdleVeto
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	UserDefined
api_location:
-	pepfx.h
api_name:
-	ProcessorIdleVeto
product: Windows
targetos: Windows
req.typenames: PO_FX_CORE_DEVICE, *PPO_FX_CORE_DEVICE
---

# POFXCALLBACKPROCESSORIDLEVETO callback


## -description


The <b>ProcessorIdleVeto</b> routine increments or decrements the veto count for a veto code for a processor idle state.


## -parameters




### -param ProcessorHandle [in]

A POHANDLE value that represents the registration of the processor (as a device) with <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The platform extension plug-in (PEP) previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the processor had been registered with PoFx.


### -param ProcessorState [in]

The index of the processor idle state whose veto count is being incremented or decremented. The PEP previously specified the supported processor idle states in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. If the PEP specified N processor idle states, valid processor idle state indexes range from 0 to N–1.


### -param VetoReason [in]

A PEP-defined veto code that indicates why the processor idle state cannot be entered. The PEP previously specified the supported veto reasons in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a> notification. If the PEP specified M veto reasons, valid veto codes range from 1 to M.


### -param Increment [in]

Whether to increment or decrement the veto count. Set to TRUE to increment the veto count for this veto reason, or to FALSE to decrement the count.

Whether to increment or decrement the veto count. Set to TRUE to increment the veto count for this veto reason, or to FALSE to decrement the count.


## -returns



This routine does not return a value.




## -remarks



This routine is implemented by the power management framework (PoFx) and is called by the platform extension plug-in (PEP). The <b>ProcessorIdleVeto</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>ProcessorIdleVeto</b> routine.






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a>
 

 

