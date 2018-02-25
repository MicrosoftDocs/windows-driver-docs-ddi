---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentProcessDataOffset
title: IDebugSystemObjects4::GetCurrentProcessDataOffset method
author: windows-driver-content
description: The GetCurrentProcessDataOffset method returns the location of the system data structure describing the current process.
old-location: debugger\getcurrentprocessdataoffset.htm
old-project: debugger
ms.assetid: a71190ac-0368-40bd-a19d-82a27986a9b3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 4, :, C, D, G, GetCurrentProcessDataOffset method [Windows Debugging], GetCurrentProcessDataOffset method [Windows Debugging], IDebugSystemObjects interface, GetCurrentProcessDataOffset method [Windows Debugging], IDebugSystemObjects2 interface, GetCurrentProcessDataOffset method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentProcessDataOffset method [Windows Debugging], IDebugSystemObjects4 interface, GetCurrentProcessDataOffset,IDebugSystemObjects.GetCurrentProcessDataOffset, GetCurrentProcessDataOffset,IDebugSystemObjects2.GetCurrentProcessDataOffset, GetCurrentProcessDataOffset,IDebugSystemObjects3.GetCurrentProcessDataOffset, GetCurrentProcessDataOffset,IDebugSystemObjects4.GetCurrentProcessDataOffset, I, IDebugSystemObjects, IDebugSystemObjects interface [Windows Debugging], GetCurrentProcessDataOffset method, IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentProcessDataOffset method, IDebugSystemObjects2::GetCurrentProcessDataOffset, IDebugSystemObjects3, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentProcessDataOffset method, IDebugSystemObjects3::GetCurrentProcessDataOffset, IDebugSystemObjects4, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentProcessDataOffset method, IDebugSystemObjects4::GetCurrentProcessDataOffset, IDebugSystemObjects::GetCurrentProcessDataOffset, IDebugSystemObjects_f3602018-7f0a-45eb-aadc-26e0f7349737.xml, O, P, S, a, b, c, dbgeng/IDebugSystemObjects2::GetCurrentProcessDataOffset, dbgeng/IDebugSystemObjects3::GetCurrentProcessDataOffset, dbgeng/IDebugSystemObjects4::GetCurrentProcessDataOffset, dbgeng/IDebugSystemObjects::GetCurrentProcessDataOffset, debugger.getcurrentprocessdataoffset, e, f, g, j, m, n, o, r, s, t, u, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSystemObjects.GetCurrentProcessDataOffset
-	IDebugSystemObjects2.GetCurrentProcessDataOffset
-	IDebugSystemObjects3.GetCurrentProcessDataOffset
-	IDebugSystemObjects4.GetCurrentProcessDataOffset
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects4::GetCurrentProcessDataOffset method


## -description


The <b>GetCurrentProcessDataOffset</b> method returns the location of the system data structure describing the current process.


## -syntax


````
HRESULT GetCurrentProcessDataOffset(
  [out] PULONG64 Offset
);
````


## -parameters




### -param Offset [out]

Receives the location in the target's virtual address space of the system data structure describing the current process.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 




## -remarks



In user-mode debugging, the location returned is of the process environment block (PEB) for the current process.  This is the same location returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff545839">GetCurrentProcessPeb</a>.

In kernel-mode debugging, the location returned is of the KPROCESS structure for the system process in which the last event occurred.

<div class="alert"><b>Note</b>    In kernel mode, the current process of the target is always the single virtual process the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> created for the kernel.  However, because events may occur in different system processes, the KPROCESS location returned by this method may change.</div>
<div> </div>
For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details about the PEB and KPROCESS structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.



