---
UID: NC:wdm.PROCESSOR_HALT_ROUTINE
title: PROCESSOR_HALT_ROUTINE
author: windows-driver-content
description: A Halt callback routine transitions the processor to an idle state.
old-location: kernel\halt.htm
old-project: kernel
ms.assetid: 425239C1-4FBE-4703-B7DB-9DCC17562A6C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.halt, Halt routine [Kernel-Mode Driver Architecture], Halt, PROCESSOR_HALT_ROUTINE, PROCESSOR_HALT_ROUTINE, wdm/Halt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Pepfx.h
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
req.irql: See Remarks.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdm.h
apiname:
-	Halt
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PROCESSOR_HALT_ROUTINE callback


## -description


A <i>Halt</i> callback routine transitions the processor to an idle state.


## -prototype


````
PROCESSOR_HALT_ROUTINE Halt;

NTSTATUS Halt(
  _Inout_opt_ PVOID Context
)
{ ... }
````


## -parameters




### -param Context [in, out, optional]

A pointer to a PEP-defined processor-halt context. This pointer is the <i>Context</i> parameter value that the PEP previously passed to the <a href="..\pepfx\nc-pepfx-pofxcallbackprocessorhalt.md">ProcessorHalt</a> routine.


## -returns


A <i>Halt</i> callback routine may or may not return. If this routine does return, it returns STATUS_SUCCESS to indicates that the processor successfully entered the idle state. Otherwise, it returns an appropriate error status code.



## -remarks


This routine is implemented by the platform extension plug-in (PEP) and is called by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The <a href="..\pepfx\nc-pepfx-pofxcallbackprocessorhalt.md">ProcessorHalt</a> routine accepts a pointer to a <i>Halt</i> callback routine as a parameter.

The PEP's <i>Halt</i> routine is called at the same IRQL at which the PEP called <b>ProcessorHalt</b>.



## -see-also

<a href="..\pepfx\nc-pepfx-pofxcallbackprocessorhalt.md">ProcessorHalt</a>

<a href="..\pepfx\ns-pepfx-_pep_crashdump_information.md">PEP_CRASHDUMP_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PROCESSOR_HALT_ROUTINE routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

