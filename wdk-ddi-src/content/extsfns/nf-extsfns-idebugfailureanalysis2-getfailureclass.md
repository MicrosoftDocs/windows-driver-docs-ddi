---
UID: NF:extsfns.IDebugFailureAnalysis2.GetFailureClass
title: IDebugFailureAnalysis2::GetFailureClass method
author: windows-driver-content
description: The GetFailureClass method gets the failure class of a DebugFailureAnalysis object. The failure class indicates whether the debugging session that created the DebugFailureAnalysis object is a kernel mode session or a user mode session.
old-location: debugger\idebugfailureanalysis2_getfailureclass.htm
old-project: debugger
ms.assetid: 4840F881-E3CB-4C89-AE2D-88610790C221
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 2, :, A, C, D, F, G, GetFailureClass method [Windows Debugging], GetFailureClass method [Windows Debugging], IDebugFailureAnalysis2 interface, GetFailureClass,IDebugFailureAnalysis2.GetFailureClass, I, IDebugFailureAnalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], GetFailureClass method, IDebugFailureAnalysis2::GetFailureClass, a, b, debugger.idebugfailureanalysis2_getfailureclass, e, extsfns/IDebugFailureAnalysis2::GetFailureClass, g, i, l, n, r, s, t, u, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: extsfns.h
req.include-header: 
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
req.lib: extsfns.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	extsfns.h
apiname:
-	IDebugFailureAnalysis2.GetFailureClass
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::GetFailureClass method


## -description


The <b>GetFailureClass</b> method gets the failure class of a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object. The failure class indicates whether the debugging session  that created the <b>DebugFailureAnalysis</b> object is a kernel mode session or a user mode session.


## -syntax


````
ULONG GetFailureClass();
````


## -parameters






## -returns



<table>
<tr>
<th>Return code/value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>DEBUG_CLASS_UNINITIALIZED</b></dt>
<dt>0</dt>
</dl>
</td>
<td width="60%">
The debug class has not been initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>DEBUG_CLASS_KERNEL</b></dt>
<dt>1</dt>
</dl>
</td>
<td width="60%">
The debugging session is a kernel-mode session.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>DEBUG_CLASS_USER_WINDOWS</b></dt>
<dt>2</dt>
</dl>
</td>
<td width="60%">
The debugging session is a user-mode session.

</td>
</tr>
</table>
 

These return values are defined in dbgeng.h.




## -see-also

<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983416">GetFailureCode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983417">GetFailureType</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::GetFailureClass method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

