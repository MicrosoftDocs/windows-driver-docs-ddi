---
UID: NC:wdm.PROCESSOR_HALT_ROUTINE
title: PROCESSOR_HALT_ROUTINE (wdm.h)
description: A Halt callback routine transitions the processor to an idle state.
old-location: kernel\halt.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PROCESSOR_HALT_ROUTINE callback function"]
ms.keywords: Halt, Halt routine [Kernel-Mode Driver Architecture], PROCESSOR_HALT_ROUTINE, kernel.halt, wdm/Halt
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PROCESSOR_HALT_ROUTINE
 - wdm/PROCESSOR_HALT_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - Halt
---

# PROCESSOR_HALT_ROUTINE callback function


## -description

A <i>Halt</i> callback routine transitions the processor to an idle state.

## -parameters

### -param Context 

[in, out, optional]
A pointer to a PEP-defined processor-halt context. This pointer is the <i>Context</i> parameter value that the PEP previously passed to the <a href="/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackprocessorhalt">ProcessorHalt</a> routine.

## -returns

A <i>Halt</i> callback routine may or may not return. If this routine does return, it returns STATUS_SUCCESS to indicates that the processor successfully entered the idle state. Otherwise, it returns an appropriate error status code.

## -remarks

This routine is implemented by the platform extension plug-in (PEP) and is called by the Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx). The <a href="/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackprocessorhalt">ProcessorHalt</a> routine accepts a pointer to a <i>Halt</i> callback routine as a parameter.

The PEP's <i>Halt</i> routine is called at the same IRQL at which the PEP called <b>ProcessorHalt</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_crashdump_information">PEP_CRASHDUMP_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackprocessorhalt">ProcessorHalt</a>
