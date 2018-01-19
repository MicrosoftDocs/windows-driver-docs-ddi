---
UID: NF:wdm.KeSaveExtendedProcessorState
title: KeSaveExtendedProcessorState function
author: windows-driver-content
description: The KeSaveExtendedProcessorState routine saves extended processor state information.
old-location: kernel\kesaveextendedprocessorstate.htm
old-project: kernel
ms.assetid: 06be6c3b-cc1a-4e57-8700-03357215d624
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeSaveExtendedProcessorState
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
req.alt-api: KeSaveExtendedProcessorState
req.alt-loc: Ntoskrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: <= DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeSaveExtendedProcessorState function



## -description
The <b>KeSaveExtendedProcessorState</b> routine saves extended processor state information.



## -syntax

````
NTSTATUS KeSaveExtendedProcessorState(
  _In_  ULONG64      Mask,
  _Out_ PXSTATE_SAVE XStateSave
);
````


## -parameters

### -param Mask [in]

A 64-bit feature mask. The bits in this mask identify the extended processor feature states to save. If a mask bit is one, the routine saves the state of the feature that is identified by this bit. If a mask bit is zero, the state for the corresponding feature is not saved. This mask must not identify extended processor features that the operating system has not enabled. To obtain a mask of the enabled features, call the <a href="..\ntddk\nf-ntddk-rtlgetenabledextendedfeatures.md">RtlGetEnabledExtendedFeatures</a> routine.

A caller can set this parameter to the bitwise OR of one or more of the following <b>XSTATE_MASK_<i>XXX</i></b> flag bits:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param XSTATE_MASK_LEGACY_FLOATING_POINT

</td>
<td width="60%">
The floating-point extension (x87/MMX).

</td>
</tr>
<tr>

### -param XSTATE_MASK_LEGACY_SSE

</td>
<td width="60%">
The streaming SIMD extension (SSE).

</td>
</tr>
<tr>

### -param XSTATE_MASK_LEGACY

</td>
<td width="60%">
Both the x87/MMX and SSE extensions.

</td>
</tr>
<tr>

### -param XSTATE_MASK_GSSE

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
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A memory allocation operation failed.

 


## -remarks
On x86-based processors that support the XSAVE and XRSTOR instructions, these instructions provide a flexible mechanism to save and restore extended processor state information. <b>KeSaveExtendedProcessorState</b> uses these instructions if they are available.

To restore the extended processor state that was saved by <b>KeSaveExtendedProcessorState</b>, call the <a href="..\wdm\nf-wdm-kerestoreextendedprocessorstate.md">KeRestoreExtendedProcessorState</a> routine.

The <i>Mask</i> parameter specifies the extended processor features whose state is to be saved. A <b>KeRestoreExtendedProcessorState</b> call restores only the extended processor state that was saved by the <b>KeSaveExtendedProcessorState</b> call that saved the state.

Kernel-mode code must save the state of an extended processor feature before it uses that feature, and it must restore the state before it exits.

Interrupt service routines (ISRs) run under severe time constraints that typically prevent them from using extended processor features. However, an ISR can schedule a deferred procedure call (DPC) that uses one or more extended processor features. The DPC routine must save and restore the state of the extended features to preserve the context of the interrupted program in whose process address space the routine runs.

The <a href="..\wdm\nf-wdm-kesavefloatingpointstate.md">KeSaveFloatingPointState</a> and <a href="..\wdm\nf-wdm-kerestorefloatingpointstate.md">KeRestoreFloatingPointState</a> routines save and restore just the floating-point state (the x87/MMX registers) and the SSE state. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-kerestoreextendedprocessorstate.md">KeRestoreExtendedProcessorState</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kerestorefloatingpointstate.md">KeRestoreFloatingPointState</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesavefloatingpointstate.md">KeSaveFloatingPointState</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlgetenabledextendedfeatures.md">RtlGetEnabledExtendedFeatures</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566414">XSTATE_SAVE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSaveExtendedProcessorState routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

