---
UID: NF:wdm.KeSaveFloatingPointState
title: KeSaveFloatingPointState function
author: windows-driver-content
description: The KeSaveFloatingPointState routine saves the nonvolatile floating-point context so the caller can carry out floating-point operations.
old-location: kernel\kesavefloatingpointstate.htm
old-project: kernel
ms.assetid: 2ab1b2dd-4848-4eb0-9836-e3be987535a6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k105_f004bc61-7a09-46d1-a9c3-dc2a76a03c43.xml, KeSaveFloatingPointState, wdm/KeSaveFloatingPointState, kernel.kesavefloatingpointstate, KeSaveFloatingPointState routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeSaveFloatingPointState
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeSaveFloatingPointState function


## -description


The <b>KeSaveFloatingPointState</b> routine saves the nonvolatile floating-point context so the caller can carry out floating-point operations.


## -syntax


````
NTSTATUS KeSaveFloatingPointState(
  _Out_ PKFLOATING_SAVE FloatSave
);
````


## -parameters




### -param FloatSave [out]

Pointer to a caller-allocated resident buffer, which must be at least <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/ff554233">KFLOATING_SAVE</a>).


## -returns


<b>KeSaveFloatingPointState</b> returns STATUS_SUCCESS if it saved the current thread's floating-point context and set up a fresh floating-point context for the caller. Otherwise, it returns one of the following error status codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ILLEGAL_FLOAT_CONTEXT</b></dt>
</dl>
</td>
<td width="60%">
The system is configured to use floating-point emulation, rather than doing floating-point operations in the processors.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>KeSaveFloatingPointState</b> could not allocate sufficient memory to save the current thread's floating-point context.

</td>
</tr>
</table> 



## -remarks


A successful call to <b>KeSaveFloatingPointState</b> allows the caller to carry out floating-point operations of its own, but such a caller must restore the previous nonvolatile floating-point context as soon as its floating-point operations are done. Any routine that calls <b>KeSaveFloatingPointState</b> must call <a href="..\wdm\nf-wdm-kerestorefloatingpointstate.md">KeRestoreFloatingPointState</a> before that routine returns control.

If the call to <b>KeSaveFloatingPointState</b> is successful, the data at <i>FloatSave</i> is opaque to the caller. The caller should not release the memory that it allocated for this data until after the call to <a href="..\wdm\nf-wdm-kerestorefloatingpointstate.md">KeRestoreFloatingPointState</a>.

In Windows Vista and earlier versions of Windows, a <b>KeSaveFloatingPointState</b> call and the corresponding <b>KeRestoreFloatingPointState</b> call must occur in a guarded region. That is, the <a href="..\wdm\nf-wdm-keenterguardedregion.md">KeEnterGuardedRegion</a> routine must be called before <b>KeSaveFloatingPointState</b> is called, and the <a href="..\wdm\nf-wdm-keleaveguardedregion.md">KeLeaveGuardedRegion</a> routine must be called after <b>KeRestoreFloatingPointState</b> is called. No such requirement exists in Windows 7 and later versions of Windows.

For performance reasons, drivers should avoid doing any floating-point operations unless absolutely necessary. The overhead of saving and restoring the current thread's nonvolatile floating-point state degrades the performance of any driver that does floating-point operations.



## -see-also

<a href="..\wdm\nf-wdm-kerestorefloatingpointstate.md">KeRestoreFloatingPointState</a>

<a href="..\wdm\nf-wdm-pscreatesystemthread.md">PsCreateSystemThread</a>

<a href="..\wdm\nf-wdm-kegetcurrentthread.md">KeGetCurrentThread</a>

<a href="..\wdm\nf-wdm-keenterguardedregion.md">KeEnterGuardedRegion</a>

<a href="..\wdm\nf-wdm-keleaveguardedregion.md">KeLeaveGuardedRegion</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSaveFloatingPointState routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

