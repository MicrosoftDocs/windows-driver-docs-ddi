---
UID: NF:extsfns.IDebugFailureAnalysis2.GetFailureClass
title: IDebugFailureAnalysis2::GetFailureClass
author: windows-driver-content
description: The GetFailureClass method gets the failure class of a DebugFailureAnalysis object. The failure class indicates whether the debugging session that created the DebugFailureAnalysis object is a kernel mode session or a user mode session.
old-location: debugger\idebugfailureanalysis2_getfailureclass.htm
old-project: debugger
ms.assetid: 4840F881-E3CB-4C89-AE2D-88610790C221
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetFailureClass, GetFailureClass method [Windows Debugging], GetFailureClass method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],GetFailureClass method, IDebugFailureAnalysis2.GetFailureClass, IDebugFailureAnalysis2::GetFailureClass, debugger.idebugfailureanalysis2_getfailureclass, extsfns/IDebugFailureAnalysis2::GetFailureClass
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	extsfns.h
api_name:
-	IDebugFailureAnalysis2.GetFailureClass
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::GetFailureClass


## -description


The <b>GetFailureClass</b> method gets the failure class of a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object. The failure class indicates whether the debugging session  that created the <b>DebugFailureAnalysis</b> object is a kernel mode session or a user mode session.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983416">GetFailureCode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983417">GetFailureType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

