---
UID: NF:dbgeng.IDebugControl.SetRadix
title: IDebugControl::SetRadix
author: windows-driver-content
description: The SetRadix method sets the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.
old-location: debugger\setradix.htm
tech.root: debugger
ms.assetid: 7346733d-2ac7-4eee-9f9c-ea6e1ee2ce5d
ms.date: 5/3/2018
ms.keywords: IDebugControl interface [Windows Debugging],SetRadix method, IDebugControl.SetRadix, IDebugControl2 interface [Windows Debugging],SetRadix method, IDebugControl2::SetRadix, IDebugControl3 interface [Windows Debugging],SetRadix method, IDebugControl3::SetRadix, IDebugControl::SetRadix, IDebugControl_f0462fa8-da93-414b-b4b1-246a50572bb2.xml, SetRadix, SetRadix method [Windows Debugging], SetRadix method [Windows Debugging],IDebugControl interface, SetRadix method [Windows Debugging],IDebugControl2 interface, SetRadix method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetRadix, dbgeng/IDebugControl3::SetRadix, dbgeng/IDebugControl::SetRadix, debugger.setradix
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl.SetRadix
-	IDebugControl2.SetRadix
-	IDebugControl3.SetRadix
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::SetRadix


## -description


The <b>SetRadix</b> method sets the default radix (number base) used by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> when it evaluates and displays MASM expressions, and when it displays symbol information.


## -parameters




### -param Radix [in]

Specifies the new default radix.  The following table contains the possible values for the radix.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
8

</td>
<td>
Octal

</td>
</tr>
<tr>
<td>
10

</td>
<td>
Decimal

</td>
</tr>
<tr>
<td>
16

</td>
<td>
Hexadecimal

</td>
</tr>
</table>
 


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



When the radix is changed, the engine notifies the event callbacks by passing the DEBUG_CES_RADIX flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> callback method.

For more information about the default radix, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548218">GetRadix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552287">n (Set Number Base)</a>
 

 

