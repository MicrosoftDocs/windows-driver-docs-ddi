---
UID: NF:wdm.KeSaveExtendedProcessorState
title: KeSaveExtendedProcessorState function
author: windows-driver-content
description: The KeSaveExtendedProcessorState routine saves extended processor state information.
old-location: kernel\kesaveextendedprocessorstate.htm
old-project: kernel
ms.assetid: 06be6c3b-cc1a-4e57-8700-03357215d624
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: KeSaveExtendedProcessorState, KeSaveExtendedProcessorState routine [Kernel-Mode Driver Architecture], XSTATE_MASK_GSSE, XSTATE_MASK_LEGACY, XSTATE_MASK_LEGACY_FLOATING_POINT, XSTATE_MASK_LEGACY_SSE, k105_e03ec6f9-5b9b-48dc-ae77-3c27e6edc910.xml, kernel.kesaveextendedprocessorstate, wdm/KeSaveExtendedProcessorState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntoskrnl.exe
api_name:
-	KeSaveExtendedProcessorState
product: Windows
targetos: Windows
req.typenames: 
---

# KeSaveExtendedProcessorState function


## -description


The <b>KeSaveExtendedProcessorState</b> routine saves extended processor state information.


## -parameters




### -param Mask [in]

A 64-bit feature mask. The bits in this mask identify the extended processor feature states to save. If a mask bit is one, the routine saves the state of the feature that is identified by this bit. If a mask bit is zero, the state for the corresponding feature is not saved. This mask must not identify extended processor features that the operating system has not enabled. To obtain a mask of the enabled features, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561905">RtlGetEnabledExtendedFeatures</a> routine.

A caller can set this parameter to the bitwise OR of one or more of the following <b>XSTATE_MASK_<i>XXX</i></b> flag bits:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="XSTATE_MASK_LEGACY_FLOATING_POINT"></a><a id="xstate_mask_legacy_floating_point"></a><dl>
<dt><b>XSTATE_MASK_LEGACY_FLOATING_POINT</b></dt>
</dl>
</td>
<td width="60%">
The floating-point extension (x87/MMX).

</td>
</tr>
<tr>
<td width="40%"><a id="XSTATE_MASK_LEGACY_SSE"></a><a id="xstate_mask_legacy_sse"></a><dl>
<dt><b>XSTATE_MASK_LEGACY_SSE</b></dt>
</dl>
</td>
<td width="60%">
The streaming SIMD extension (SSE).

</td>
</tr>
<tr>
<td width="40%"><a id="XSTATE_MASK_LEGACY"></a><a id="xstate_mask_legacy"></a><dl>
<dt><b>XSTATE_MASK_LEGACY</b></dt>
</dl>
</td>
<td width="60%">
Both the x87/MMX and SSE extensions.

</td>
</tr>
<tr>
<td width="40%"><a id="XSTATE_MASK_GSSE"></a><a id="xstate_mask_gsse"></a><dl>
<dt><b>XSTATE_MASK_GSSE</b></dt>
</dl>
</td>
<td width="60%">
The Intel Sandy Bridge (formerly Gesher) SSE extension.

</td>
</tr>
</table>
 


### -param XStateSave [out]

A pointer to a caller-allocated buffer into which the routine writes an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566414">XSTATE_SAVE</a> structure. This structure contains the saved state information for the extended processor features indicated by the <i>Mask</i> parameter. The buffer must be large enough to contain this structure.


## -returns



<b>KeSaveExtendedProcessorState</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A memory allocation operation failed.

</td>
</tr>
</table>
 




## -remarks



On x86-based processors that support the XSAVE and XRSTOR instructions, these instructions provide a flexible mechanism to save and restore extended processor state information. <b>KeSaveExtendedProcessorState</b> uses these instructions if they are available.

To restore the extended processor state that was saved by <b>KeSaveExtendedProcessorState</b>, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553182">KeRestoreExtendedProcessorState</a> routine.

The <i>Mask</i> parameter specifies the extended processor features whose state is to be saved. A <b>KeRestoreExtendedProcessorState</b> call restores only the extended processor state that was saved by the <b>KeSaveExtendedProcessorState</b> call that saved the state.

Kernel-mode code must save the state of an extended processor feature before it uses that feature, and it must restore the state before it exits.

Interrupt service routines (ISRs) run under severe time constraints that typically prevent them from using extended processor features. However, an ISR can schedule a deferred procedure call (DPC) that uses one or more extended processor features. The DPC routine must save and restore the state of the extended features to preserve the context of the interrupted program in whose process address space the routine runs.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff553243">KeSaveFloatingPointState</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553185">KeRestoreFloatingPointState</a> routines save and restore just the floating-point state (the x87/MMX registers) and the SSE state. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553182">KeRestoreExtendedProcessorState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553185">KeRestoreFloatingPointState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553243">KeSaveFloatingPointState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561905">RtlGetEnabledExtendedFeatures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566414">XSTATE_SAVE</a>
 

 

