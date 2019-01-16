---
UID: NF:wdm.KeRestoreFloatingPointState
title: KeRestoreFloatingPointState function
description: The KeRestoreFloatingPointState routine restores the nonvolatile floating-point context saved by the preceding call to KeSaveFloatingPointState.
old-location: kernel\kerestorefloatingpointstate.htm
tech.root: kernel
ms.assetid: 9a9b3c9f-5371-4d70-b1f3-5038e4cabc83
ms.date: 04/30/2018
ms.keywords: KeRestoreFloatingPointState, KeRestoreFloatingPointState routine [Kernel-Mode Driver Architecture], k105_94a36699-2129-4e69-ba6a-206452f0b723.xml, kernel.kerestorefloatingpointstate, wdm/KeRestoreFloatingPointState
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
-	KeRestoreFloatingPointState
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeRestoreFloatingPointState function


## -description


The <b>KeRestoreFloatingPointState</b> routine restores the nonvolatile floating-point context saved by the preceding call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff553243">KeSaveFloatingPointState</a>. 


## -parameters




### -param FloatSave [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554233">KFLOATING_SAVE</a> structure that was passed in the preceding call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff553243">KeSaveFloatingPointState</a>.


## -returns



<b>KeRestoreFloatingPointState</b> returns STATUS_SUCCESS.




## -remarks



<b>KeRestoreFloatingPointState</b> is the reciprocal of <b>KeSaveFloatingPointState</b>. 

Any routine that calls <b>KeSaveFloatingPointState</b><i> must</i> call <b>KeRestoreFloatingPointState</b> before that routine returns control, and it must be running at the same IRQL as that from which the preceding call to <b>KeSaveFloatingPointState</b> occurred. Failure to meet either of these conditions causes a system bug check.

Kernel-mode driver code must ensure that calls to <b>KeSaveFloatingPointState</b> and <b>KeRestoreFloatingPointState</b> are properly nested. This is required so that, at each nesting level, the state that was restored by the <b>KeRestoreFloatingPointState</b> call is the same state that was saved by the corresponding <b>KeSaveFloatingPointState</b> call. To ensure proper nesting, kernel-mode driver code must follow these rules:

<ul>
<li>
A <b>KeRestoreFloatingPointState</b> call that restores a saved state must be running at the same IRQL as the <b>KeSaveFloatingPointState</b> call that saved the state.

</li>
<li>
If a pair of <b>KeSaveFloatingPointState</b> and <b>KeRestoreFloatingPointState</b> calls is nested within a pair of surrounding <b>KeSaveFloatingPointState</b> and <b>KeRestoreFloatingPointState</b> calls, the IRQL for the nested calls must not be lower than the IRQL for the surrounding calls. 

</li>
<li>
Typically, the caller-allocated <b>KFLOATING_SAVE</b> structure that contains the state that was saved by <b>KeSaveFloatingPointState</b> resides on the stack. The stack naturally preserves the nesting of saved state information. If driver code stores the state in a location other than the stack, the driver writer must take special care to preserve the nesting of the <b>KeSaveFloatingPointState</b> and <b>KeRestoreFloatingPointState</b> calls. 

</li>
<li>
The <b>KeRestoreFloatingPointState</b> call that restores a saved state must be running in the same thread as the <b>KeSaveFloatingPointState</b> call that saved the state. 

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554233">KFLOATING_SAVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553243">KeSaveFloatingPointState</a>
 

 

