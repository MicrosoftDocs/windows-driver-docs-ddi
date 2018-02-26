---
UID: NF:dbgeng.IDebugControl2.RemoveTextReplacements
title: IDebugControl2::RemoveTextReplacements method
author: windows-driver-content
description: The RemoveTextReplacements method removes all user-named aliases.
old-location: debugger\removetextreplacements.htm
old-project: debugger
ms.assetid: f753542a-c9e6-423f-80e4-c7e2e0f36a04
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 2, :, C, D, I, IDebugControl2, IDebugControl2 interface [Windows Debugging], RemoveTextReplacements method, IDebugControl2::RemoveTextReplacements, IDebugControl3 interface [Windows Debugging], RemoveTextReplacements method, IDebugControl3::RemoveTextReplacements, IDebugControl_ba950bc7-3ed5-4e2e-913d-c743e1190482.xml, R, RemoveTextReplacements method [Windows Debugging], RemoveTextReplacements method [Windows Debugging], IDebugControl2 interface, RemoveTextReplacements method [Windows Debugging], IDebugControl3 interface, RemoveTextReplacements,IDebugControl2.RemoveTextReplacements, T, a, b, c, dbgeng/IDebugControl2::RemoveTextReplacements, dbgeng/IDebugControl3::RemoveTextReplacements, debugger.removetextreplacements, e, g, l, m, n, o, p, r, s, t, u, v, x"
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
-	Dbgeng.h
apiname:
-	IDebugControl2.RemoveTextReplacements
-	IDebugControl3.RemoveTextReplacements
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::RemoveTextReplacements method


## -description


The <b>RemoveTextReplacements</b> method removes all user-named aliases.  


## -syntax


````
HRESULT RemoveTextReplacements();
````


## -parameters






## -returns



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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



For an overview of aliases used by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551041">Interacting with the Engine</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537997">ad (Delete Alias)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547988">GetNumberTextReplacements</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553268">OutputTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556818">SetTextReplacement</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl2::RemoveTextReplacements method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

