---
UID: NN:wdtfsystemaction.IWDTFSystemAction2
title: IWDTFSystemAction2
author: windows-driver-content
description: Defines operations and properties that support driver testing.
old-location: dtf\iwdtfsystemaction2.htm
old-project: dtf
ms.assetid: 783ddaaa-f39f-4e66-85aa-4788bf7959a6
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: dtf.iwdtfsystemaction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], IWDTFSystemAction2 interface [Windows Device Testing Framework], described, IWDTFSystemAction2, wdtfsystemaction/IWDTFSystemAction2, Microsoft.WDTF.IWDTFSystemAction2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wdtfsystemaction.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFSystemAction.Interop.dll
req.type-library: 
req.lib: wdtfsystemaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFSystemAction.Interop.dll
apiname:
-	IWDTFSystemAction2
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSystemAction2 interface


## -description


Defines operations and properties that support driver testing.


## -members

The <b>IWDTFSystemAction2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/11d774b1-2af9-453e-b53e-c232d84bcbee">ConnectedStandby</a>
</td>
<td align="left" width="63%">
Puts the system into Connected Standby state and 
    exits Connected Standby state after the desired time has passed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439308">GetFirstSleepState</a>
</td>
<td align="left" width="63%">
Returns the first supported sleep state.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439310">GetNextSleepState</a>
</td>
<td align="left" width="63%">
Returns the next supported sleep state.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/B8C422C0-7E42-4BE7-8919-A4ABF33E8D5E">PowerAnalyzeTraceByFile</a>
</td>
<td align="left" width="63%">
Analyzes a power trace session that has already been collected and stored in the associated trace message (.etl) log file. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/d27678cb-8aad-4cbe-a65e-64828ff4944a">PowerTracingEnd</a>
</td>
<td align="left" width="63%">
Ends a power trace session. This method
    is available starting with Windows 8.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b82ebd99-289e-4761-9717-ce09cf5c40f0">PowerTracingStart</a>
</td>
<td align="left" width="63%">
Starts a power trace session using the default location to store the associated trace message file. This method
    is available starting with Windows 8.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/c37095d2-fbf5-49fa-a6c8-b4776bf530af">PowerTracingStartByFile</a>
</td>
<td align="left" width="63%">
Starts a power trace session and specifies the  path to store the associated trace message file. This method
    is available starting with Windows 8.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439319">RebootRestart</a>
</td>
<td align="left" width="63%">
Restart the system and the current test.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439321">RebootRestartWithContext</a>
</td>
<td align="left" width="63%">
Restarts the system and the current test with context data.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439324">Sleep</a>
</td>
<td align="left" width="63%">
Puts the system into the desired sleep state.

</td>
</tr>
</table>Puts the system into Connected Standby state and 
    exits Connected Standby state after the desired time has passed.

Returns the first supported sleep state.

Returns the next supported sleep state.

Analyzes a power trace session that has already been collected and stored in the associated trace message (.etl) log file. 

Ends a power trace session. This method
    is available starting with Windows 8.

Starts a power trace session using the default location to store the associated trace message file. This method
    is available starting with Windows 8.

Starts a power trace session and specifies the  path to store the associated trace message file. This method
    is available starting with Windows 8.

Restart the system and the current test.

Restarts the system and the current test with context data.

Puts the system into the desired sleep state.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFSystemAction2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/mt158256">Critical</a>


</td>
<td align="left" width="10%">
Read/write

</td>
<td align="left" width="63%">
Gets or sets a value that indicates whether the the system power state is critical.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439312">GetRebootContext</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the context data after the system restarts as a result of a call to
	      <a href="https://msdn.microsoft.com/library/windows/hardware/hh439321">RebootRestartWithContext</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439315">IsRestarted</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a value that indicates whether the test script restarted as a result of a call to 
	      <a href="https://msdn.microsoft.com/library/windows/hardware/hh439319">RebootRestart</a> or 
	      <a href="https://msdn.microsoft.com/library/windows/hardware/hh439321">RebootRestartWithContext</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439317">IsRestartedWithContext</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a value that indicates whether the test script was restarted for a specific context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439328">SleepWakeTimeInSeconds</a>


</td>
<td align="left" width="10%">
Read/write

</td>
<td align="left" width="63%">
Gets or sets the time in seconds when the system will wake from the sleep state.

</td>
</tr>
</table>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt158256">Critical</a>


Read/write

Gets or sets a value that indicates whether the the system power state is critical.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh439312">GetRebootContext</a>


Read-only

Gets the context data after the system restarts as a result of a call to
	      <a href="https://msdn.microsoft.com/library/windows/hardware/hh439321">RebootRestartWithContext</a>.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh439315">IsRestarted</a>


Read-only

Gets a value that indicates whether the test script restarted as a result of a call to 
	      <a href="https://msdn.microsoft.com/library/windows/hardware/hh439319">RebootRestart</a> or 
	      <a href="https://msdn.microsoft.com/library/windows/hardware/hh439321">RebootRestartWithContext</a>.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh439317">IsRestartedWithContext</a>


Read-only

Gets a value that indicates whether the test script was restarted for a specific context.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh439328">SleepWakeTimeInSeconds</a>


Read/write

Gets or sets the time in seconds when the system will wake from the sleep state.

 

