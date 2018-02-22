---
UID: NF:dbgeng.IDebugControl2.GetNumberTextReplacements
title: IDebugControl2::GetNumberTextReplacements method
author: windows-driver-content
description: The GetNumberTextReplacements method returns the number of currently defined user-named and automatic aliases.
old-location: debugger\getnumbertextreplacements.htm
old-project: Debugger
ms.assetid: d15400a8-3d8d-48dd-86f0-4e53f8b04add
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugControl2, IDebugControl3::GetNumberTextReplacements, dbgeng/IDebugControl3::GetNumberTextReplacements, GetNumberTextReplacements method [Windows Debugging], GetNumberTextReplacements method [Windows Debugging], IDebugControl3 interface, GetNumberTextReplacements, debugger.getnumbertextreplacements, IDebugControl2::GetNumberTextReplacements, GetNumberTextReplacements method [Windows Debugging], IDebugControl2 interface, dbgeng/IDebugControl2::GetNumberTextReplacements, IDebugControl_34139b78-b8a1-4096-a54c-7fdfac7024ce.xml, IDebugControl3 interface [Windows Debugging], GetNumberTextReplacements method, IDebugControl2 interface [Windows Debugging], GetNumberTextReplacements method
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
-	IDebugControl2.GetNumberTextReplacements
-	IDebugControl3.GetNumberTextReplacements
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::GetNumberTextReplacements method


## -description


The <b>GetNumberTextReplacements</b> method returns the number of currently defined user-named and automatic aliases.  


## -syntax


````
HRESULT GetNumberTextReplacements(
  [out] PULONG NumRepl
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553268">OutputTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556818">SetTextReplacement</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549280">GetTextReplacement</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl2::GetNumberTextReplacements method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

