---
UID: NF:extsfns.IDebugFailureAnalysis2.GetFailureClass
title: IDebugFailureAnalysis2::GetFailureClass (extsfns.h)
description: The GetFailureClass method gets the failure class of a DebugFailureAnalysis object. The failure class indicates whether the debugging session that created the DebugFailureAnalysis object is a kernel mode session or a user mode session.
old-location: debugger\idebugfailureanalysis2_getfailureclass.htm
tech.root: debugger
ms.assetid: 4840F881-E3CB-4C89-AE2D-88610790C221
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2::GetFailureClass"]
ms.keywords: GetFailureClass, GetFailureClass method [Windows Debugging], GetFailureClass method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],GetFailureClass method, IDebugFailureAnalysis2.GetFailureClass, IDebugFailureAnalysis2::GetFailureClass, debugger.idebugfailureanalysis2_getfailureclass, extsfns/IDebugFailureAnalysis2::GetFailureClass
f1_keywords:
 - "extsfns/IDebugFailureAnalysis2.GetFailureClass"
 - "IDebugFailureAnalysis2.GetFailureClass"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- extsfns.h
api_name:
- IDebugFailureAnalysis2.GetFailureClass
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::GetFailureClass


## -description


The <b>GetFailureClass</b> method gets the failure class of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object. The failure class indicates whether the debugging session  that created the <b>DebugFailureAnalysis</b> object is a kernel mode session or a user mode session.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getfailurecode">GetFailureCode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getfailuretype">GetFailureType</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
 

 

