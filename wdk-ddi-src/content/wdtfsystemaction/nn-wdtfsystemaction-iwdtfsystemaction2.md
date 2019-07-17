---
UID: NN:wdtfsystemaction.IWDTFSystemAction2
title: IWDTFSystemAction2 (wdtfsystemaction.h)
description: Defines operations and properties that support driver testing.
old-location: dtf\iwdtfsystemaction2.htm
tech.root: dtf
ms.assetid: 783ddaaa-f39f-4e66-85aa-4788bf7959a6
ms.date: 04/04/2018
ms.keywords: IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], IWDTFSystemAction2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFSystemAction2, dtf.iwdtfsystemaction2, wdtfsystemaction/IWDTFSystemAction2
ms.topic: interface
f1_keywords:
 - "wdtfsystemaction/IWDTFSystemAction2"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTFSystemAction.Interop.dll
api_name:
- IWDTFSystemAction2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSystemAction2 interface


## -description


Defines operations and properties that support driver testing.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFSystemAction2</b> interface inherits from <b>IWDTFAction2</b>. <b>IWDTFSystemAction2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IWDTFSystemAction2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-connectedstandby">ConnectedStandby</a>
</td>
<td align="left" width="63%">
Puts the system into Connected Standby state and 
    exits Connected Standby state after the desired time has passed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-getfirstsleepstate">GetFirstSleepState</a>
</td>
<td align="left" width="63%">
Returns the first supported sleep state.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-getnextsleepstate">GetNextSleepState</a>
</td>
<td align="left" width="63%">
Returns the next supported sleep state.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-poweranalyzetracebyfile">PowerAnalyzeTraceByFile</a>
</td>
<td align="left" width="63%">
Analyzes a power trace session that has already been collected and stored in the associated trace message (.etl) log file. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-powertracingend">PowerTracingEnd</a>
</td>
<td align="left" width="63%">
Ends a power trace session. This method
    is available starting with Windows 8.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-powertracingstart">PowerTracingStart</a>
</td>
<td align="left" width="63%">
Starts a power trace session using the default location to store the associated trace message file. This method
    is available starting with Windows 8.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-powertracingstartbyfile">PowerTracingStartByFile</a>
</td>
<td align="left" width="63%">
Starts a power trace session and specifies the  path to store the associated trace message file. This method
    is available starting with Windows 8.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-rebootrestart">RebootRestart</a>
</td>
<td align="left" width="63%">
Restart the system and the current test.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-rebootrestartwithcontext">RebootRestartWithContext</a>
</td>
<td align="left" width="63%">
Restarts the system and the current test with context data.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-sleep">Sleep</a>
</td>
<td align="left" width="63%">
Puts the system into the desired sleep state.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFSystemAction2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/mt158256(v=vs.85)">Critical</a>


</td>
<td align="left" width="10%">
Read/write

</td>
<td align="left" width="63%">
Gets or sets a value that indicates whether the system power state is critical.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh439312(v=vs.85)">GetRebootContext</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the context data after the system restarts as a result of a call to
	      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-rebootrestartwithcontext">RebootRestartWithContext</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-get_isrestarted">IsRestarted</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a value that indicates whether the test script restarted as a result of a call to 
	      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-rebootrestart">RebootRestart</a> or 
	      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-rebootrestartwithcontext">RebootRestartWithContext</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-isrestartedwithcontext">IsRestartedWithContext</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-put_sleepwaketimeinseconds">SleepWakeTimeInSeconds</a>


</td>
<td align="left" width="10%">
Read/write

</td>
<td align="left" width="63%">
Gets or sets the time in seconds when the system will wake from the sleep state.

</td>
</tr>
</table> 

