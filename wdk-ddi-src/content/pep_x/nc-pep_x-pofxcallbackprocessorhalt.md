---
UID: NC:pep_x.POFXCALLBACKPROCESSORHALT
title: POFXCALLBACKPROCESSORHALT (pep_x.h)
description: The ProcessorHalt routine prepares the processor to be halted.
old-location: kernel\processorhalt.htm
tech.root: kernel
ms.assetid: DEBE74B2-DFBD-43D7-8B14-86B4DA7D4C98
ms.date: 04/30/2018
keywords: ["POFXCALLBACKPROCESSORHALT callback function"]
ms.keywords: POFXCALLBACKPROCESSORHALT, ProcessorHalt, ProcessorHalt routine [Kernel-Mode Driver Architecture], kernel.processorhalt, pepfx/ProcessorHalt
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
req.irql: <= HIGH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - POFXCALLBACKPROCESSORHALT
 - pep_x/POFXCALLBACKPROCESSORHALT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - pepfx.h
api_name:
 - ProcessorHalt
---

# POFXCALLBACKPROCESSORHALT callback function (pep_x.h)


## -description

The <b>ProcessorHalt</b> routine prepares the processor to be halted.

## -parameters

### -param Flags 

[in]
Flags that indicate the properties of the idle state that the processor will enter. The <i>Flags</i> parameter is set to zero or to the bitwise-OR of one or more of the following flag bits.

<table>
<tr>
<th>Flag name</th>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>PROCESSOR_HALT_CACHE_FLUSH_OVERRIDE</td>
<td>0x01</td>
<td>The PEP's <i>Halt</i> callback routine is responsible for flushing the processor's caches. If this flag is <u>not</u> set, <b>ProcessorHalt</b> will flush the caches on entry to the processor idle state, and will invalidate the caches on exit from this state.</td>
</tr>
<tr>
<td>PROCESSOR_HALT_CACHE_COHERENT</td>
<td>0x02</td>
<td>Prepare the processor to enter an idle state in which the processor's caches will remain coherent.</td>
</tr>
<tr>
<td>PROCESSOR_HALT_CONTEXT_RETAINED</td>
<td>0x04</td>
<td>Prepare the processor to enter an idle state in which the processor's thread context will be preserved.</td>
</tr>
<tr>
<td>PROCESSOR_HALT_RETURN_NOT_SAFE</td>
<td>0x08</td>
<td>The PEP's <i>Halt</i> callback routine is guaranteed to not return. Set this flag if the <i>Halt</i> callback transitions the processor to a context-losing, power-gated state that cannot be canceled by hardware. When this flag is set, the operating system will treat a return from the <i>Halt</i> callback as a fatal error.</td>
</tr>
<tr>
<td>PROCESSOR_HALT_VIA_PSCI_CPU_SUSPEND</td>
<td>0x16</td>
<td></td>
</tr>
</table>

### -param Context 

[in, out, optional]
A pointer to a PEP-defined processor-halt context. This pointer is passed as a parameter to the <i>Halt</i> callback routine. This context is opaque to the Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx).

### -param Halt 

[in]
A pointer to a PEP-implemented <i>Halt</i> callback routine. PoFx calls this routine after preparations to halt the processor have been completed. During this callback, the PEP is expected to transition the processor to the <i>halted</i> state.

## -returns

<b>ProcessorHalt</b> returns STATUS_SUCCESS if the processor is successfully prepared to be halted. Possible error return values include the following status code.

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>
</td>
<td width="60%">
The <i>Halt</i> parameter is NULL; or an invalid flag value was specified in <i>Flags</i>; or <i>Flags</i> contains an illegal combination of flag bits. For more information, see Remarks.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_UNSUCCESSFUL</dt>
</dl>
</td>
<td width="60%">
The PEP's <i>Halt</i> callback routine unexpectedly returned from an idle state in which the processor's hardware context was not preserved.

</td>
</tr>
</table>

## -remarks

This routine is implemented by the power management framework (PoFx) and is called by the platform extension plug-in (PEP). The <b>ProcessorHalt</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_kernel_information_struct_v3">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to a <b>ProcessorHalt</b> routine.

Before halting the processor, the PEP calls the <b>ProcessorHalt</b> routine to give PoFx an opportunity to save the processor's hardware context. If necessary, <b>ProcessorHalt</b> saves this state internally in PoFx so that the state can later be restored when the processor exits the idle state. After preparing the processor to enter the idle state, <b>ProcessorHalt</b> calls the PEP's <i>Halt</i> callback routine to halt the processor.

As part of the PEP's handling of a  <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_idle_execute">PEP_NOTIFY_PPM_IDLE_EXECUTE</a> notification, the PEP must transition the processor to the idle state that the PEP has selected. The following are the two ways to enter the processor idle state:

<ul>
<li>For a processor idle state in which the processor's caches remain coherent so that all system and processor state is maintained, the PEP can enter the idle state directly without first calling <b>ProcessorHalt</b>.</li>
<li>For a processor idle state in which the processor's caches might not remain coherent, or an idle state in which the processor hardware context is not preserved, the PEP must call <b>ProcessorHalt</b> before transitioning the processor to the idle state.</li>
</ul>
The following combinations of flag bits are illegal:

<ul>
<li>
PROCESSOR_HALT_CONTEXT_RETAINED = 1 and PROCESSOR_HALT_RETURN_NOT_SAFE = 1

The PEP's <i>Halt</i> callback routine must return from any state in which context      is retained.

</li>
<li>
PROCESSOR_HALT_CACHE_FLUSH_OVERRIDE = 1 and PROCESSOR_HALT_CACHE_COHERENT = 1

The cache-flush-override flag should be set <u>only</u> if entering an idle state      that is not cache coherent.

</li>
<li>
PROCESSOR_HALT_CACHE_FLUSH_OVERRIDE = 0 and PROCESSOR_HALT_CACHE_COHERENT = 0

The cache-flush-override flag must be set for any non-cache coherent halt.

</li>
<li>
PROCESSOR_HALT_CONTEXT_RETAINED = 0 and PROCESSOR_HALT_CACHE_COHERENT = 1

Any idle states that lose processor hardware context (and therefore use the <a href="https://acpica.org/sites/acpica/files/MP Startup for ARM platforms.doc">multiprocessor parking protocol</a> to exit the idle state and return control to the operating system) are not cache-coherent states.

</li>
</ul>
If the <i>Flags</i> parameter contains an illegal combination of flag bits, <b>ProcessorHalt</b> fails and returns STATUS_INVALID_PARAMETER.

The PEP can call this routine at IRQL <= HIGH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_kernel_information_struct_v3">PEP_KERNEL_INFORMATION_STRUCT_V3</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_idle_execute">PEP_NOTIFY_PPM_IDLE_EXECUTE</a>