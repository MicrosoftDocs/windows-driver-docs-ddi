---
UID: NF:wdm.KdRefreshDebuggerNotPresent
title: KdRefreshDebuggerNotPresent function
author: windows-driver-content
description: The KdRefreshDebuggerNotPresent macro refreshes the value of the KD_DEBUGGER_NOT_PRESENT global kernel variable.
old-location: devtest\kdrefreshdebuggernotpresent.htm
old-project: devtest
ms.assetid: 3b43943d-99b7-4d60-96fe-019f4ba2b809
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DebugFns_77b08eed-2f06-4ede-b02f-f1a7a5ab9ba5.xml, KdRefreshDebuggerNotPresent, KdRefreshDebuggerNotPresent function [Driver Development Tools], devtest.kdrefreshdebuggernotpresent, ntddk/KdRefreshDebuggerNotPresent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows Server 2003 and later.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KdRefreshDebuggerNotPresent
product: Windows
targetos: Windows
req.typenames: 
---

# KdRefreshDebuggerNotPresent function


## -description


The <b>KdRefreshDebuggerNotPresent</b> macro refreshes the value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548125">KD_DEBUGGER_NOT_PRESENT</a> global kernel variable.


## -parameters






## -returns



<b>KdRefreshDebuggerNotPresent</b> returns the value of KD_DEBUGGER_NOT_PRESENT.




## -remarks



When <b>KdRefreshDebuggerNotPresent</b> is called, it forces the value of KD_DEBUGGER_NOT_PRESENT to be updated to reflect whether a kernel debugger is currently attached. This updated value is also used as the return value of this routine.

If a kernel debugger was recently attached or removed, the value of KD_DEBUGGER_NOT_PRESENT may not reflect the new state. If you suspect this has happened, you should call <b>KdRefreshDebuggerNotPresent</b> to refresh the value of this variable. After this call, you may use either the value of KD_DEBUGGER_NOT_PRESENT or the return value of <b>KdRefreshDebuggerNotPresent</b> to determine if the kernel debugger is present.

KD_DEBUGGER_NOT_PRESENT can be modified by Windows or any other kernel-mode binary. Therefore, it is possible that the most recent return value of <b>KdRefreshDebuggerNotPresent</b> may not match the current value of KD_DEBUGGER_NOT_PRESENT.

<div class="alert"><b>Note</b>  <b>KdRefreshDebuggerNotPresent</b> works equally well in the free build of a driver and the checked build of a driver -- unlike the other routines beginning with the letters "Kd."</div>
<div> </div>
The following sample shows how to use <b>KdRefreshDebuggerNotPresent</b>:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>if (KdRefreshDebuggerNotPresent() == FALSE)
{
    //  A kernel debugger is active.
    DbgPrint("A problem occurred\n");
 DbgBreakPoint();
}
else
{
 //  No kernel debugger attached, or kernel debugging not enabled.
 KeBugCheckEx(...);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541860">Determining if a Debugger is Attached</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548118">KD_DEBUGGER_ENABLED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548125">KD_DEBUGGER_NOT_PRESENT</a>
 

 

