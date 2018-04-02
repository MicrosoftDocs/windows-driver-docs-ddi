---
UID: NF:dbgeng.IDebugControl2.GetNumberTextReplacements
title: IDebugControl2::GetNumberTextReplacements method
author: windows-driver-content
description: The GetNumberTextReplacements method returns the number of currently defined user-named and automatic aliases.
old-location: debugger\getnumbertextreplacements.htm
old-project: debugger
ms.assetid: d15400a8-3d8d-48dd-86f0-4e53f8b04add
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetNumberTextReplacements method [Windows Debugging], GetNumberTextReplacements method [Windows Debugging], IDebugControl2 interface, GetNumberTextReplacements method [Windows Debugging], IDebugControl3 interface, GetNumberTextReplacements,IDebugControl2.GetNumberTextReplacements, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetNumberTextReplacements method, IDebugControl2::GetNumberTextReplacements, IDebugControl3 interface [Windows Debugging], GetNumberTextReplacements method, IDebugControl3::GetNumberTextReplacements, IDebugControl_34139b78-b8a1-4096-a54c-7fdfac7024ce.xml, dbgeng/IDebugControl2::GetNumberTextReplacements, dbgeng/IDebugControl3::GetNumberTextReplacements, debugger.getnumbertextreplacements
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
-	IDebugControl2.GetNumberTextReplacements
-	IDebugControl3.GetNumberTextReplacements
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::GetNumberTextReplacements method


## -description


The <b>GetNumberTextReplacements</b> method returns the number of currently defined user-named and automatic aliases.  


## -parameters




### -param NumRepl [out]

Receives the total number of user-named and automatic aliases.


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



For an overview of aliases used by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551041">Interacting with the Engine</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549280">GetTextReplacement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553268">OutputTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556818">SetTextReplacement</a>
 

 

