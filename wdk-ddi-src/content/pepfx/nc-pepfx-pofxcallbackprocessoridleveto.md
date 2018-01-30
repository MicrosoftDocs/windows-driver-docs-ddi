---
UID: NC:pepfx.POFXCALLBACKPROCESSORIDLEVETO
title: POFXCALLBACKPROCESSORIDLEVETO
author: windows-driver-content
description: The ProcessorIdleVeto routine increments or decrements the veto count for a veto code for a processor idle state.
old-location: kernel\processoridleveto.htm
old-project: kernel
ms.assetid: 505276EE-5D41-4AB2-82FB-FBDEF994F372
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.processoridleveto, ProcessorIdleVetoreadv, ProcessorIdleVeto routine [Kernel-Mode Driver Architecture], ProcessorIdleVeto, POFXCALLBACKPROCESSORIDLEVETO, POFXCALLBACKPROCESSORIDLEVETO, pepfx/ProcessorIdleVeto
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	pepfx.h
apiname:
-	ProcessorIdleVeto
product: Windows
targetos: Windows
req.typenames: "*PVPCI_PNP_ID, VPCI_PNP_ID"
---

# POFXCALLBACKPROCESSORIDLEVETO callback


## -description


The <b>ProcessorIdleVeto</b> routine increments or decrements the veto count for a veto code for a processor idle state.


## -prototype


````
POFXCALLBACKPROCESSORIDLEVETO ProcessorIdleVeto;

void ProcessorIdleVeto(
  _In_ POHANDLE ProcessorHandle,
  _In_ ULONG    ProcessorState,
  _In_ ULONG    VetoReason,
  _In_ BOOLEAN  Increment,
  _In_ BOOLEAN  Increment
)
{ ... }
````


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


This routine is implemented by the power management framework (PoFx) and is called by the platform extension plug-in (PEP). The <b>ProcessorIdleVeto</b> member of the <a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>ProcessorIdleVeto</b> routine.





## -see-also

<a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POFXCALLBACKPROCESSORIDLEVETO routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

