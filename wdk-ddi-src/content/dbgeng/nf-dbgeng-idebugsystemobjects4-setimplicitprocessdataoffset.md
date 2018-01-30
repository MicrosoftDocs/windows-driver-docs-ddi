---
UID: NF:dbgeng.IDebugSystemObjects4.SetImplicitProcessDataOffset
title: IDebugSystemObjects4::SetImplicitProcessDataOffset method
author: windows-driver-content
description: The SetImplicitProcessDataOffset method sets the implicit process for the current target.
old-location: debugger\setimplicitprocessdataoffset.htm
old-project: debugger
ms.assetid: 2a09341d-a580-4817-9103-29d8c36b81e3
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects4 interface [Windows Debugging], SetImplicitProcessDataOffset method, SetImplicitProcessDataOffset method [Windows Debugging], debugger.setimplicitprocessdataoffset, SetImplicitProcessDataOffset method [Windows Debugging], IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects4::SetImplicitProcessDataOffset, IDebugSystemObjects4, IDebugSystemObjects2 interface [Windows Debugging], SetImplicitProcessDataOffset method, SetImplicitProcessDataOffset method [Windows Debugging], IDebugSystemObjects3 interface, IDebugSystemObjects3 interface [Windows Debugging], SetImplicitProcessDataOffset method, IDebugSystemObjects3::SetImplicitProcessDataOffset, SetImplicitProcessDataOffset method [Windows Debugging], IDebugSystemObjects2 interface, IDebugSystemObjects4::SetImplicitProcessDataOffset, IDebugSystemObjects2::SetImplicitProcessDataOffset, dbgeng/IDebugSystemObjects3::SetImplicitProcessDataOffset, IDebugSystemObjects_10effa04-b87c-4555-9860-c2d5057a2529.xml, SetImplicitProcessDataOffset, dbgeng/IDebugSystemObjects2::SetImplicitProcessDataOffset
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
-	IDebugSystemObjects2.SetImplicitProcessDataOffset
-	IDebugSystemObjects3.SetImplicitProcessDataOffset
-	IDebugSystemObjects4.SetImplicitProcessDataOffset
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugSystemObjects4::SetImplicitProcessDataOffset method


## -description


The <b>SetImplicitProcessDataOffset</b> method sets the implicit process for the current target.


## -syntax


````
HRESULT SetImplicitProcessDataOffset(
  [in] ULONG64 Offset
);
````


## -parameters




### -param Offset [in]

Specifies the location in the target's memory address space of the data structure of the system process that is to become the implicit process for the current target.  If this is zero, the implicit process for the current target is set to the default implicit process.


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


In kernel-mode debugging, the data structure is the KPROCESS structure for the process.

In user-mode debugging, the data structure is the process environment block (PEB) for the process.
<div class="alert"><b>Warning</b>    Because it is possible to use <a href="https://msdn.microsoft.com/library/windows/hardware/ff556716">SetImplicitThreadDataOffset</a> to set the implicit thread independently of the implicit process, the implicit thread might not belong to the implicit process.  This can cause errors if you attempt to access any of the user state for the implicit thread, because it will be incompatible with the virtual address space (specified by the implicit process).</div><div> </div>For more information about the current implicit process, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the KPROCESS and PEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.


