---
UID: NC:pep_x.PPO_ENUMERATE_INTERRUPT_SOURCE_CALLBACK
title: PO_ENUMERATE_INTERRUPT_SOURCE_CALLBACK
author: windows-driver-content
description: An EnumerateInterruptSource callback routine supplies a platform extension plug-in (PEP) with information about an interrupt source.
old-location: kernel\enumerateinterruptsource.htm
old-project: kernel
ms.assetid: 1E6841D8-88A0-4EDB-89EF-3878AF8B0072
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: EnumerateInterruptSource, EnumerateInterruptSource routine [Kernel-Mode Driver Architecture], PO_ENUMERATE_INTERRUPT_SOURCE_CALLBACK, kernel.enumerateinterruptsource, pepfx/EnumerateInterruptSource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: See Remarks.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	pepfx.h
api_name:
-	EnumerateInterruptSource
product: Windows
targetos: Windows
req.typenames: PO_FX_CORE_DEVICE, *PPO_FX_CORE_DEVICE
---

# PPO_ENUMERATE_INTERRUPT_SOURCE_CALLBACK callback


## -description


An <i>EnumerateInterruptSource</i> callback routine supplies a platform extension plug-in (PEP) with information about an interrupt source.


## -prototype


````
PO_ENUMERATE_INTERRUPT_SOURCE_CALLBACK EnumerateInterruptSource;

BOOLEAN EnumerateInterruptSource(
  _In_ PVOID                               CallbackContext,
  _In_ PPEP_UNMASKED_INTERRUPT_INFORMATION InterruptInformation
)
{ ... }
````


## -parameters




### -param CallbackContext [in]

A pointer to a callback context. The PEP specified this pointer value as a parameter in the <a href="..\pepfx\nc-pepfx-pofxcallbackenumerateunmaskedinterrupts.md">EnumerateUnmaskedInterrupts</a> call that initiated the enumeration of interrupt sources.


### -param InterruptInformation [in]

A pointer to a <a href="..\pepfx\ns-pepfx-_pep_unmasked_interrupt_information.md">PEP_UNMASKED_INTERRUPT_INFORMATION</a> structure that contains information about the interrupt source.


## -returns



If the <i>EnumerateInterruptSource</i> callback routine returns TRUE, <b>EnumerateUnmaskedInterrupts</b> will continue to call the <i>EnumerateInterruptSource</i> callback routine while more interrupts are available to be enumerated. If the <i>EnumerateInterruptSource</i> callback routine returns FALSE, <b>EnumerateUnmaskedInterrupts</b> returns without enumerating any more interrupts.




## -remarks



This callback routine is implemented by a PEP, and is called by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The <i>Callback</i> parameter of the <a href="..\pepfx\nc-pepfx-pofxcallbackenumerateunmaskedinterrupts.md">EnumerateUnmaskedInterrupts</a> routine is a pointer to an <i>EnumerateInterruptSource</i> callback routine.

After a PEP calls <b>EnumerateUnmaskedInterrupts</b> to enumerate the unmasked interrupt sources, PoFx calls the PEP's <i>EnumerateInterruptSource</i> callback routine once for each unmasked interrupt source. <b>EnumerateUnmaskedInterrupts</b> returns only after the last call to the <i>EnumerateInterruptSource</i> callback routine completes.

An <i>EnumerateInterruptSource</i> callback routine is called at the same IRQL as the PEP's call to <b>EnumerateUnmaskedInterrupts</b> that initiates the enumeration callbacks.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_unmasked_interrupt_information.md">PEP_UNMASKED_INTERRUPT_INFORMATION</a>



<a href="..\pepfx\nc-pepfx-pofxcallbackenumerateunmaskedinterrupts.md">EnumerateUnmaskedInterrupts</a>



 

 


