---
UID: NF:wdm.KeRestoreExtendedProcessorState
title: KeRestoreExtendedProcessorState function
author: windows-driver-content
description: The KeRestoreExtendedProcessorState routine restores extended processor state information that was previously saved.
old-location: kernel\kerestoreextendedprocessorstate.htm
old-project: kernel
ms.assetid: ea5e654a-9cb5-4d4d-9660-339410a6a20f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeRestoreExtendedProcessorState, KeRestoreExtendedProcessorState routine [Kernel-Mode Driver Architecture], k105_35142457-ddfe-4773-b4ed-d2d84d5c74d0.xml, kernel.kerestoreextendedprocessorstate, wdm/KeRestoreExtendedProcessorState
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeRestoreExtendedProcessorState
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeRestoreExtendedProcessorState function


## -description


The <b>KeRestoreExtendedProcessorState</b> routine restores extended processor state information that was previously saved.


## -syntax


````
VOID KeRestoreExtendedProcessorState(
  _In_ PXSTATE_SAVE XStateSave
);
````


## -parameters




### -param XStateSave [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566414">XSTATE_SAVE</a> structure that contains the extended processor state information to restore. The contents of this structure must have been previously saved by the <a href="..\wdm\nf-wdm-kesaveextendedprocessorstate.md">KeSaveExtendedProcessorState</a> routine.


## -returns



None




## -remarks



Kernel-mode driver code must ensure that calls to <b>KeSaveExtendedProcessorState</b> and <b>KeRestoreExtendedProcessorState</b> are properly nested. This is required so that, at each nesting level, the state that was restored by the <b>KeRestoreExtendedProcessorState</b> call is the same state that was saved by the corresponding <b>KeSaveExtendedProcessorState</b> call. To ensure proper nesting, kernel-mode driver code must follow these rules:

<ul>
<li>
A <b>KeRestoreExtendedProcessorState</b> call that restores a saved state must be running at the same IRQL as the <b>KeSaveExtendedProcessorState</b> call that saved the state. 

</li>
<li>
If a pair of <b>KeSaveExtendedProcessorState</b> and <b>KeRestoreExtendedProcessorState</b> calls is nested within a pair of surrounding <b>KeSaveExtendedProcessorState</b> and <b>KeRestoreExtendedProcessorState</b> calls, the IRQL for the nested calls must not be lower than the IRQL for the surrounding calls. 

</li>
<li>
Typically, the caller-allocated <b>XSTATE_SAVE</b> structure that contains the state that was saved by <b>KeSaveExtendedProcessorState</b> resides on the stack. The stack naturally preserves the nesting of saved state information. If driver code stores the state in a location other than the stack, the driver writer must take special care to preserve the nesting of the <b>KeSaveExtendedProcessorState</b> and <b>KeRestoreExtendedProcessorState</b> calls.

</li>
<li>
The <b>KeRestoreExtendedProcessorState</b> call that restores a saved state must be running in the same thread as the <b>KeSaveExtendedProcessorState</b> call that saved the state. 

</li>
</ul>
A similar set of rules apply to the <a href="..\wdm\nf-wdm-kesavefloatingpointstate.md">KeSaveFloatingPointState</a> and <a href="..\wdm\nf-wdm-kerestorefloatingpointstate.md">KeRestoreFloatingPointState</a> routines.




## -see-also

<a href="..\wdm\nf-wdm-kerestorefloatingpointstate.md">KeRestoreFloatingPointState</a>



<a href="..\wdm\nf-wdm-kesavefloatingpointstate.md">KeSaveFloatingPointState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566414">XSTATE_SAVE</a>



<a href="..\wdm\nf-wdm-kesaveextendedprocessorstate.md">KeSaveExtendedProcessorState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRestoreExtendedProcessorState routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

