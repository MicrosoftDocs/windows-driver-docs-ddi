---
UID: NN:dbgeng.IDebugPlmClient3
title: IDebugPlmClient3
author: windows-driver-content
description: This interface supports Process Lifecycle Management (PLM) for the debug client.
old-location: debugger\idebugplmclient3.htm
old-project: debugger
ms.assetid: 5B0580FF-0829-406A-B511-C0CD91A08D5F
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::SetImplicitThreadDataOffset, SetImplicitThreadDataOffset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugPlmClient3
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugPlmClient3 interface



## -description
This interface supports Process Lifecycle Management (PLM) for the debug client.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugPlmClient3</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IDebugPlmClient3</b> also has these types of members:

The <b>IDebugPlmClient3</b> interface has these methods.

    Launches and attaches to a Process Lifecycle Management (PLM) background task.

Disables a Process Lifecycle Management (PLM) package debug.

Enables a Process Lifecycle Management (PLM) package debug.

    Launches and attaches to a Process Lifecycle Management (PLM) application. 

Query a Process Lifecycle Management (PLM) package list.

Query a Process Lifecycle Management (PLM) package.

Resumes a Process Lifecycle Management (PLM) package.

Suspends a Process Lifecycle Management (PLM) package.

Ends a Process Lifecycle Management (PLM) package.

 


## -members
The <b>IDebugPlmClient3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/77358032-1777-46F4-BF16-5DFFAC15E672">ActivateAndDebugPlmBgTaskWide</a>
</td>
<td align="left" width="63%">
    Launches and attaches to a Process Lifecycle Management (PLM) background task.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/23A5BAC2-E8F3-47FF-9B63-3FFF447C33B4">DisablePlmPackageDebugWide</a>
</td>
<td align="left" width="63%">
Disables a Process Lifecycle Management (PLM) package debug.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/6373B8BD-264D-4D03-9FE9-F87E45D617EE">EnablePlmPackageDebugWide</a>
</td>
<td align="left" width="63%">
Enables a Process Lifecycle Management (PLM) package debug.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/F3DD5912-46E5-43E5-A920-940FC8FCD83F">LaunchAndDebugPlmAppWide</a>
</td>
<td align="left" width="63%">
    Launches and attaches to a Process Lifecycle Management (PLM) application. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/BAAAF09B-F39D-44E0-9409-1C98B0C6A56B">QueryPlmPackageList</a>
</td>
<td align="left" width="63%">
Query a Process Lifecycle Management (PLM) package list.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/29BAAEF9-5B69-4723-BC23-A8B668E2A867">QueryPlmPackageWide</a>
</td>
<td align="left" width="63%">
Query a Process Lifecycle Management (PLM) package.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/CC69357E-425B-440B-93D0-918E8586D5DF">ResumePlmPackageWide</a>
</td>
<td align="left" width="63%">
Resumes a Process Lifecycle Management (PLM) package.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/B887CCD2-0747-483E-A4CF-632471AB19A2">SuspendPlmPackageWide</a>
</td>
<td align="left" width="63%">
Suspends a Process Lifecycle Management (PLM) package.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/EBEEF2C7-AD2E-4BE5-B20C-D4E148F1454C">TerminatePlmPackageWide</a>
</td>
<td align="left" width="63%">
Ends a Process Lifecycle Management (PLM) package.

</td>
</tr>
</table>    Launches and attaches to a Process Lifecycle Management (PLM) background task.

Disables a Process Lifecycle Management (PLM) package debug.

Enables a Process Lifecycle Management (PLM) package debug.

    Launches and attaches to a Process Lifecycle Management (PLM) application. 

Query a Process Lifecycle Management (PLM) package list.

Query a Process Lifecycle Management (PLM) package.

Resumes a Process Lifecycle Management (PLM) package.

Suspends a Process Lifecycle Management (PLM) package.

Ends a Process Lifecycle Management (PLM) package.

 


## -remarks
