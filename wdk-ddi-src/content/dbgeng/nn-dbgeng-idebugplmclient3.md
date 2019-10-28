---
UID: NN:dbgeng.IDebugPlmClient3
title: IDebugPlmClient3 (dbgeng.h)
description: This interface supports Process Lifecycle Management (PLM) for the debug client.
old-location: debugger\idebugplmclient3.htm
tech.root: debugger
ms.assetid: 5B0580FF-0829-406A-B511-C0CD91A08D5F
ms.date: 05/03/2018
ms.keywords: IDebugPlmClient3, IDebugPlmClient3 interface [Windows Debugging], IDebugPlmClient3 interface [Windows Debugging],described, dbgeng/IDebugPlmClient3, debugger.idebugplmclient3
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugPlmClient3"
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
- dbgeng.h
api_name:
- IDebugPlmClient3
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugPlmClient3 interface


## -description


This interface supports Process Lifecycle Management (PLM) for the debug client.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugPlmClient3</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugPlmClient3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugPlmClient3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugplmclient3-activateanddebugplmbgtaskwide">ActivateAndDebugPlmBgTaskWide</a>
</td>
<td align="left" width="63%">
    Launches and attaches to a Process Lifecycle Management (PLM) background task.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugplmclient3-disableplmpackagedebugwide">DisablePlmPackageDebugWide</a>
</td>
<td align="left" width="63%">
Disables a Process Lifecycle Management (PLM) package debug.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugplmclient3-enableplmpackagedebugwide">EnablePlmPackageDebugWide</a>
</td>
<td align="left" width="63%">
Enables a Process Lifecycle Management (PLM) package debug.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugplmclient3-launchanddebugplmappwide">LaunchAndDebugPlmAppWide</a>
</td>
<td align="left" width="63%">
    Launches and attaches to a Process Lifecycle Management (PLM) application. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugplmclient3-queryplmpackagelist">QueryPlmPackageList</a>
</td>
<td align="left" width="63%">
Query a Process Lifecycle Management (PLM) package list.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugplmclient3-queryplmpackagewide">QueryPlmPackageWide</a>
</td>
<td align="left" width="63%">
Query a Process Lifecycle Management (PLM) package.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugplmclient3-resumeplmpackagewide">ResumePlmPackageWide</a>
</td>
<td align="left" width="63%">
Resumes a Process Lifecycle Management (PLM) package.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugplmclient3-suspendplmpackagewide">SuspendPlmPackageWide</a>
</td>
<td align="left" width="63%">
Suspends a Process Lifecycle Management (PLM) package.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugplmclient3-terminateplmpackagewide">TerminatePlmPackageWide</a>
</td>
<td align="left" width="63%">
Ends a Process Lifecycle Management (PLM) package.

</td>
</tr>
</table> 

